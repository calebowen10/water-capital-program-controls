# HWSD — Approved Synthetic Baseline: CPM & Final QA

**Status: PASS for integrated CPM under the documented baseline and milestone constraint conventions.** No approved project finish dates changed. The source-explicit P08 outage event requires an independent fixed-date constraint; its zero float is not a driving construction path.

## Files and version provenance

- Input: previously integrated `HWSD_Project_Controls_Model_Baseline.xlsx` and approved `schedule_activities_final.csv` / `schedule_relationships_final.csv`.
- Output: `HWSD_Project_Controls_Model_Baseline_CPM.xlsx`, `schedule_activities_baseline_CPM.csv`, `schedule_relationships_baseline_CPM.csv`.
- Historical reconciliation (`schedule_reconciliation_final.csv`) and twelve existing resource assumptions (`resource_assumptions_final.csv`) remain unchanged. No original uploaded master file or GitHub repo was modified.

## Approved NTP release holds

| Project | Relationship | Additional business-day release hold |
|---|---|---:|
| P04 | R0133, Governing Approval → NTP | 15 |
| P05 | R0161, Governing Approval → NTP | 5 |
| P07 | R0260, Governing Approval → NTP | 10 |
| P08 | R0291, Governing Approval → NTP | 10 |
| P11 | R0434, Governing Approval → NTP | 5 |

The lag is an explicitly **user-approved synthetic owner release hold**, not recovered original schedule data. Each of the five relationship records contains this provenance. The lag is FS on the predecessor-finish-to-zero-duration-milestone convention.

## CPM conventions

- Calendar: Monday–Friday; no holidays. Each positive-duration task has an **inclusive** working-day span. Milestones have duration zero.
- FS+0 to a task = next business day after predecessor finish; FS+0 to a milestone = predecessor finish date. SS uses start-to-start business-day lag. FF uses finish-to-finish business-day lag.
- Early dates: full 428-node / 498-edge directed acyclic network forward pass, using approved project start anchors and incoming cross-project interfaces.
- Late dates: reverse pass using **each project’s approved finish as its own deadline**; cross-project constraints remain in the shared network. Total float is Late Start − Early Start in business days. Float therefore must not be interpreted as a common program-end float.
- `Critical_Flag = TRUE` for Total Float = 0bd; near-critical = 1–5bd. No negative float. These values are an externally calculated, frozen CPM baseline snapshot within the workbook, not self-recalculating Excel formulas.
- **P08-MOUTAGE:** separately approved dated event retained at **2026-05-22** as an explicit fixed-date milestone; its recorded planning activity A14 ends 2026-05-08. The original records do not explain the 10bd gap. The event was date-constrained, not assigned another synthetic causal lag. Its zero-float classification is constraint-driven and must not be interpreted as a governing construction path. Its project finish remains 2027-01-08.

## All twelve project finishes and CPM results

