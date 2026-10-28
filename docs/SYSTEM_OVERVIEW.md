# VAULTIS — System Overview
**As implemented: local portfolio demonstration**

## Data flow
Seeded synthetic events → normalization/deduplication → account-scoped temporal rules → persisted case snapshot → investigation and journal → simulated response/recovery → audit and export.

| Module | Responsibility |
|---|---|
| `vaultis/journeys.py` | Ten scenario families, event feed and separate ground-truth manifest |
| `vaultis/ato.py` | Duplicate checks, temporal rules, explanations and evaluation |
| `vaultis/cases.py` | SQLite storage, role demonstrations, state transitions, notes and exports |
| `app.py` | Operations, investigation, documentation, evaluation and operator guide |
| `scripts/validate_demo.py` | Reproducible scenario report and complete case-resolution walkthrough |
| `tests/` | Rule, storage, workflow and Streamlit interaction checks |

The old engine and simulation modules remain as V1 historical code and regression tests; the V2 app imports the new modules.

## Storage and transactions
The local SQLite store persists cases, journal entries, audit records and action submission tokens. Mutations use transactions; case actions compare an expected revision. Retried identical tokens are idempotent. Note corrections form a linked revision chain; a stale revision cannot silently replace a newer correction.

Audit records include actor, UTC timestamp, reason and before/after state. Denied actions on accessible cases are recorded. JSON report preparation is audited, but browser download completion is not tracked. No reset/delete button is supplied.

## Boundaries
Detection operates on normalized events without reading truth labels. Evaluation uses the separate manifest. A local seeded case snapshot is created once; this version does not ingest live streams or update a running case from a changing upstream feed. Reproducible late-event evaluation uses the complete fixture and reports when evidence became available.

Demo identities are selectable and are not authentication. Analyst assignment checks and reviewer-only operations illustrate policy; they do not secure an exposed server. Run locally only. The database is not encrypted and direct filesystem access can alter it. No actual bank actions, ML model, external AI service or uploaded binary documents are involved.
