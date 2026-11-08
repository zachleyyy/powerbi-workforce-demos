# Combined workforce — synthetic Power BI demo

This is a sanitized adaptation of a native Power BI project. All embedded rows are deterministic fictional demo data, not anonymized original records. No original dataset, public dataset, credentials, caches, images, spreadsheets, exports, or remote data connections are included.

## Open and refresh

Keep the project and both companion folders together. Open `Combined Workforce.pbip` using Power BI Desktop with Power BI project support enabled. If necessary, enable the Power BI project and enhanced report definition preview features in Desktop settings and restart. Use **Refresh** to populate the semantic model from its embedded typed Power Query `#table` partitions. No source files, credentials, network data access, or organizational service binding are required. Do not upload this working copy without a separate publication review.

The report binds to the sibling semantic model using a local `byPath` reference. This is native PBIP/PBIR/TMDL, not an HTML reconstruction or a pre-rendered report. It is not a PBIX binary export.

## Demonstration scope

The model includes fictional people, headcount, joiner/exit movements, sites, grades, leads, products, and quarterly staffing requirements. The main calendar covers 2025–2026. Demo calculations use a fixed reference date of June 30, 2026. Select a period in the date slicers to explore trends. Measures show illustrative calculations only; they are not business benchmarks.

## Limitations and fidelity

Generic reviewed DAX, field names, native queries, chart types, page layout, and safe relationships are retained. Organizational location mapping and header text have neutral replacements. A historical validation measure now follows the ordinary joiner measure. Original branding, an image visual, themes, formatting, identity-bound styles, persisted filters, bookmark/expansion state, and linguistic metadata are excluded. Visuals use default Desktop styling; projection captions are neutral. The fiscal labels in synthetic data follow calendar quarters, while the retained fiscal month sorting convention may differ.

Two legacy relationships with incompatible employee-key types are omitted rather than changing declared column types. The compatible latest-employee dimension relationships are retained. This can change cross-filter behavior for the legacy employee dimension.

Static validation is not Power BI engine execution. Power BI Desktop opening, refresh, DAX/M evaluation, and visual rendering have **not** been tested. Validate these locally before treating this as a finished presentation or publishing it.

## Provenance and rights

Prepared as a sanitized adaptation of an existing native dashboard family, with entirely new synthetic rows and neutral presentation text. This working copy makes no license assignment and no claim about rights to redistribute underlying dashboard design. The private audit and build tooling are intentionally outside this folder.
