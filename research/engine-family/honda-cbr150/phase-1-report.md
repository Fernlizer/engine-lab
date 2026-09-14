# Honda CBR150 Engine Research — Phase 1 Working Report

Status: active research; first source and specification pass complete

## Executive finding

The accessible evidence supports at least four distinct catalog/model groups: CBR150RC, CBR150RF, CBR150RG/J/RK/RAK, and CBR150RM/RAM. A secondary authorized-dealer index calls the corresponding families KPP, K45A, K45G/K45N, and K45R, but those family aliases are not yet treated as universally verified Honda model codes.^1

The newest CBR150RM/RAM group is the current leading candidate for simulator v1 because official Honda parts catalogs and owner manuals are available across Indonesia, the Philippines, Vietnam, Thailand, and Malaysia. It is not yet the final recommendation: a factory service manual containing overhaul dimensions, tolerances, wear limits, and full torque specifications has not been located through an official public source.

## Evidence boundary

This report distinguishes three kinds of statements:

- **Verified observation:** transcribed from a registered Honda or official-distributor source with an exact locator.
- **Candidate mapping:** supported by a secondary source or by a document filename/catalog family label whose global meaning has not been proven.
- **Unknown:** not established by the sources reviewed so far.

Model years shown in a parts catalog identify catalog applicability, not necessarily launch dates or uninterrupted retail availability in every market.

## Source coverage

| Source group | Market | Document scope | Evidence | Engineering value |
|---|---|---|---|---|
| Honda parts catalog 18KPPB02 | Imported/Indonesia | CBR150RC, catalog dated 2011-05-20 | C | Part numbers, quantities, block structure, engine/frame serial applicability |
| Honda parts catalog 18K45FI1 | Indonesia | CBR150RF, catalog dated 2014-07-20 | C | Part numbers, quantities, engine/frame/throttle-body serial applicability |
| Honda parts catalog 18K45GI2 | Indonesia | CBR150RG, RJ, RK, RAK; 2016-2018 | A | Part numbers, quantities, standard/ABS applicability, engine/frame/throttle-body serial ranges |
| Honda parts catalog 18K45B1AJ | Indonesia | CBR150RM and CBR150RAM; catalog year 2020 | A | Part numbers, quantities, standard/ABS applicability, engine/frame/throttle-body serial ranges |
| Owner manual 32K45B000 | Philippines | CBR150R PH/III PH/V PH | A | Main dimensions, engine fundamentals, ratios, fluids, service data, selected torque values |
| Owner manual 32K45B100 | Philippines | CBR150R/CBR150RA IV PH | A | Main dimensions, engine fundamentals, ratios, fluids, service data, selected torque value |
| Owner manual 00X4F-K45-F000 | Vietnam | CBR150RA | A | Main dimensions, engine fundamentals, ratios, fluids, service data, selected torque value |
| Owner manual 32K45D200 | Thailand/Malaysia | CBR150RA destination codes TH/MA | A | Main dimensions, engine fundamentals, ratios, fuels, fluids, and service data |
| Current official product pages/brochure | Vietnam, Malaysia, Philippines | Current retail configuration; explicit model year often absent | A | Claimed output, induction/head/valve architecture, transmission and chassis summary |
| Thai Honda Parts Electronic Catalogue | Thailand | CBR150R model years 2004, 2011, 2016, 2017, 2019, 2020, 2021, 2025 | A | Exploded-view identity, Thai part description, reported quantity, and current price |

The four parts catalogs together contain hundreds of component records. Bulk reproduction has not yet been performed because the extraction needs an applicability-aware part schema and a review of catalog reuse/retention constraints.

The dynamic Thai Honda PEC is usable through its model-year and exploded-view interface. Machine-readable extractions now cover the 2021 E-1 cylinder-head-cover, E-2 cylinder-head, and E-3 camshaft/valve blocks. E-2 contains 24 returned part identities and 14 catalogue-reported size strings. Reference 20 remains unknown because selecting it did not yield a distinct live-list row. E-3 contains 73 unique part numbers, including 57 explicitly listed valve-shim thicknesses from 1.500 mm through 2.900 mm. Live prices are visible but are excluded from engineering parameters because they are commercial, time-variant values.^13

Part-number family segments must not be treated as exclusive vehicle applicability. For example, the Thai CBR150R 2021 E-1 selection returns both `90017-KGH-900` and `90017-KPP-900` for the cylinder-head-cover bolt. This establishes applicability in that catalog selection, but does not by itself establish which part supersedes the other or that all KGH- and KPP-family parts interchange.

## Model and serial map

### Evidence-backed catalog identities

