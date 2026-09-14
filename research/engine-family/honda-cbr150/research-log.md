# Honda CBR150 Phase 1 Research Log

Use one entry per research session or material decision. Do not place unsupported specifications in the log.

## Entry template

### YYYY-MM-DD — Short title

- Researcher:
- Question:
- Sources added or reviewed:
- Findings:
- Conflicts:
- Unknowns:
- Decisions:
- Follow-up:

## 2026-09-14 — Research foundation initialized

- Researcher: repository initialization
- Question: What structure and controls are required before CBR150 research begins?
- Sources added or reviewed: none
- Findings: none
- Conflicts: none recorded
- Unknowns: all CBR150 generation, market, code, and engineering parameters
- Decisions: adopt Research Standard v0.1 and machine-readable parameter/source schemas
- Follow-up: begin source discovery with market-specific Honda/OEM documents

## 2026-09-14 — First Honda/OEM source pass

- Researcher: Codex
- Question: Which CBR150 catalog groups, market variants, and first simulator-relevant values can be established without relying on memory?
- Sources added or reviewed: 12 registered sources, including four parts catalogs, four owner manuals, two official product pages, one official brochure lead, and one authorized-dealer catalog index
- Findings: catalog identities CBR150RC, RF, RG/RJ/RK/RAK, and RM/RAM; first factory engine, drivetrain, fluid, service, torque, and market-specific observations recorded
- Conflicts: current official claimed output differs between Malaysia/Philippines and Vietnam; chassis/fuel limits also differ by market
- Unknowns: formal engine-code terminology, final mechanical generation boundaries, most internal dimensions/materials/tolerances/clearances/wear limits, and complete overhaul torque tables
- Decisions: keep market observations separate; retain KPP/K45 labels only as working aliases; use RM/RAM as a provisional research target, not a final simulator selection
- Follow-up: extract applicability-aware engine-part identities, acquire applicable factory service manuals, then compare part-number changes without inferring dimensional changes

## 2026-09-14 — Thai Honda PEC access test

- Researcher: Codex
- Question: Can the dynamic Thai-market Honda Parts Electronic Catalogue support reproducible part research?
- Sources added or reviewed: official Thai Honda PEC, CBR150R model-year selector and 2021 E-1 cylinder-head-cover view
- Findings: the interface exposes CBR150R years 2004, 2011, 2016, 2017, 2019, 2020, 2021, and 2025; exploded-view blocks expose part number, Thai description, quantity, and live unit price
- Conflicts: none established in E-1; PEC returned both 90017-KGH-900 and 90017-KPP-900 as applicable shared/alternative parts, but did not explain their supersession or substitution direction
- Unknowns: stable deep links, catalog revision identifier, engine/frame serial filters for non-VIN browsing, and whether all returned alternatives are simultaneously applicable
- Decisions: register PEC as market-specific level A evidence; store part identity and quantity, exclude volatile price from engineering parameters, and treat both displayed bolt numbers as verified applicability without inventing a supersession relationship
- Follow-up: extract all engine blocks year by year and cross-check part-number changes against official catalogs and service manuals

## 2026-09-14 — Thai CBR150R 2021 cylinder-head extraction

- Researcher: Codex
- Question: What part identities and catalogue-reported numeric sizes are exposed by the Thai-market 2021 E-2 cylinder-head block?
- Sources added or reviewed: Thai Honda PEC E-2 exploded view and live part list; Indonesia Honda catalogue 18K45B1AJ used only for cross-market comparison
- Findings: 24 Thai-market E-2 part identities recorded; 14 records contain catalogue-reported size strings; Thai intake pipe 17111-K15-921 differs from Indonesia 17111-K15-920
- Conflicts: no engineering incompatibility inferred from the intake-pipe part-number difference
- Unknowns: E-2 reference 20 did not produce a distinct live-list row; its Thai part identity remains unknown
- Decisions: preserve size strings without assigning dimensional axes; exclude prices; do not copy the Indonesian reference-20 part into Thai applicability
- Follow-up: extract E-3 camshaft/valve and E-4 cam-chain/tensioner, then compare 2020 and 2025

## 2026-09-14 — Thai CBR150R 2021 camshaft/valve extraction

- Researcher: Codex
- Question: Which part identities and explicitly reported engineering values are exposed by the Thai-market 2021 E-3 camshaft/valve block?
- Sources added or reviewed: Thai Honda PEC E-3 exploded view and live part list
- Findings: 73 unique part numbers recorded: 16 ordinary rows plus 57 valve-shim variants; shim thicknesses run from 1.500 mm through 2.900 mm in observed 0.025 mm increments
- Conflicts: PEC returns two alternatives each for valve-stem seals, outer valve springs, and inner valve springs without declaring substitution or supersession direction
- Unknowns: cam profiles, lift, duration, journal dimensions, valve dimensions, spring free lengths/rates, materials, tolerances, masses, and wear limits
- Decisions: retain every shim mapping explicitly; share catalog-level provenance in an extraction envelope; exclude live prices; do not infer compatibility from K45, K56, KT7, or ML0 part-number segments
- Follow-up: extract E-4 cam-chain/tensioner, normalize E-3 records, and seek the applicable factory service manual for physical specifications

## 2026-09-14 — Public CBR150RK catalog candidate extraction

