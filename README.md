# Workforce headcount, staffing gaps and attrition | Power BI

A Power BI reporting project for HR, workforce-planning and operations teams to compare available headcount with staffing requirements, explain changes through hires and exits, and review attrition by site, worker category and reporting period.

A workforce total alone does not explain whether a site is understaffed, whether recruitment is keeping pace with departures, or whether a recorded exit is a genuine loss of workers. This project brings staffing requirements, roster dates and movement records into related reporting views so those questions can be investigated together.

**This public repository uses entirely synthetic data.** It demonstrates the models, report structure and reviewed calculations without publishing employee records or company connections. It contains native Power BI projects, not a live HR system or a hosted dashboard.

## What the project helps users decide

| Reporting question | What the project provides | Decision it supports |
|---|---|---|
| Does a site have enough people for its staffing plan? | Actual-versus-required headcount, staffing gap and fulfilment measures in the direct and combined projects | Identify staffing shortages before discussing recruitment or allocation |
| Why did headcount change during the selected period? | Opening and closing headcount, joiners, exits and net movement | Separate hiring activity from departures rather than interpreting the closing total alone |
| Which groups account for departures? | Attrition views by worker category, tenure, location and termination reason; vendor analysis in the fiscal project | Focus retention or supplier discussions on the affected groups |
| Is an exit actually an internal conversion? | Fiscal measures separate verified conversion events from attrition-eligible exits and flag events requiring review | Avoid treating every recorded departure as workforce loss |
| Do movement records explain the reported total? | Reconciliation variance/residual measures and fiscal repeated-event and unassigned-hierarchy checks | Flag records or reporting definitions for investigation instead of assuming every difference is a real staffing change |

These are reporting and review functions. The project does not forecast staffing, prove why someone left, automate recruitment, or measure the effect of a retention intervention.

## Three related dashboards

### Direct workforce: staffing coverage and movement

The direct-labour (DL) dashboard compares available workers with site staffing requirements. Its three pages cover workforce overview, movement and attrition. The available dimensions include site, product, grade and worker category.

The model separates the workforce roster, headcount snapshot, movement events and staffing requirements. A roster count, the number of hires in a period and the number of people required are different quantities; the report provides measures for each.

Entry point: `direct-workforce/DirectWorkforce.pbip`.

### Combined workforce: labour-type and worker-category comparison

The combined project extends the overview, movement and attrition structure with labour-type analysis for direct and indirect labour (DL/IDL). Employee and contingent-worker categories support separate attrition measures.

Use it to compare workforce composition and movement across labour types and sites. Labour type and employment category are separate dimensions: DL/IDL is not the same distinction as employee/contingent worker.

**Scope detail:** the retained requirement measure, `Required DL HC`, uses the direct-labour requirement table. It is not a complete staffing target for every labour type.

Entry point: `combined-workforce/Combined Workforce.pbip`.

### Fiscal workforce: period comparison, vendor attrition and reconciliation

The fiscal project organizes movement around fiscal reporting periods. It includes opening/closing headcount, previous-period comparisons, employee/contingent-worker composition, vendor metrics and management-hierarchy breakdowns.

It addresses a specific attrition-reporting issue: an employment event classified as an exit may represent an internal conversion rather than a loss of workers. Separate measures track verified conversion events, events requiring review and attrition-eligible exits. In this public version, classification flags are synthetic inputs, not a production conversion-detection system.

Movement residuals, repeated-event counts and unassigned hierarchy measures flag exceptions for investigation. They do not automatically repair source records.

Entry point: `fiscal-workforce/Fiscal Workforce.pbip`.

## How to interpret the main metrics

| Metric | Definition in the published models |
|---|---|
| Headcount | A distinct-person count evaluated using hire/termination dates and the relevant reporting date. Roster-based and snapshot-based measures are separate. |
| Staffing gap | Current headcount minus required headcount. Negative indicates a shortage against the selected requirement; positive indicates headcount above it. |
| Fulfilment | Current headcount divided by required headcount. The direct/combined requirement measure takes the maximum requirement per site for the selected quarter, then sums across sites; it does not add daily targets. |
| Net movement | Joiners minus exits for the relevant period and measure context, not the closing headcount. |
| Average headcount | The mean of beginning and ending headcount, not a daily-weighted average. |
| Attrition rate | Direct/combined: terminated employees divided by average headcount. Fiscal: attrition-eligible exits divided by average headcount, excluding events flagged as verified internal conversions. |
| Fiscal termination rate | Terminations divided by ending headcount. Its denominator differs from attrition rate. |
| Reconciliation variance/residual | `Closing headcount - (opening headcount + joiners - exits)`. A nonzero result calls for review; it is not proof of duplicate or missing records. |

Date-boundary rules and filter context differ between some measures and projects. Similarly named cards are not necessarily interchangeable, and reconciliation is not guaranteed to return zero. Review the DAX before adopting a reporting convention.

## Technical approach

```text
Embedded synthetic Power Query tables
        -> Native semantic model: roster/snapshots/events + dimensions
        -> DAX headcount, movement, requirement and review measures
        -> Native Power BI report pages and field bindings
```

- Power Query (M) supplies typed, deterministic embedded tables. The public version does not reproduce the operational extraction pipeline or connect to an HR system.
- DAX defines date-aware headcount, movement, staffing-gap, attrition and reconciliation measures.
- Related fact and dimension tables separate workforce, dates, organizational groups and staffing requirements. The fiscal project uses a different model structure.
- PBIP, PBIR and TMDL keep the project, report and model definitions as text files for review and version control.

## Open the projects

1. Clone or download this repository.
2. Use a compatible Power BI Desktop installation with PBIP/PBIR/TMDL support.
3. Keep each `.pbip` file beside its companion `.Report` and `.SemanticModel` folders, then open the entry point for the project you want to inspect.
4. Select **Refresh** to materialize the embedded synthetic tables. No original workbooks, source credentials or company network connections are supplied or required by these model definitions.
5. Use the dates documented in each project README. The demos use fixed reference dates and different calendar ranges, not live data.

GitHub stores the definitions; it does not render an interactive Power BI report. This version includes no screenshots or hosted report.

## Public demo scope

The rows are invented examples, not anonymized real employees or evidence of business results. This repository does not claim measured time savings, reduced attrition, production deployment or completed source-system integration.

Branding, images, cached data, original records, service bindings and saved selections were excluded or neutralized. Some legacy relationships, classifications, formatting and narrative measures changed during preparation. Each project README explains its fidelity limitations.

## Validation limits

Automated tests, JSON schema checks and offline Microsoft TOM model deserialization were performed. These are not engine execution tests. **Power BI Desktop opening, refresh, DAX/M evaluation and visual rendering have not been tested.** Treat these as statically validated working copies, not certified dashboards. The synthetic rows illustrate behavior; they are not real workforce statistics or benchmarks.

## Rights

Data sanitization is not an ownership transfer. No open-source license is assigned. Redistribution of the underlying report design and calculations requires the appropriate rights. Private source-selection, build and audit materials are deliberately excluded from this repository.