| Catalog model | Catalog date/year | Engine serial applicability | Frame serial applicability | Throttle-body ID | Source status |
|---|---:|---|---|---|---|
| CBR150RC | 2011-05-20 | `KC17E-2000001~` | `MLHKC179*B55000001~` | `GQ1BA B` | Candidate: Honda catalog obtained from authorized-dealer mirror^2 |
| CBR150RF | 2014-07-20 | `KC71E0000001~` | `MH1KC71**EK000001~` | `GQ1HA A` | Candidate: Honda catalog obtained from authorized-dealer mirror^3 |
| CBR150RG | 2016 | `KC91E0000001~` | `MH1KC91**FK000001~` | `GQ1LA A` | Verified in official Honda catalog^4 |
| CBR150RJ | 2017/2018 catalog applicability | `KC91E0000001~`, then variant-specific ranges shown in catalog | `MH1KC91**HK000001~`, then variant-specific ranges | `GQ1LA A` | Verified in official Honda catalog; exact sub-range depends on area code^4 |
| CBR150RK | 2018 | `KC92E0000001~` | `MH1KC92**JK000001~` | `GQ1LA B` | Verified in official Honda catalog^4 |
| CBR150RAK | 2018 | `KC93E0000001~` | `MH1KC93**JK000001~` | `GQ1LA B` | Verified in official Honda catalog^4 |
| CBR150RM | 2020 catalog year | `KCB1E-0000001~` | `MH1KCB1**MK000001~` | `GQ13B A` | Verified in official Honda catalog^5 |
| CBR150RAM | 2020 catalog year | `KCC1E-0000001~` | `MH1KCC1**MK000001~` | `GQ13B A` | Verified in official Honda catalog^5 |

The letters embedded in catalog model names are preserved exactly. Their meaning has not been generalized beyond the explicit catalog rows.

### Working family aliases

| Alias | Current evidence state | Decision |
|---|---|---|
| KPP | Appears in Honda catalog number/part-number families and authorized-dealer index | Use as a search alias; do not yet treat as the formal engine code |
| K45A | Authorized-dealer index maps it to the 2014 catalog group | Candidate only |
| K45G | Authorized-dealer index maps it to the 2016 catalog group; official 2018 catalog title is `PC K45N` | Candidate boundary; catalog models are authoritative |
| K45N | Official 2018 PDF title is `PC K45N`; dealer index separates it from K45G beginning in 2018 | Candidate generation/sub-generation boundary |
| K45R | Official 2020 catalog PDF title is `PC_K45R`; dealer index maps it to January 2021 onward | Strong working alias, but retail-year range remains market-specific |

## Verified numeric engine and drivetrain observations

### Philippines manual comparison

| Parameter | 32K45B000, Philippines | 32K45B100, Philippines | Interpretation |
|---|---:|---:|---|
| Displacement | 149 cm³ | 149 cm³ | Same reported rounded displacement |
| Bore | 57.300 mm | 57.300 mm | Same |
| Stroke | 57.843 mm | 57.843 mm | Same |
| Compression ratio | 11.3:1 | 11.3:1 | Same |
| Minimum recommended fuel | 88 RON | 88 RON | Same market requirement |
| Tank capacity | 12.0 L | 12 L | Same reported capacity |
| Gear ratios 1-6 | 3.083 / 1.941 / 1.500 / 1.227 / 1.041 / 0.923 | Same | Same reported ratio set |
| Primary reduction | 3.260 | 3.260 | Same |
| Final reduction | 3.000 | 3.000 | Same |
| Cooling-system capacity | 0.58 L | 0.58 L | Same |
| Engine oil after draining | 1.1 L | 1.1 L | Same |
| Engine oil after disassembly | 1.3 L | 1.3 L | Same |
| Idle speed | 1,600 ± 100 rpm | 1,600 ± 100 rpm | Same |
| Spark-plug gap | 0.8-0.9 mm | 0.8-0.9 mm | Same |
| Drive-chain slack | 25-35 mm | 25-35 mm | Same |
| Drive-chain links | 128 | 128 | Same |
| Drive sprocket | 15 teeth | 15 teeth | Same |
| Driven sprocket | 45 teeth | 45 teeth | Same |

The 2016-source values are on printed pages 106-108; the 2021-source values are on printed pages 91-93.^6,7

### Selected market differences within the later manual group

| Parameter | Philippines 2021 | Vietnam 2021 | Thailand/Malaysia 2024 manual |
|---|---:|---:|---:|
| Wheelbase | 1,310 mm | 1,312 mm | 1,310 mm |
| Curb weight | 136 kg standard / 138 kg ABS | 139 kg | 137 kg |
| Maximum load | 121 kg | 161 kg | 151 kg Thailand / 161 kg Malaysia |
| Minimum recommended fuel | 88 RON | 88 RON | 91 RON |
| Permitted ethanol | up to 10% | up to 10% | up to 20% Thailand / 10% Malaysia |

