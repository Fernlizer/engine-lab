# Data Schema v0.1

## Goals

The schema makes provenance, unknowns, derivations, and assumptions machine-visible. It is engine-agnostic and does not contain Honda-specific values.

Normative JSON Schemas:

- `specs/schemas/engineering-parameter.schema.json`
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

Dataset records should add stable record and parameter identifiers plus explicit engine applicability around this envelope. Those container schemas will be designed after Phase 1 reveals the actual variant and conflict requirements.

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
