# Unknown Data Policy

Unknown is a valid research result, not an error to conceal.

## Required representation

Use this shape when a parameter is not currently known:

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

The unit may be retained when the parameter definition requires a fixed unit. Otherwise use `unit: null`.

## Prohibited behavior

- Do not use zero, an empty string, a midpoint, a value from another generation, or a common industry value to mean unknown.
- Do not copy a value across markets, years, model codes, or variants without applicability evidence.
- Do not let serializers, forms, databases, equations, or visualizations replace nulls with defaults.
- Do not silently exclude unknown inputs from calculations when their absence changes the result.
- Do not label an estimate as a measurement or factory specification.

## Model behavior

Simulation-core must fail with a specific missing-input result when a required parameter is unknown. If an explicit assumption mode is added later, it must expose the assumed record and must not mutate the research dataset.

## Resolving an unknown

Replace an unknown only through a reviewable data change containing a registered source or a documented direct measurement. The new record must meet Research Standard v0.1.
