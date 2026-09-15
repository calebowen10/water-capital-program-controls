# Municipal Water Infrastructure Capital Improvement Program — Project Controls & Risk Management System

A simulated $96.0M municipal water capital improvement program — 12 projects totaling $88.5M in
baselined work plus a $7.5M program contingency reserve — built to demonstrate industrial
engineering, project-controls, and program-management methods: work breakdown structures,
baseline scheduling, earned value management (EVM), risk management, change control,
resource/vendor tracking, and executive reporting via Excel and Power BI.

> **Portfolio disclaimer:** This project uses synthetic data and a fictional municipal utility
> ("Harborview Water & Sewer Department"). It is intended to demonstrate industrial engineering,
> project-controls, analytics, and program-management methods. It does not represent actual
> municipal performance and does not include licensed civil engineering design.

## Status: Work in Progress

This repository is being built in public, phase by phase. Current phase: **Phase 2, Step 1 —
Work Breakdown Structure (complete)**.

### Project status
- [x] Program definition complete
- [x] Budget architecture complete
- [x] Project master complete
- [x] WBS complete
- [ ] Baseline schedule next

### Planned deliverables
- [x] Program charter, assumptions, and 12-project master list
- [x] Work breakdown structure
- [ ] Baseline schedule
- [ ] Monthly cost model and Earned Value Management (EVM) analysis
- [ ] Risk register and risk heat map
- [ ] Change control scenario and contingency tracking
- [ ] Resource/staffing and vendor tracking
- [ ] Power BI executive dashboard
- [ ] Optional Python Monte Carlo cost/schedule risk simulation
- [ ] Final case study write-up

## Work Breakdown Structure (WBS)

The program's scope is decomposed into 4 levels:

| Level | Meaning |
|---|---|
| **1 — Program** | The single HWSD Municipal Water Capital Improvement Program (implicit root of every WBS code) |
| **2 — Project** | One of the 12 numbered projects (P01–P12), each with a fixed BAC and one accountable Project Manager |
| **3 — Control Account / Lifecycle Phase** | The level at which cost and schedule performance is measured and owned. Every project has 6 control accounts, one per lifecycle phase (11 projects use standard phase names; P12 uses differently-worded phases that still map to the same 6 categories via a `Standard_Lifecycle_Phase` field) |
| **4 — Work Package** | A discrete piece of deliverable scope within a control account, sized proportionally to complexity (1–2 work packages for simple phases like Planning or Closeout, more for Construction and — for the treatment plant project specifically — Testing & Commissioning) |

Schedule activities, built in the next phase, will each reference exactly one Level-4 work
package. Control accounts (Level 3) will later receive their own allocated BAC, PV, EV, and AC
during the Earned Value Management phase, with each project's BAC rolling up from its 6 control
accounts.

See `06_project_controls/work_breakdown_structure.xlsx` for the full, standalone WBS, or
`02_data/processed/wbs.csv` for the raw export.

More detail will be added to this README as each phase is completed.
