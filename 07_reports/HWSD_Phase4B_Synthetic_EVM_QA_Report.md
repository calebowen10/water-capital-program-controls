# HWSD Phase 4B — Synthetic Actual Progress and Cost Scenario (2026-03-31)

**Status: scenario generated and reconciled.** All records in this package are **fictional, deterministically generated portfolio modeling data**, not audited actuals, supplier information, or real municipal project performance. This snapshot is illustrative, not an approved contractor forecast.

## Frozen approved source inputs
- Source workbook: `HWSD_Project_Controls_Model_Cost_Baseline_PV.xlsx` (new output copy only).
- Approved project BAC $88,500,000.00 across 12 projects; separate contingency $7,500,000; authorized $96,000,000.
- 342 budgeted ownership components, 328 budgeted tasks; 428 schedule rows and 498 relationships unchanged.
- Frozen original monthly PV retained across 2025-01 through 2027-12. No future-period EV/AC records generated.

## Status summary
- PV = **$54441596.86**; EV = **$53047300.74**; AC = **$57699638.90**.
- CV = **$-4652338.16**; SV = **$-1394296.12**; CPI = **0.9194**, SPI = **0.9744**.
- Aggregated project EAC = **$95434737.44**, *not* BAC / program CPI.
- Evidence records: 343; separately incurred-cost entries: 391; purchase-order commitments: 28.

## Synthetic scenario mechanics (version 1)
- Reproducible per-project workday shifts and cost multipliers are in `phase4b_scenario_assumptions.csv`; deterministic SHA-256 per-line perturbations provide variation. These are invented assumptions.
- Workday-based components use independently simulated engineer-completion or 100-unit synthetic accepted-quantity index; they do not copy PV. The synthetic quantity index is **not** a real meter, pipe, or site quantity.
- Procurement components earn 20%/30%/30%/20% at **synthetic, shifted accepted-stage dates**, independently of the baseline PV stage dates.
- Final-gate components earn 0% or 100% on a separate synthetic acceptance date; component-funded gates remain distinct even when sharing an activity.
- Closed P01/P02/P11 components finish by the cutoff. P10 has no earned work, cost or commitment before its April 2026 scheduled start.
- Each line's synthetic AC is accrued from its modeled work performed, project cost multiplier, and an additional early procurement 2% incurred-cost allowance; AC is recorded at month end as an *incurrence date*, not a paid invoice.
- The commitment register contains separately labeled synthetic purchase orders for procurement components started by cutoff. Unincurred commitments are reported separately and **never added to AC**. These values are placeholders, not external contractual evidence.
- EV and AC remain monthly transaction ledgers; monthly PV is still an approved frozen historical baseline.

## EAC convention
- Completed: EAC = assumed final incurred AC. Active with meaningful EV and AC: BAC / cumulative CPI, marked indicative. Future/not started: BAC unchanged with no performance forecast. Program EAC is sum of project EAC values, not an extrapolation from aggregate program CPI. No remaining contractual forecast or actual management estimate was modeled.

## QA / limits
- Project and program BAC unchanged; contingency outside performance denominators.
- Component EV never exceeds its BAC; no progress beyond 100%; duplicate line and evidence IDs prevented.
- Evidence-earned EV equals component/project/program summary; actual ledger equals recorded AC; commitment figures excluded from AC.
- Baseline retains 432 project-month PV records; reporting cutoff excludes later actual/EV data.
- Workbook source schedule and relationship IDs verified unchanged and output workbook reimported.
- A monthly end-of-period timestamp is a synthetic accounting approximation, not proof of an actual invoice date.
- **Scope limit:** project-level cost-category assumptions are portfolio storytelling choices. These do not establish true field progress, specific procurement outcomes, invoices, physical quantity acceptance, detailed cash flow, or a resource-leveled recovery plan.

## GitHub decision
**Commit after reviewing the workbook and QA.** Replace `03_excel_model/HWSD_Project_Controls_Model.xlsx`; add synthetic progress, evidence, actual cost ledger, commitment register, EVM monthly/project summaries, scenario assumptions and QA CSVs to `02_data/processed/`; add this report under `07_reports/`. Suggested message: `Add synthetic progress actual costs and EVM snapshot`. Do not change baseline PV, schedule, or cost-ownership CSVs.

## Next phase
Phase 5: Power BI data model and executive dashboard, using baseline PV together with the Phase 4B synthetic actuals and EVM tables.
