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
