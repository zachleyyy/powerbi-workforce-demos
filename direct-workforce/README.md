# Direct workforce — native Power BI synthetic demo

This is a sanitized adaptation of an existing workforce dashboard project. It is a native Power BI project (`DirectWorkforce.pbip`), not an HTML reconstruction or a report export. The original project was left untouched.

## Synthetic data only

All imported data is generated deterministically inside the semantic model as typed, embedded Power Query `#table` expressions. No source records, workbooks, public datasets, credentials, tenant metadata, or external connections are included. Demo worker labels identify fictional generated rows, not anonymized real people. Contact, identity-document and sensitive demographic fields are blank or explicitly non-applicable.

The demo contains 48 fictional workers, three sites, four teams, four grades, four products, join/exit events, monthly staffing requirements and a 2026 date dimension. The fixed demonstration reference date is **2026-03-31**. Historical hire dates are also synthetic. Changing the computer date does not change the demonstration clock.

## Open and refresh

1. Use a current Power BI Desktop version that supports PBIP, PBIR and TMDL projects. Enable project-format support in Desktop if your version requires it.
2. Keep `DirectWorkforce.pbip`, `DirectWorkforce.Report` and `DirectWorkforce.SemanticModel` together. Open `DirectWorkforce.pbip` locally.
3. Select **Home > Refresh** to materialize the embedded synthetic tables and calculated model objects. No organizational sign-in, source credentials, spreadsheets, gateway or network data source is required for the model refresh.
4. Explore the overview, movement and attrition pages. Select periods in 2026; the demo's current-week definition covers March 30–April 5, 2026. All original persisted slicer/filter selections were deliberately cleared.
5. Save any Desktop-generated local caches outside a publication package. Do not publish/upload this working copy as part of validation.

The report uses a local `byPath` model binding. Keep the relative folder layout intact. The supplied project contains definitions, not a pre-materialized data cache; Refresh is required before evaluating visuals.

## Adaptation and limitations

- Model columns and declared types are retained. Generic DAX arithmetic and report field bindings are retained; source-specific location mapping, branded header text, the source validation window and requirement-quarter display are replaced with neutral demo logic. Age/tenure and current-week calculations use the fixed demo reference date.
- Three legacy employee relationships crossed incompatible string/integer key types. They are omitted while their column types remain intact. Existing compatible latest-employee relationships are retained, with a compatible relationship added for the historic snapshot. The legacy integer-key employee table remains in the schema but is not connected to string-key facts.
- Original source M transformations are not demonstrated: all import partitions are replaced with populated synthetic tables. Requirements use a simplified calendar-quarter convention rather than any source-specific fiscal rules.
- Original themes, custom assets, one asset-backed image visual, linguistic metadata, model diagrams, tenant metadata, caches and query scratch files are omitted. A generic built-in theme reference is retained. Filter/bookmark state, data-scoped formatting, custom aliases, presentation-format overrides and unreviewed style settings are cleared. Some source presentation fidelity and saved filtering behavior are intentionally lost; rebuild any desired detail filters using the synthetic model only.
- Validation is static: official JSON schemas, the Microsoft TOM TMDL deserializer and the Microsoft Power Query syntax parser were used. These checks do not execute DAX or M or validate rendered visual behavior.
- **Power BI Desktop rendering and refresh were not tested.** Desktop was not available for this validation. This is a statically validated native working copy, not a claim of Desktop certification or pixel-perfect fidelity.

## Provenance and rights

This package is a sanitized adaptation with wholly synthetic demo data. It does not claim ownership of the underlying design or assign rights to it. **No license is assigned** by this preparation. Obtain the necessary rights and complete local Desktop verification before any separate publication decision.
