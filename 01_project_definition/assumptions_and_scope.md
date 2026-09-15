# Assumptions & Scope

## Fictional Utility
**Harborview Water & Sewer Department (HWSD)** — a fictional mid-sized municipal water utility
in the northeastern United States. No real utility, municipality, contractor, or individual is
represented by this data.

## Program Mission
Modernize aging drinking-water infrastructure, improve reliability, reduce failure risk, satisfy
regulatory and service obligations, and deliver the work within an approved multi-year capital
budget.

## Program Parameters

| Parameter | Value |
|---|---|
| Program name | HWSD Municipal Water Capital Improvement Program |
| Program duration | 36 months (January 2025 – December 2027) |
| **Project BAC total (P01–P12)** | **$88,500,000** |
| **Program contingency reserve** | **$7,500,000** |
| **Total program authorization** | **$96,000,000** (Project BAC total + contingency reserve) |
| Number of projects | 12 |
| Reporting cadence | Monthly |
| Status / reporting date | March 31, 2026 (Month 15 of 36) |
| Currency | USD |
| Data type | 100% synthetic / simulated |

### Budget architecture — read this before touching any cost data
This program tracks two distinct pools of money, and they are never added together as if they
were one project budget:

- **Project BAC total ($88,500,000)** — the sum of the 12 projects' scoped, baselined budgets.
  This is the number used as "BAC" everywhere EVM is calculated (Phase 4 onward): program-level
  CPI and SPI are dollar-weighted rollups of the 12 projects, denominated against $88,500,000,
  not $96,000,000.
- **Program contingency reserve ($7,500,000)** — unallocated, held at the program level,
  controlled by the Program Manager. It covers *known-unknown* risks within the program's
  identified risk profile. It is not assigned to any project and does not appear in any
  project's BAC unless and until it is formally drawn down through an approved change request
  (Phase 6 — Change Control), at which point the dollar amount transfers into the receiving
  project's BAC and out of the reserve balance.
- **Total program authorization ($96,000,000)** — the sum of the two above. This is the
  governance/appropriation figure, not an EVM figure. It's the number a reader would see on a
  capital-budget resolution; it is not the denominator for any performance ratio.

This project deliberately uses a single reserve pool rather than splitting contingency and
management reserve into two separately tracked pools. The latter distinction (known-unknown
risk controlled by the Program Manager, vs. unknown-unknown risk held above the Program
Manager's authority) is real in practice, but modeling two reserve pools would add complexity
without adding anything this portfolio needs to demonstrate — one clearly defined reserve is
more defensible than two loosely defined ones.

The status date is fixed deliberately at Month 15 so that, at the point every dashboard and
report is measured against, some projects are substantially complete, some have not yet started,
and most are mid-execution. This is what allows cost and schedule performance to vary
realistically across the portfolio instead of every project looking the same.

### Proportional BAC normalization — a documented modeling choice
The 12 project BACs were originally drafted to sum to $96.0M with no separate reserve — an
internally inconsistent structure, since $7.5M of that total was also being described as
contingency. To correct this, every project's BAC was scaled down by the same factor
(88.5 / 96.0 ≈ 0.921875) and rounded to the nearest $0.1M, so that:

- Each project's **relative size** within the program is unchanged — P03 (WTP Process Upgrade)
  is still by far the largest project, P11 (Valve Replacement) still the smallest, in the same
  proportion as before.
- The **project BAC total** lands exactly on $88.5M, leaving a clean, separately identified
  $7.5M for the program contingency reserve.

This is a synthetic modeling choice, not a claim that any real capital program would rescale
budgets this way. An actual utility would set each project's budget independently based on its
own cost estimate, then set contingency as a percentage of that total. Proportional scaling was
used here purely to preserve the *relative* shape of the original 12-project portfolio while
correcting the double-counting error, without arbitrarily cutting one project to absorb the
entire $7.5M. It is documented here so the reasoning is transparent rather than assumed.

### P12 vs. the program contingency reserve — do not conflate these
**P12 (Programwide Small Capital & Emergency Response Improvements, $5.1M)** is real, planned,
scoped standing capital work — small distribution repairs, emergency response capital projects,
and similar recurring needs that are budgeted every capital cycle but not tied to one specific
asset. It has its own BAC and is included in the $88,500,000 project BAC total.

**The program contingency reserve ($7.5M)** is a separate, unallocated pool held at the program
level. It is not a project, has no BAC of its own, and does not appear anywhere in the 12-project
list. It is only accessed through an approved change request (Phase 6), which increases the
receiving project's BAC and decreases the reserve balance.

If a genuinely unplanned, unscoped event occurs (e.g., an emergency main failure beyond what P12
anticipated), that draws from the **contingency reserve** via change control — not from P12.

## In Scope
- Program- and project-level controls: scope, schedule, budget, performance tracking
- Work breakdown structure and baseline scheduling
- Earned Value Management (PV, EV, AC, CPI, SPI, CV, SV, EAC, ETC, VAC)
- Risk register, probability/impact scoring, and risk heat mapping
- Change control, including one modeled scenario with cost and schedule impact
- Resource/staffing and vendor/contractor tracking
- Monthly and executive-level reporting (Excel and Power BI)
- Optional Python-based Monte Carlo cost/schedule risk simulation

## Out of Scope
- Detailed hydraulic design or process engineering calculations
- Structural or civil design calculations
- Stamped engineering drawings or licensed professional engineering deliverables
- Real municipal procurement actions, real contractor identities, or real financial data

This project demonstrates the **industrial engineering / project-controls / program-management**
side of infrastructure delivery — not licensed civil engineering design.

## Governance (Simulated)
Executive Sponsor → Program Manager → Project Managers → Discipline Leads / Contractors →
Controls Analyst (this role, held by the project author).

## Methodology Assumptions
- EVM is calculated at the project level using the simplified method: **EV = BAC × physical
  percent complete**, then rolled up to the program level by summing dollars (not averaging
  ratios like CPI/SPI across projects). The "BAC" in every EVM formula refers to the
  **$88,500,000 project BAC total**, never the $96,000,000 total program authorization.
- RAG (Red/Amber/Green) status thresholds are project-defined assumptions, documented in the
  `11_KPI_THRESHOLDS` tab of the Excel model, and are stated explicitly as assumptions rather
  than industry-mandated values.
- Monthly baseline spending for each project is spread using an S-curve-like pattern and must
  sum exactly to that project's BAC.
- All project IDs (P01–P12) are held constant across every file, sheet, dashboard, and document
  in this repository.

## Data Integrity Rules
These rules apply across every phase of this project and every file in this repository:
1. The sum of the 12 project BACs always equals exactly $88,500,000 — the project BAC total.
2. The program contingency reserve always equals $7,500,000 and is never counted as part of
   any project's BAC unless drawn down through an approved change.
3. Total program authorization (project BAC total + contingency reserve) always equals exactly
   $96,000,000.
4. Monthly baseline spend for each project always sums to that project's BAC.
5. Project IDs, names, and categories are identical across Excel, CSV, Power BI, Python, and
   this README.
6. All EVM values reconcile: CPI = EV/AC, SPI = EV/PV, EAC/ETC/VAC follow the formulas defined
   in the Excel model's `05_EVM` tab, denominated against the $88,500,000 project BAC total.
7. Any change to one part of the model (e.g., a schedule delay, or a change request that draws
   down contingency) is reflected in every downstream table, calculation, and dashboard it
   affects — including the contingency reserve balance itself.
