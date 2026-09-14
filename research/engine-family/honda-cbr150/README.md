# Honda CBR150 Engine Research — Phase 1

Status: active; first official-source pass complete

## Purpose

Phase 1 is building an evidence-backed map of the Honda CBR150 engine family and will select one reference engine for simulator v1. The first source pass is documented in [`phase-1-report.md`](phase-1-report.md); machine-readable observations are stored under `data/engines/honda-cbr150/`.

## Objectives

- identify all major engine generations;
- identify important market differences;
- map engine and model codes where reliable;
- map bore × stroke;
- map compression ratio;
- map induction system;
- map cylinder-head architecture and valve count;
- map gearbox configuration;
- map claimed power and torque;
- identify major internal engine changes;
- identify the generation with the best available engineering data; and
- recommend one reference engine for simulator v1.

## Deliverables

1. A source registry populated with traceable primary and supporting evidence.
2. A catalog-group and market matrix in `family-map.md`.
3. Parameter records conforming to the engineering-parameter schema.
4. A contradiction and gap register in `open-questions.md`.
5. A scored reference-engine recommendation based on evidence availability, not preference.

## Completion gate

Phase 1 is complete only when the generation boundaries and recommended reference engine are supported by cited evidence, key conflicts are explicit, and missing values remain marked unknown. The CBR150RM/RAM group is currently only a provisional research target. Simulator implementation is out of scope for Phase 1.