These differences prove that market applicability must remain part of every record. They must not be averaged into one global specification.^7,8,9

### Claimed output differs by market/source snapshot

| Market/source | Claimed maximum power | Claimed maximum torque | Source limitation |
|---|---:|---:|---|
| Malaysia current product page | 12.0 kW at 9,000 rpm | 13.7 N·m at 7,000 rpm | Current page; explicit model year not shown |
| Philippines 2025 official material | 12.0 kW at 9,000 rpm | 13.7 N·m at 7,000 rpm | Current-generation marketing material |
| Vietnam current product page | 12.6 kW at 9,000 rpm | 14.4 N·m at 7,000 rpm | Current page; explicit model year not shown |

No normalization to horsepower or PS has been added. Any conversion will be a separate evidence-level F derived record.^10,11,12

## Selected verified service and component numbers

The Philippines 2021 owner manual reports:^7

- battery: GTZ6V or YTZ6V, 12 V, 5.0 Ah at 10-hour rate;
- front tyre: 100/80-17M/C 52P;
- rear tyre: 130/70-17M/C 62P;
- solo tyre pressure: 175 kPa front, 200 kPa rear;
- rider/passenger tyre pressure: 175 kPa front, 225 kPa rear;
- minimum tread depth: 1.5 mm front, 2.0 mm rear;
- spark plug: NGK MR9C-9N or DENSO U27EPR-N9;
- standard chain: FSCM428H or RK428HSE1, 128 links;
- cooling-system capacity: 0.58 L;
- main fuse: 20 A;
- other fuse: 10 A standard or 20 A and 10 A ABS; and
- seat mounting bolt torque: 10 N·m.

The earlier Philippines manual additionally publishes five selected chassis/service torque values:^6

- seat-lock cover bolts: 4.2 N·m;
- right middle-cowl bolts B: 4.2 N·m;
- engine-oil drain bolt: 24 N·m;
- rear axle nut: 68 N·m; and
- front axle nut: 59 N·m.

These are owner-maintenance values, not a complete engine overhaul torque table.

## Part-level research model

A parts catalog answers **what part number and quantity applies**, but usually does not answer **the physical dimensions, material, tolerance, or service limit**. Each component therefore needs separate linked records:

1. **Identity:** catalog block, reference number, part number, description, quantity, serial applicability, supersession.
2. **Factory specification:** nominal dimension, tolerance, material, mass, surface treatment, torque, clearance, or wear limit where published.
3. **Direct measurement:** specimen identity, instrument, calibration, repeated readings, temperature, wear state, and uncertainty.
4. **Derived geometry:** calculated area, volume, ratio, or mass property with equation and input links.
5. **Validation:** comparison between factory data, measured parts, and simulation inputs.

Numbers embedded in a part description, such as bolt dimensions or bearing designations, will be stored as reported attributes. They will not be expanded into assumed geometry unless the applicable naming standard is documented.

## Major engine-change investigation

The parts catalogs provide a defensible way to identify change candidates by comparing part-number sets for:

- cylinder head and cover;
- intake and exhaust camshafts;
- valves, springs, retainers, guides, and tappets/shims;
- cam chain, guides, tensioner, and sprockets;
- cylinder, piston, rings, pin, connecting rod, crankshaft, and balancer;
- crankcases and covers;
- clutch basket, plates, springs, lifter, and assist/slipper mechanism;
- transmission shafts and individual gears;
- oil pump and water pump;
- throttle body, injector, intake tract, and ECU-related parts; and
- generator, starter motor, and starter clutch.

A changed part number is evidence of a catalog change, not automatically proof of changed dimensions or performance. Shared part numbers are evidence of catalog interchangeability only within the catalog's stated applicability and revision.

## Data availability assessment

| Catalog group | Parts identity | Owner specs | Official market comparison | Overhaul tolerances | Dyno validation | Current confidence |
|---|---|---|---|---|---|---|
| CBR150RC / KPP working alias | Available through dealer mirror | Secondary service-manual leads exist | Sparse | Secondary mirror lead only | Not collected | Low |
| CBR150RF / K45A working alias | Available through dealer mirror | Not yet located from official origin | Sparse | Unknown | Not collected | Low |
| CBR150RG/J/RK/RAK | Official catalog available | Official Philippines manual available | Partial | Unknown | Not collected | Medium |
| CBR150RM/RAM / K45R working alias | Official catalog available | Official manuals across four markets | Strong | Unknown | Not collected | Highest current coverage |

## Provisional simulator-v1 recommendation

Use the CBR150RM/RAM catalog group as the **provisional research target**, not yet as a locked simulator reference engine. It currently has the strongest combination of official part identity, engine/frame serial mapping, owner-level specifications, and cross-market evidence.

The recommendation becomes final only if one of these conditions is met:

