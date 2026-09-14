# CBR150RK 2021 Catalog Cross-check — First Four Assemblies

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
| PEC E-4 / secondary E-4 | 12 | 12 | 9 | All three non-exact pairs are punctuation-only forms at references 10–12; removing the final separator yields the same character sequence. Quantities are established only by PEC. |
| PEC E-5 / secondary E-5 | 3 | 3 | 3 | Exact reference and part-number agreement for every row. Quantities are established only by PEC. |
| PEC E-6 / secondary E-6 | 19 | 19 | 16 | References 18–19 differ only in dash formatting. Reference 6 conflicts: PEC `11394-K56-V50`; secondary `11394-K56-N00`. |

## Source-specific block numbering

The Thai Honda PEC 2021 page exposes 18 engine images numbered continuously E-1 through E-18. The secondary catalog exposes 18 engine categories but uses E-1, E-2, E-3, E-4, E-5, E-6, E-8 through E-17, E-19, and E-23. Therefore block number is a source-local locator, not a cross-source assembly identifier. E-4 was compared only after its cam-chain/tensioner contents aligned; later assemblies must be paired by source title and part content before comparing rows.

## Interpretation boundary

- An exact match supports catalog-identity agreement between the two observations; it does not establish dimensions, material, interchangeability, or cross-model compatibility.
- A different part number is a source conflict or applicability difference until catalog revision, serial range, and model-code scope are reconciled.
- The secondary reference-20 observation is candidate evidence only and does not resolve the Thai Honda PEC record to level A.
- Alternative rows are preserved independently; no supersession direction is inferred.

## Next checks

1. Re-open PEC E-2 reference 20 and capture the returned list row or an explicit absence.
2. Record catalog revision and serial/VIN applicability for both sources if exposed.
3. Re-check E-2 reference 5 and E-3 reference 11 in an official parts catalog applicable to the exact Thai model code.
4. Pair PEC E-6 onward to the secondary categories by assembly content before comparing part rows.
5. Resolve the E-6 reference-6 gasket conflict using catalog revision/serial applicability; do not infer supersession from the suffix.
