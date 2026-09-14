# Engine Lab

Engine Lab is an evidence-first engine research and simulation platform. Its first research program is the Honda CBR150 engine family, while the data contracts and simulation boundary are designed to remain engine-agnostic.

## Governing sequence

```text
Evidence -> Dataset -> Mathematical Model -> Validation -> Simulation -> 3D / Web UI
```

Work must move through these stages in order. A downstream artifact must not turn an unknown upstream value into a plausible-looking fact.

## Non-negotiable rules

- Never invent engineering values.
- Store unknown values as `null` with `status: unknown` and `evidence_level: UNKNOWN`.
- Attach provenance to every important numeric engineering value.
- Classify values as factory, direct measurement, secondary source, derived, or assumption.
- Keep derived values and assumptions visibly distinct from observed facts.
- Add tests for every simulation equation before it is accepted into simulation-core.
- Keep simulation-core independent from presentation, web, and 3D code.
- Do not silently replace missing data with defaults or estimates.

## Repository map

- `research/` — research rules, program plans, logs, and open questions
- `sources/` — source metadata and locally retained evidence
- `data/` — normalized engine, part, measurement, and validation datasets
- `models/` — reviewed equations and explicit assumptions
- `validation/` — comparisons against factory, dyno, measurement, and road-test evidence
- `specs/` — data contracts and simulator scope

The active program is [Honda CBR150 Engine Research — Phase 1](research/engine-family/honda-cbr150/README.md). No Honda CBR150 engineering specifications are asserted in this initialization commit.

## Start here

1. Read [Research Standard v0.1](research/standards/research-standard.md).
2. Register a source in [`sources.yaml`](sources/registry/sources.yaml).
3. Record findings with the parameter envelope defined in [Data Schema](specs/data-schema.md).
4. Preserve contradictions and unknowns; do not resolve them without evidence.
5. Validate a candidate reference engine before implementing simulator equations.

## Current status

Repository foundation only. Research data collection, model selection, simulation-core, web UI, and 3D work have not started.
