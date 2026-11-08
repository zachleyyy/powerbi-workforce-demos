# Fiscal workforce — synthetic native Power BI demo

This is a sanitized adaptation of a native fiscal-workforce dashboard project. All rows are deterministic, invented demonstration data; none are source records, sampled data, public datasets, or representations of an actual organization. It remains a Power BI Project (PBIP), PBIR report and TMDL semantic model, not an HTML reconstruction.

## Open and refresh

1. Use a Power BI Desktop version supporting PBIP, PBIR and TMDL project definitions; enable the relevant project features if required by your installed version.
2. Open `Fiscal Workforce.pbip` in Power BI Desktop.
3. Select **Refresh** to import the seven embedded typed M tables. No files, server, account credentials, gateway, network data source, or original dataset are needed for refresh.
4. The imported model has no data cache in this folder. Save any Desktop-generated local caches outside the publication copy. Review chart/slicer defaults after first opening; the report deliberately has no saved data selections.

## Contents and synthetic scenario

Seven populated tables retain the safe column names and declared types required by the report. Six model relationships and 80 measure names are retained. Synthetic employees span hires, departures, two verified-conversion examples and two review examples, sites, vendors, products and management groups. The calendar covers 2024–2025 and uses an explicitly illustrative July-start fiscal year, with simple seven-day fiscal weeks; this is not an assertion about the source calendar. Snapshot date is fixed at 2025-12-31.

Nine neutrally named report pages retain visual placements and schema-resolved field projections. Built-in default theme and formatting replace original branding. Synthetic contact-style fields use reserved example.invalid values or explicit synthetic placeholders, not usable personal details.

## Deliberate limitations

- External M, import sources and original partition logic were replaced in full with embedded typed synthetic tables. This does not reproduce source-system extraction, reconciliation or operational policy.
- Three calculated classification columns became imported synthetic columns with the same names/types. Nationality classifications are neutral synthetic groups; no actual nationality mapping or organization-specific classification is reproduced.
- Five narrative/text measures were replaced with a synthetic-demo notice. Other generic measures were reviewed; movement-category literals were normalized to the invented Hire/Exit categories.
- All original persisted filters, selections, bookmarks, expansion states, synchronization state, text labels, custom interactions, navigation actions, custom assets, branding and localization metadata were omitted or regenerated. Six image visuals were removed. Text boxes contain neutral demo notices; some decorative shapes/buttons are retained without their original actions/formatting. Default chart formatting and descriptive labels may need adjustment after opening.
- Original records, exports, validation outputs, spreadsheets, images, PDFs, caches and original repositories are not included. The project requires a refresh before data is available.
- Offline Microsoft TOM successfully parsed the semantic model. Official Microsoft JSON schemas validated the native project/report JSON definitions. These checks do not execute DAX or M, import data into the Power BI engine, or prove chart rendering.
- **Desktop rendering has not been tested.** Desktop refresh, expression-engine execution and interactive visual behavior remain unverified; this is a working copy, not a certified production dashboard.

## Provenance and rights

Prepared as a sanitized adaptation of the selected corrected native project, with independently generated synthetic data. The original project was treated as read-only. Private build, audit, tests, hashes and source-selection evidence are intentionally outside this folder. No license is assigned by this README; any rights or permission to redistribute the underlying design must be reviewed separately. No upload, Git initialization or remote operation was performed.
