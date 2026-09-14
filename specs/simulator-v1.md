# Simulator v1 Specification — Draft 0.1

Status: research-gated; implementation not started

## Purpose

Simulator v1 will provide a deterministic, testable engine calculation core for one evidence-selected reference engine. Selection is deferred until Honda CBR150 Phase 1 is complete.

## Boundaries

In scope later:

- a UI-independent simulation-core;
- typed, unit-aware inputs loaded from versioned datasets;
- explicit propagation of evidence and assumption metadata;
- deterministic equations with documented domains and tests;
- validation reports against registered evidence; and
- structured missing-input and out-of-domain results.

Out of scope now:

- web UI;
- 3D viewer or geometry rendering;
- real-time ECU, control, combustion, CFD, or finite-element claims;
- performance predictions without a defined mathematical model and validation target; and
- implicit estimates for missing inputs.

## Reference-engine gate

The reference engine is `UNKNOWN`. It may be selected only after the Phase 1 rubric in `research/engine-family/honda-cbr150/family-map.md` is completed with cited evidence.

## Future model contract

Each equation must define:

- equation ID, version, source, and derivation;
- input parameters, units, allowed ranges, and required evidence policy;
- output parameters and units;
- assumptions and omitted effects;
- numerical method and precision/rounding behavior;
- failure behavior for null, invalid, or out-of-domain inputs;
- unit tests using analytically checkable cases; and
- validation cases against independent evidence.

## Missing-data behavior

Required unknown inputs stop the affected calculation with a named missing-input result. Optional assumption mode, if implemented later, must be explicit in the invocation and output and must never alter the source dataset.

## Validation gate

A simulation result must identify the dataset version, equation versions, input provenance, assumptions, and validation status. Passing unit tests proves implementation consistency, not physical accuracy; physical claims require separate validation evidence.
