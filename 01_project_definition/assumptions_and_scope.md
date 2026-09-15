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
| Approved capital budget (BAC) | $96,000,000 |
| Number of projects | 12 |
| Program contingency / management reserve | $7,500,000 (embedded in the $96.0M total) |
| Reporting cadence | Monthly |
| Status / reporting date | March 31, 2026 (Month 15 of 36) |
| Currency | USD |
| Data type | 100% synthetic / simulated |

The status date is fixed deliberately at Month 15 so that, at the point every dashboard and
report is measured against, some projects are substantially complete, some have not yet started,
and most are mid-execution. This is what allows cost and schedule performance to vary
realistically across the portfolio instead of every project looking the same.

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
  ratios like CPI/SPI across projects).
- RAG (Red/Amber/Green) status thresholds are project-defined assumptions, documented in the
  `11_KPI_THRESHOLDS` tab of the Excel model, and are stated explicitly as assumptions rather
  than industry-mandated values.
- Monthly baseline spending for each project is spread using an S-curve-like pattern and must
  sum exactly to that project's BAC.
- All project IDs (P01–P12) are held constant across every file, sheet, dashboard, and document
  in this repository.

## Data Integrity Rules
These rules apply across every phase of this project and every file in this repository:
1. Program BAC always equals exactly $96,000,000.
2. The sum of the 12 project BACs always equals the program BAC.
3. Monthly baseline spend for each project always sums to that project's BAC.
4. Project IDs, names, and categories are identical across Excel, CSV, Power BI, Python, and
   this README.
5. All EVM values reconcile: CPI = EV/AC, SPI = EV/PV, EAC/ETC/VAC follow the formulas defined
   in the Excel model's `05_EVM` tab.
6. Any change to one part of the model (e.g., a schedule delay) is reflected in every downstream
   table, calculation, and dashboard it affects.
