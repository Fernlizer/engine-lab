# CBR150RK 2021 Catalog Cross-check — E-1 to E-3

Date: 2026-09-14  
Status: working comparison; not a compatibility determination

## Scope

This compares the public secondary-source CBR150RK 2021 catalog extraction (`SRC-HONDA-BIKE-PARTS-TH-CBR150RK-2021`, evidence level C) with the previously transcribed Thai Honda PEC datasets (`SRC-HONDA-THA-PEC-CBR150R-2021-2026`, evidence level A).

Rows are matched by the pair `(reference_number, part_number)`. Punctuation-only part-number differences are reported, not silently normalized. The public catalog provides no established bill-of-material quantity in the observed product rows, so all candidate quantities remain `null` and cannot validate PEC quantities.

## Results

| Block | PEC rows | Secondary rows | Exact ref + part matches | Finding |
| --- | ---: | ---: | ---: | --- |
| E-1 | 5 | 4 | 4 | Secondary source omits PEC alternative `90017-KPP-900` at reference 3. |
| E-2 | 24 | 25 | 20 | Reference 5 differs (`17111-K15-921` PEC vs `17111-K15-920` secondary); references 19, 21, and 22 differ only in dash formatting; secondary source supplies `94301-10120` at reference 20 where PEC extraction remains unresolved. |
| E-3 | 73 | 73 | 72 | Reference 11 differs (`14771-K45-NL0` PEC vs `14771-MFL-000` secondary). |

## Interpretation boundary

- An exact match supports catalog-identity agreement between the two observations; it does not establish dimensions, material, interchangeability, or cross-model compatibility.
- A different part number is a source conflict or applicability difference until catalog revision, serial range, and model-code scope are reconciled.
- The secondary reference-20 observation is candidate evidence only and does not resolve the Thai Honda PEC record to level A.
- Alternative rows are preserved independently; no supersession direction is inferred.

## Next checks

1. Re-open PEC E-2 reference 20 and capture the returned list row or an explicit absence.
2. Record catalog revision and serial/VIN applicability for both sources if exposed.
3. Re-check E-2 reference 5 and E-3 reference 11 in an official parts catalog applicable to the exact Thai model code.
4. Cross-check E-4 onward against PEC before promoting any candidate record.
