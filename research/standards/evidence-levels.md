# Evidence Levels

Evidence levels describe where a claim came from. They do not replace applicability checks or validation.

| Level | Definition | Typical examples | Required caution |
|---|---|---|---|
| A | Honda/OEM primary source | Owner/service manual, homologation document, official specification, OEM parts catalog | Confirm market, year, model code, revision, and document authenticity. |
| B | Direct physical measurement | Dimension, mass, volume, or test result measured from an identified part or engine | Record instrument, method, calibration, conditions, sample identity, and uncertainty. |
| C | Reputable technical source, component manufacturer, or dyno facility | Published technical data or a traceable test report | Record test setup and distinguish measured results from copied factory claims. |
| D | Multiple independent observations | Independently produced observations that agree and can be traced separately | Verify independence; repetition of one upstream claim is not corroboration. |
| E | Single community source | Forum post, owner report, video, or unverified listing | Treat as a lead or candidate, not a verified engineering value by itself. |
| F | Derived or estimated | Calculation, interpolation, estimate, or explicit assumption | Link inputs and method; never present as directly measured or factory-issued. |
| UNKNOWN | Not currently known | No admissible value is available | Store `value: null`; do not substitute a plausible value. |

## Precedence

Higher-grade evidence is not automatically applicable or correct. Prefer the claim with the strongest combination of provenance, exact applicability, traceable method, and reproducibility. Preserve unresolved conflicts.

## Direct measurements

Level B records should include, when applicable:

- engine, vehicle, and part identifiers;
- instrument make/model and resolution;
- calibration status;
- environmental and operating conditions;
- procedure and repeated observations;
- measurement uncertainty; and
- whether the part may be worn, modified, or replaced.