| Project | Approved finish | Calculated finish | Critical rows | Near-critical rows | Representative tight critical sequence (activity IDs) |
|---|---|---|---:|---:|---|
| P01 | 2025-12-29 | 2025-12-29 | 19 | 0 | P01-A1 → P01-A2 → P01-A3 → P01-A4 → P01-A5 → P01-A5b → P01-M2 → P01-A7a → P01-A7b → P01-A7c → P01-A8 → P01-A11 → P01-A12 → P01-A10 → P01-A15 → P01-M3 → P01-A13 → P01-A14 → P01-M4 |
| P02 | 2026-02-25 | 2026-02-25 | 17 | 1 | P02-A1 → P02-A2 → P02-A3 → P02-A4 → P02-A5 → P02-A5b → P02-M2 → P02-A7a → P02-A7b → P02-A7c → P02-A7d → P02-A10 → P02-A14 → P02-A15 → P02-A16 → P02-A17 → P02-M5 |
| P03 | 2027-01-27 | 2027-01-27 | 26 | 0 | P03-A1 → P03-A2 → P03-A2b → P03-A3 → P03-A4 → P03-A5 → P03-A6 → P03-A7 → P03-A8 → P03-A9 → P03-A9b → P03-M2 → P03-A11 → P03-A12 → P03-A13 → P03-A14 → P03-A15 → P03-A20 → P03-A25 → P03-A26 → P03-A27 → P03-A28 → P03-A30 → P03-A32 → P03-A33 → P03-M4 |
| P04 | 2026-04-24 | 2026-04-24 | 21 | 1 | P04-A1 → P04-A2 → P04-A3 → P04-A4 → P04-A5 → P04-A5b → P04-A5c → P04-M2 → P04-A7 → P04-A8 → P04-A9 → P04-A10 → P04-A11 → P04-A12 → P04-A13 → P04-A14 → P04-A15 → P04-A16 → P04-A17 → P04-A18 → P04-M4 |
| P05 | 2026-05-15 | 2026-05-15 | 21 | 0 | P05-A1 → P05-A2 → P05-A3 → P05-A4 → P05-A5 → P05-A5b → P05-A5c → P05-M2 → P05-A7 → P05-A9 → P05-A12a → P05-A13a → P05-A14a → P05-A15a → P05-A15b → P05-A15c → P05-A16 → P05-A17 → P05-A18 → P05-M4 |
| P06 | 2026-12-24 | 2026-12-24 | 23 | 0 | P06-A1 → P06-A2 → P06-A3 → P06-A4 → P06-A5 → P06-A5b → P06-A5c → P06-M2 → P06-A11 → P06-A12 → P06-A13 → P06-APILOTSTAGE → P06-MPILOTREADY → P06-A16 → P06-A17 → P06-A21a → P06-A21b → P06-A22 → P06-A23 → P06-A24 → P06-A25 → P06-A26 → P06-M4 |
| P07 | 2026-09-01 | 2026-09-01 | 19 | 0 | P07-A1 → P07-A2 → P07-A3 → P07-A4 → P07-A5 → P07-A5b → P07-A5c → P07-M2 → P07-A8 → P07-A9 → P07-A11 → P07-A12 → P07-A13 → P07-A14 → P07-A15 → P07-A16 → P07-A17 → P07-A18 → P07-M4 |
| P08 | 2027-01-08 | 2027-01-08 | 22 | 0 | P08-A1 → P08-A2 → P08-A3 → P08-A4 → P08-A5 → P08-A5b → P08-A5c → P08-M2 → P08-A8 → P08-A9 → P08-A9fat → P08-A11 → P08-A15 → P08-A17 → P08-A18 → P08-A19 → P08-A20 → P08-A21 → P08-A22 → P08-A23 → P08-M4 |
| P09 | 2027-03-03 | 2027-03-03 | 19 | 1 | P09-A1 → P09-A2 → P09-A3a → P09-A3 → P09-A4 → P09-A4c → P09-M2 → P09-A10 → P09-A11 → P09-A12 → P09-A15 → P09-A16 → P09-A18 → P09-A19 → P09-A20 → P09-A21 → P09-A22 → P09-A23 → P09-M4 |
| P10 | 2027-08-06 | 2027-08-06 | 29 | 0 | P10-A1 → P10-A2 → P10-A3 → P10-A4 → P10-A5 → P10-A6 → P10-A7 → P10-A7b → P10-A7c → P10-M2 → P10-A9 → P10-A10 → P10-A12 → P10-A13 → P10-A16 → P10-A17 → P10-A18 → P10-A19 → P10-MIF03 → P10-A20 → P10-A21 → P10-A22 → P10-A24 → P10-A25 → P10-A26 → P10-A28 → P10-M4 |
| P11 | 2026-03-09 | 2026-03-09 | 17 | 0 | P11-A1 → P11-A2 → P11-A3 → P11-A4 → P11-A5 → P11-A5b → P11-A5c → P11-M2 → P11-A9 → P11-B1inst → P11-B2inst → P11-B2rest → P11-B2gis → P11-A11 → P11-A12 → P11-A13 → P11-M4 |
| P12 | 2027-06-23 | 2027-06-23 | 25 | 0 | P12-Y1A1 → P12-Y1A2 → P12-Y1A3 → P12-Y1A4 → P12-Y1A5 → P12-Y1A6 → P12-Y1A7 → P12-Y1A8 → P12-Y2A1 → P12-Y2A2 → P12-Y2A3 → P12-Y2A4 → P12-Y2A5 → P12-Y2A6 → P12-Y2A7 → P12-Y2A8 → P12-Y3A1 → P12-Y3A2 → P12-Y3A3 → P12-Y3A4 → P12-Y3A5 → P12-Y3A6 → P12-Y3A7 → P12-Y3A8 → P12-MPROGCLOSE |

