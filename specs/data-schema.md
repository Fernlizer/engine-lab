# Data Schema v0.1

## Goals

The schema makes provenance, unknowns, derivations, and assumptions machine-visible. It is engine-agnostic and does not contain Honda-specific values.

Normative JSON Schemas:

- `specs/schemas/engineering-parameter.schema.json`
- `specs/schemas/extraction-run.schema.json`
- `specs/schemas/part-catalog-extraction.schema.json`
- `specs/schemas/part-record.schema.json`
- `specs/schemas/source-record.schema.json`

## Engineering parameter envelope

Verified factory example (illustrative shape only; the number is not a CBR150 claim):

```json
{
  "value": 57.3,
  "unit": "mm",
  "source_id": "SRC-EXAMPLE-0001",
  "evidence_level": "A",
  "value_class": "factory",
  "method": "factory_spec",
  "status": "verified",
  "notes": null
}
```

Unknown example:

```json
{
  "value": null,
  "unit": "mm",
  "source_id": null,
  "evidence_level": "UNKNOWN",
  "value_class": null,
  "method": null,
  "status": "unknown",
  "notes": null
}
```

The illustrative numeric value above demonstrates serialization only and must not be copied into a research dataset.

## Semantics

- `value`: reported or derived scalar; `null` means unknown. Numeric and categorical parameters use the same provenance envelope.
- `unit`: UCUM-compatible unit string when possible, `"1"` for dimensionless numeric values, or `null` when not applicable or unknown.
- `source_id`: foreign key to `sources/registry/sources.yaml`; null only for unknowns or assumptions without an external source.
- `evidence_level`: A through F or UNKNOWN, as defined by the evidence standard.
- `value_class`: `factory`, `direct_measurement`, `secondary_source`, `derived`, or `assumption`.
- `method`: controlled extraction or production method. New methods require a schema revision.
- `status`: `candidate`, `verified`, `disputed`, or `unknown`.
- `notes`: concise context, locator, applicability, uncertainty, or conflict information.

Dataset records add stable record and parameter identifiers plus explicit engine applicability around this envelope.

## Part record

`part-record.schema.json` separates catalog identity from physical engineering data:

- catalog identity records the catalog source, block, reference number, part number, description, reported quantity, and exact applicability;
- supersession fields preserve replacement relationships without implying dimensional equivalence; and
- `attributes` contains zero or more engineering-parameter envelopes for dimensions, material, mass, tolerance, clearance, torque, or limits.

An empty `attributes` array means that the part is identified but no physical engineering value has yet been established. Numbers embedded in a catalog description are transcribed only as reported attributes; their engineering meaning is not expanded from naming convention without a registered standard.

## Part-catalog extraction

`part-catalog-extraction.schema.json` is the compact, source-faithful intake format for interactive catalogs. Dataset-level source, applicability, block, and observation date apply to every contained row. Ordinary part rows live in `items`; repeated size variants live in `parameter_series`, whose members preserve every part-number-to-value mapping.

This format does not weaken provenance and is not a simulation input. A reviewed extraction must be normalized to individual `part-record.schema.json` records before downstream model or validation use. Declared series ranges are completeness checks, not permission to synthesize missing members: every member must have been observed explicitly.

Raw automated extractions use `stage: raw_extraction`, `status: candidate`, the exact category `source_url`, a SHA-256 hash of the fetched response bytes in `source_content_hash`, and a SHA-256 hash of normalized rows in `content_hash`. `model_code` is an opaque catalog identifier and does not imply a market or engineering equivalence.

`completeness_status` describes whether required fields in one dataset remain unresolved. `_extraction-manifest.json`, validated by `extraction-run.schema.json`, separately reports whether every category requested for a bounded scraper run succeeded. A run can therefore be `complete` while its dataset is `partial`, for example when all requested pages were fetched but catalog quantity is not present in the observed source.

## Invariants

- `status: unknown` requires a null value/source/class/method and evidence level UNKNOWN.
- A non-null value cannot use evidence level UNKNOWN.
- Evidence level F is required for `derived` and `assumption` values.
- Derived values require `derivation` metadata with an equation identifier and input record IDs.
- Direct measurements require `measurement` metadata describing the procedure and uncertainty when known.
- Assumptions require a non-empty rationale in `notes`.
- The schema does not treat a high evidence level as proof of cross-market applicability.

## Source registry

Each source record includes at least:

`id`, `title`, `type`, `manufacturer`, `model`, `market`, `year`, `url`, `local_file`, `primary_or_secondary`, `evidence_level`, and `notes`.

The registry begins empty. Placeholder Honda sources are not created because an identifier without an actual source would imply evidence that has not been collected.
