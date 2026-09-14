# Honda CBR150 Family Map

Status: working map; catalog identities verified where noted, generation boundaries unresolved

This map uses catalog model identities as the stable starting point. KPP/K45 aliases remain search labels until Honda documentation proves their exact scope. See [`phase-1-report.md`](phase-1-report.md) for locators, limitations, and full sources.

## Generation inventory

| Research ID | Generation label | Model code | Engine code | Market | Model years | Boundary evidence | Status |
|---|---|---|---|---|---|---|---|
| CBR150-CATALOG-RC | CBR150RC catalog group | CBR150RC | KC17E serial prefix; formal engine code UNKNOWN | Imported/Indonesia | Catalog dated 2011 | Honda-authored catalog on authorized-dealer mirror | candidate |
| CBR150-CATALOG-RF | CBR150RF catalog group | CBR150RF | KC71E serial prefix; formal engine code UNKNOWN | Indonesia | Catalog dated 2014 | Honda-authored catalog on authorized-dealer mirror | candidate |
| CBR150-CATALOG-RG-RJ | CBR150RG/RJ catalog group | CBR150RG, CBR150RJ | KC91E serial prefix; formal engine code UNKNOWN | Indonesia | 2016-2017/18 catalog applicability | Honda MotoPub catalog 18K45GI2 | verified identity |
| CBR150-CATALOG-RK-RAK | CBR150RK/RAK catalog group | CBR150RK, CBR150RAK | KC92E/KC93E serial prefixes; formal engine code UNKNOWN | Indonesia | 2018 catalog applicability | Honda MotoPub catalog 18K45GI2 | verified identity |
| CBR150-CATALOG-RM-RAM | CBR150RM/RAM catalog group | CBR150RM, CBR150RAM | KCB1E/KCC1E serial prefixes; formal engine code UNKNOWN | Indonesia; related owner evidence from PH/VN/TH/MY | Catalog dated 2020; later manuals | Honda MotoPub catalog 18K45B1AJ plus market manuals | verified catalog identity; cross-market mapping candidate |

These rows prove catalog identities, not yet the final mechanical generation boundaries. A serial prefix is not promoted to a formal engine code without explicit source wording.

## Per-generation parameter matrix

Create one evidence-linked record per claim rather than compressing conflicts into a single cell.

| Research ID | Bore × stroke | Compression ratio | Induction | Head architecture | Valves | Gearbox | Claimed power | Claimed torque | Internal changes |
|---|---|---|---|---|---|---|---|---|---|
| CBR150-CATALOG-RC | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN |
| CBR150-CATALOG-RF | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN | UNKNOWN |
| CBR150-CATALOG-RG-RJ | 57.300 × 57.843 mm in applicable PH owner manual; Indonesia mapping candidate | 11.3:1 in PH manual | PGM-FI stated | DOHC stated | 4 stated | 6 ratios published | Market/year-specific; not globally normalized | Market/year-specific; not globally normalized | Parts diff pending |
| CBR150-CATALOG-RK-RAK | 57.300 × 57.843 mm in applicable PH owner manual; Indonesia mapping candidate | 11.3:1 in PH manual | PGM-FI stated | DOHC stated | 4 stated | 6 ratios published | Market/year-specific; not globally normalized | Market/year-specific; not globally normalized | Parts diff pending |
| CBR150-CATALOG-RM-RAM | 57.300 × 57.843 mm in PH manual | 11.3:1 | PGM-FI stated | DOHC stated | 4 stated | 6 ratios published | 12.0 or 12.6 kW depending on current market source | 13.7 or 14.4 N.m depending on current market source | Parts diff and service-manual proof pending |

## Reference-engine selection rubric

The recommendation must be scored only after evidence collection. Record evidence for each criterion:

- coverage of required simulator inputs;
- proportion of level A and B evidence;
- market/year/model-code specificity;
- availability of reproducible measurements;
- availability of factory or reputable validation targets;
- unresolved contradictions; and
- accessibility and lawful retention of source material.

Current result: CBR150RM/RAM is the provisional research target because it has the widest official document coverage. No simulator reference engine is locked until internal dimensions, tolerances, and service limits are available.
