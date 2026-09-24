# HWSD Phase 3G — Cost Baseline and Monthly PV Integration

**Status: PASS.** Phase 3D ownership and Phase 3F recognition conventions were explicitly approved by the user for a synthetic portfolio. No EV, AC, planned cash, invoice or actual progress records were invented. No GitHub changes were made.

## Reconciliation

- Approved workbook projects: **$88,500,000.00** (12 projects). Cost ownership: **$88,500,000.00**, **342** unique lines across **328** budgeted positive-duration tasks.
- Monthly PV for January 2025 through December 2027: **$88,500,000.00**; separate unallocated contingency: **$7,500,000.00**; authorized program: **$96,000,000.00**.
- Work packages **141**, control accounts **72**; milestone additional BAC **$0**.
- Detail contains **571 nonzero ownership-line/month records**, with exactly **432 project-month records** (12 × 36). Zero-value line/month combinations are omitted from detail, not the project-month view.
- Workbook reimport confirmed exact-cent project-month parity; schedule and relationship IDs unchanged; Excel ZIP integrity passed. Existing master workbook was read, not overwritten.

## Recognition mechanics

1. `WORKDAY_SPREAD` and `WORKDAY_FALLBACK`: allocate component BAC in integer cents evenly over inclusive scheduled Monday–Friday days, with any cent residual on last day. Fallback is expressly synthetic without independently scheduled quantities.
2. `PROCUREMENT_20_30_30_20`: distribute integer-cent budget at preapproved synthetic 20/50/80/100% workday-percentile dates. First three amounts floor to cents; final stage takes residual. Stages can share a date for a short task and are summed per month. These are **planned proxy events**, not actual vendor evidence.
3. `FINAL_GATE`: allocate planned BAC 100% on scheduled activity finish; actual EV would require distinct evidence.
4. P04 functional-readiness / acceptance, P08 vendor-integrated fuel installation, P03 testing/signoff, P05 zone sampling, P11 GIS and P12 annual emergency work retain separate funded work-package ownership.

## Workbook integration

`04_MONTHLY_COSTS` contains project-month PV and cumulative PV; actual, commitment and forecast cells remain empty. Added: `COST_CONTROL_ACCOUNTS`, `COST_WORK_PACKAGES`, `COST_ACTIVITY_OWNERSHIP`, `COST_EARNING_RULES`, `COST_MONTHLY_PV_DETAIL`, `COST_PROJECT_MONTH`, `COST_PROGRAM_MONTH`, `COST_ASSUMPTIONS`, `COST_VERSION_LOG`, `COST_QA`. `05_EVM` remains unpopulated. Existing schedule and CPM retained. `data_dictionary_phase3g.xlsx` is an expanded new copy of the original dictionary (existing sheet preserved); CSV additions also supplied. No original dictionary was overwritten.

## Limitations

- This is a **frozen, externally computed PV snapshot**, not self-recalculating Excel formulas; change controls require re-running the documented recognition algorithm and QA.
- The original sources do not supply independent planned construction quantities, procurement invoices, deliveries or EV acceptance evidence.
- Project budget allocations and embedded-scope assumptions are approved **only for the synthetic portfolio**, not a verified municipal estimate.
- Planned cash flow is a separate future model and cannot be inferred from PV.

## GitHub

**Commit after reviewing the workbook:** replace `03_excel_model/HWSD_Project_Controls_Model.xlsx` with the provided cost/PV workbook. Add seven cost/PV CSV exports to `02_data/processed/`. Add this report and the schema additions under documentation. Do not replace the baseline schedule or relationship CSVs because their values did not change. Suggested message: `Add cost-loaded baseline and monthly planned value`.