- Researcher: Codex
- Question: Can the public secondary catalog provide a bounded, reproducible candidate inventory for all CBR150RK 2021 engine blocks without filling missing fields?
- Sources added or reviewed: public `honda.bike-parts.co.th` CBR150RK 2021 model page and all 18 catalog URLs whose paths contain an E-series block identifier
- Findings: 18 engine blocks produced 352 positional rows representing 327 distinct part numbers; all 352 references were observed; 228 descriptions contain one or more numeric strings; 17 part numbers occur more than once and were intentionally not deduplicated
- Conflicts: E-1 through E-3 comparison with PEC found one omitted alternative, two substantive part-number differences, three dash-format differences, and one secondary-only candidate for an unresolved PEC reference
- Unknowns: catalog quantity for every secondary row, exact catalog revision, serial/VIN applicability, operator/manufacturer attribution for the public site, and engineering meaning of numeric strings embedded in descriptions
- Decisions: grade the source C; keep every quantity `null`; derive block ID only from the catalog URL; preserve alternatives and repeated positions; exclude retail price; do not parse description numbers into engineering parameters until their meaning and unit can be established
- Follow-up: cross-check E-4 onward in Thai Honda PEC, then normalize only verified records and explicitly reported dimensions into part records

## 2026-09-14 — Reproducible Thai Honda PEC E-4 extraction

- Researcher: Codex
- Question: Can the public PEC workflow be reproduced without coordinate-based hotspot clicking, and does its E-4 assembly agree with the secondary catalog?
- Sources added or reviewed: 12 reference-specific ASP.NET responses from Thai Honda PEC E-4 and the secondary CBR150RK E-4 candidate dataset
- Findings: PEC returned 12 part rows with explicit quantities; nine part numbers match the secondary source exactly and three match after a punctuation-only dash difference; the cam chain description explicitly reports 120 links and five fastener/O-ring descriptions report size strings
- Conflicts: no substantive part-number conflict established for this assembly; punctuation is preserved exactly in each source record
- Unknowns: model code, serial/VIN range, chain pitch, dimensional-axis conventions, thread pitch, materials, tolerances, and supersession relationships
- Decisions: store automated PEC responses as a candidate transcript with one SHA-256 per reference; promote the human-reviewed identities and quantities to verified part records; preserve reported numeric strings without inferring axes; identify block numbers as source-local locators
- Follow-up: extract PEC E-5, determine content-based mapping after PEC E-6, and cross-check each assembly before normalization

## 2026-09-14 — Thai Honda PEC E-5 cylinder extraction

- Researcher: Codex
- Question: Does the PEC E-5 cylinder assembly agree with the secondary E-5 candidate and what numeric information is explicit?
- Sources added or reviewed: three reference-specific Thai Honda PEC E-5 responses and secondary CBR150RK E-5
- Findings: all three reference/part-number pairs agree exactly; PEC establishes quantities of one cylinder, one cylinder gasket, and two dowel pins; the dowel-pin description reports `10x12`
- Conflicts: none observed in the compared identities
- Unknowns: cylinder bore and geometry, liner and deck dimensions, gasket thickness, dowel dimensional axes, materials, tolerances, and wear limits
- Decisions: verify PEC identities and quantities; preserve `10x12 mm` as a reported size string without assigning axes
- Follow-up: extract PEC E-6, then establish the first shifted block mapping by assembly contents

## 2026-09-14 — Thai Honda PEC E-6 right-crankcase-cover extraction

- Researcher: Codex
- Question: Does PEC E-6 align with the secondary right-crankcase-cover assembly and which catalog values can be verified?
- Sources added or reviewed: 19 reference-specific Thai Honda PEC E-6 responses and secondary CBR150RK E-6
- Findings: 16 exact reference/part-number matches and two punctuation-only differences; PEC establishes all 19 quantities and reports ten size strings in part descriptions
- Conflicts: reference 6 is `11394-K56-V50` in PEC and `11394-K56-N00` in the secondary catalog
- Unknowns: catalog revision/serial applicability behind the gasket conflict, all dimensional-axis conventions, thread pitches, materials, tolerances, and seal specifications beyond the reported strings
- Decisions: use the PEC part identity for the Thai verified record; retain the secondary identity as a conflict; infer no supersession; preserve ten size strings as factory-reported values without assigning axes
- Follow-up: inspect PEC E-7 contents and map it to the correct secondary assembly before row-level comparison

## 2026-09-14 — Content-based PEC E-7 clutch mapping

- Researcher: Codex
- Question: Which secondary assembly corresponds to PEC E-7 when block numbers are explicitly ignored?
- Sources added or reviewed: 18 reference-specific PEC E-7 responses producing 20 rows, plus every secondary engine-category candidate for CBR150RK 2021
- Findings: part descriptions identify PEC E-7 as clutch; secondary E-8 is the only candidate with shared contents, including ten shared part numbers; PEC reports 23 teeth for three primary-drive-gear alternatives, five explicit millimetre size strings, all quantities, and bearing designation 6903
- Conflicts: PEC uses several K45-NL1 identities and one clutch-plate kit while the secondary source uses K56-Nxx identities and individually listed plates; only one shared part remains at the same reference number because the list structure shifts
- Unknowns: exact model code/serial range behind the Thai PEC 2021 selection, compatibility between K45-NL1 and K56-Nxx components, plate count and dimensions inside the PEC kit, bearing dimensions encoded by 6903, materials, masses, spring rates, and tolerances
- Decisions: map PEC E-7 to secondary E-8 at assembly level only; verify PEC rows for the Thai PEC selection; do not claim model-code equivalence, interchangeability, or supersession
- Follow-up: obtain model-code/serial applicability evidence and map PEC E-8 by contents before comparing its rows