- an applicable factory service manual supplies the missing internal dimensions and service limits; or
- a documented direct-measurement program fills the minimum simulator input set with level B evidence.

## Blocking evidence and requested help

The highest-value missing sources are factory service/workshop manuals for:

1. CBR150RC / KPP-era catalog group;
2. CBR150RF / 2014 Indonesia catalog group;
3. CBR150RG/J/RK/RAK / 2016-2018 group; and
4. CBR150RM/RAM / current group.

For each manual, the identifying cover, publication number, revision date, applicable model codes, and market are required. A manual with no cover or applicability page cannot support verified values safely.

## Next extraction batches

1. Extract the Thai 2021 E-4 cam-chain/tensioner block, then continue the remaining engine blocks.
2. Normalize reviewed catalog extractions into applicability-aware part records.
3. Compare 2020 and 2025 Thai blocks and diff part numbers without inferring dimensional or performance changes.
4. Extract the official Indonesia catalog groups in this order: 2020, 2018, then the dealer-hosted 2014 and 2011 catalogs.
5. Acquire applicable service manuals and extract nominal values, tolerances, clearances, wear limits, and complete torque tables.
6. Add independent dyno sources and define direct-measurement protocols for values absent from factory publications.

## Sources

1. Honda Cengkareng. “[Katalog Suku Cadang Motor Honda](https://www.hondacengkareng.com/katalog-suku-cadang-motor-honda/).” Authorized-dealer catalog index, accessed 2026-09-14.
2. Honda Motor Co., Ltd. “[CBR150R Parts Catalog 18KPPB02](https://www.hondacengkareng.com/wp-content/uploads/2016/02/Katalog-Suku-Cadang-Honda-CBR-150R-CBU.pdf).” Edition 1, 2011-05-20, authorized-dealer mirror, pp. 6-7.
3. Honda Motor Co., Ltd. “[CBR150RF Parts Catalog 18K45FI1](https://www.hondacengkareng.com/wp-content/uploads/2016/02/Katalog-Suku-Cadang-CBR-150R.pdf).” Edition 1, 2014-07-20, authorized-dealer mirror, printed p. 7.
4. Honda Motor Co., Ltd. “[CBR150R/CBR150RA Parts Catalog 18K45GI2](https://2rom-prd-data.hondamotopub.com/pc/AHJ/CBR150R/2018/PC_CBR150R.pdf).” Revision 2, 2018-08-20, printed p. 7.
5. Honda Motor Co., Ltd. “[CBR150R/CBR150RA Parts Catalog 18K45B1AJ](https://2rom-prd-data.hondamotopub.com/pc/AHJ/CBR150R/2021/PC_CBR150R_%282021%29.pdf).” Revision 1, 2020-10-20, printed p. 7.
6. Honda Motor Co., Ltd. “[CBR150R Owner's Manual 32K45B000_eng](https://2rom-prd-data.hondamotopub.com/om/HPI/CBR150R/2018/CBR150R_32K45B000_1.pdf).” Copyright 2016, printed pp. 106-108.
7. Honda Motor Co., Ltd. “[CBR150R/CBR150RA Owner's Manual 32K45B100_eng](https://2rom-prd-data.hondamotopub.com/om/HPI/CBR150R/2021/CBR150R_32K45B1XX_0.pdf).” Copyright 2020, PDF created 2021-04-09, printed pp. 91-93.
8. Honda Motor Co., Ltd. “[CBR150RA Vietnamese Owner's Manual 00X4F-K45-F000](https://cdn.honda.com.vn/motorbike-manual/October2021/EbMj0ueSu11yfSVPShcP.pdf).” 2021, printed pp. 92-94.
9. Honda Motor Co., Ltd. “[CBR150RA Owner's Manual 32K45D200_eng](https://boonsiewhonda.com.my/wp-content/uploads/2026/04/CBR150R-Owner_s-Manual-K45X.pdf).” Copyright 2024, printed pp. 90-92.
10. Boon Siew Honda. “[Honda CBR150R Product Page](https://boonsiewhonda.com.my/product/honda-cbr150r/).” Accessed 2026-09-14.
11. Honda Philippines, Inc. “[The New CBR150R Specification Brochure](https://cms.hondaph.com/files/products/683d082df0072.pdf).” Accessed through manufacturer-indexed content 2026-09-14.
12. Honda Vietnam. “[CBR150R Product Comparison Specification](https://www.honda.com.vn/xe-may/so-sanh?category=3&sp=%5B%22cbr150r%22%5D&version=61).” Accessed 2026-09-14.
13. Thai Honda Co., Ltd. “[Honda Parts Electronic Catalogue](https://pec.thaihonda.co.th/Applications/Common/Programs/StartApp.aspx).” CBR150R model year 2021, E-1 cylinder-head-cover live view, accessed 2026-09-14.