**Total: 428 rows (328 tasks, 100 milestones), 498 relationships; 258 zero-float rows, 3 rows with 1–5bd float.** The representative path shown is one chain; multiple critical branches exist on some projects and are preserved in the full relationship/float exports.

## Cross-project interfaces

| Relationship | Upstream → downstream | Upstream float (bd) | Downstream float (bd) | Remaining date gap (bd) | Drives successor? |
|---|---|---:|---:|---:|---|
| R0398 | P03-I-P03-02 → P10-IF-01 | 284 | 85 | 199 | No |
| R0399 | P08-I-P08-02 → P10-IF-01 | 132 | 85 | 47 | No |
| R0406 | P03-I-P03-03 → P10-MIF03 | 110 | 0 | 142 | No |
| R0407 | P08-I-P08-03 → P10-MIF03 | 45 | 0 | 90 | No |

All four approved P03/P08→P10 interfaces are feasible. None currently drives the successor date; P10 site-integration readiness can nevertheless have zero float due to P10’s internal path.

## Complete QA

| Check | Result |
|---|---|
| 213-row WBS; valid project/control account/work package | PASS: zero invalid mappings |
| Activity/relationship uniqueness | PASS: zero duplicate IDs |
| Relationship endpoints / acyclicity | PASS: zero missing endpoints, zero cycles |
| Milestone duration/date | PASS: all 100 zero duration, identical start/finish |
| Network forward pass vs all stored activity dates | PASS: 0 deviations after five holds + P08 fixed milestone |
| All twelve approved project starts/finishes | PASS: 0 changed |
| Float feasibility and critical flags | PASS: zero negative float, zero flag mismatches |
| Workbook parity after export/import | PASS: all 428 activity/CPM rows and all 498 relationship IDs/lags equal CSV values |
| Workbook formula-error search | PASS: 0 matches |
| Excel ZIP integrity | PASS |

## Resource feasibility screen

- Distribution/excavation contractor peak: **6 crew groups** over 2025-10-21–2025-11-07. Baseline capacity **7** (one group headroom); 4-crew sensitivity deficit **2**.
- Owner commissioning peak: **3 simultaneous project teams**, 2026-10-26–2026-11-04. Assumed availability two internal teams plus one temporary specialist; baseline deficit **0**, but without that temporary specialist deficit **1**.
- Electrical, controls/I&C and inspection capacities remain screening assumptions rather than detailed individual resource assignments. This check is not an exhaustive resource-leveled schedule.

## Qualifications and next step

- The seven unrecovered P01/P02 activity durations remain **provisional synthetic assumptions approved for this portfolio**. The P06 pilot assumes pre-delivery technical integration in a test environment and sufficient cybersecurity/IT work.
- P08-MOUTAGE is a *fixed dated event*, not a newly inferred 10bd causal delay. Document this explicitly when presenting schedule results, especially because it has zero float.
- P12 standing-work finish is not the same as program Substantial Completion.
- **Recommended next GitHub commit:** `Build coordinated baseline program schedule`. Upload only after review: replace the master workbook with the completed CPM version and the two processed schedule CSVs; include the QA report and supporting reconciliations as appropriate.
- **Next portfolio phase:** Cost Loading → Monthly PV → EVM → Power BI.

No GitHub upload was performed.
