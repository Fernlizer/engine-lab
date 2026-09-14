# Research Standard v0.1

Status: active for repository initialization

Scope: all Engine Lab research findings and datasets

## 1. Purpose

This standard defines how evidence becomes an auditable dataset. It prevents undocumented values, estimates disguised as facts, and accidental loss of contradictory evidence.

## 2. Required workflow

1. **Register the source.** Add source metadata to `sources/registry/sources.yaml` before using it in a dataset.
2. **Preserve the evidence.** Record the stable URL and, when legally permitted, a local file path. Do not copy material whose license does not permit retention.
3. **Extract without interpretation.** Record the value, unit, wording, page/section/table locator, applicable model/market/year, and source identifier.
4. **Normalize explicitly.** Preserve the reported value and unit. If a normalized value is produced, store it as a separate derived record with its conversion method.
5. **Grade the evidence.** Apply the levels in `evidence-levels.md`; the grade describes provenance, not whether a claim is correct.
6. **Classify the value.** Use exactly one class: `factory`, `direct_measurement`, `secondary_source`, `derived`, or `assumption`.
7. **Set status.** Use `candidate`, `verified`, `disputed`, or `unknown`. Verification requires the checks below.
8. **Record conflicts.** Keep each conflicting claim as a separate record and link them in notes or a validation record. Never average conflicting values by default.
9. **Validate before modeling.** A model input is eligible only when its evidence and uncertainty are visible to the model runner.
10. **Log the decision.** Record material research decisions in the program research log.

## 3. Finding record requirements

Every engineering parameter record must conform to `specs/schemas/engineering-parameter.schema.json` and include:

- `value` and `unit`
- `source_id`
- `evidence_level`
- `value_class`
- `method`
- `status`
- `notes`

When a source supports multiple markets, years, or variants, the dataset must state the exact applicability of the extracted claim. If applicability cannot be established, the finding remains a candidate and the uncertainty is recorded.

## 4. Verification criteria

A finding may be marked `verified` only when:

- the source is registered and accessible to a reviewer;
- the cited locator resolves to the reported claim;
- model, market, year, and variant applicability have been checked;
- the unit and any conversion have been reviewed;
- the evidence level and value class match the provenance; and
- contradictions are either resolved with evidence or explicitly represented.

Evidence level A does not automatically mean a value applies to every market or generation. Evidence level B does not automatically mean a measurement is representative of factory production.

## 5. Derived values and assumptions

A derived value must identify its equation or transformation, input record identifiers, units, and rounding behavior. It uses evidence level F because it is not directly reported, even when all inputs are high-grade evidence.

An assumption must be labeled `value_class: assumption`, use evidence level F, explain why it is needed, define its allowed scope, and remain replaceable. Simulations must be able to reject assumptions when a strict evidence mode is selected.

## 6. Unknown and disputed data

Unknown parameters use `value: null`, `status: unknown`, `source_id: null`, and `evidence_level: UNKNOWN`. The unit may remain the expected unit when the parameter definition fixes it; otherwise it is `null`.

Disputed claims remain separate records. A dispute is not resolved by source count alone; applicability and independence must be examined.

## 7. Change discipline

- Research-foundation changes and research-data additions should be separate commits.
- A data commit should identify the source IDs added or used.
- Corrections must preserve an audit trail through version control and explain why the prior record changed.
- Simulation code must never rewrite research evidence.

## 8. Review checklist

- [ ] Source registered
- [ ] Stable locator recorded
- [ ] Applicability bounded by model/market/year/variant
- [ ] Original value and unit preserved
- [ ] Evidence level and value class assigned
- [ ] Unknowns remain null
- [ ] Conflicts preserved
- [ ] Derivation inputs and equation linked, if applicable
- [ ] No unstated fallback or plausible default introduced
