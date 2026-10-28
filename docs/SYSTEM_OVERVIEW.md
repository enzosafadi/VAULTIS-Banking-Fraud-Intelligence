# VAULTIS — V2 System Overview
**Target design; not yet implemented or verified**

## Account takeover workflow
Synthetic account history and events → account-scoped temporal correlation → explainable risk signals → persistent investigation case → simulated verification/containment → recovery review → recorded closure.

## Planned components
| Component | Responsibility |
|---|---|
| Journey simulator | Seeded attack and benign sequences with separate truth labels |
| Event normalization | Stable IDs, event/ingestion timestamps, deduplication and quality flags |
| Correlation and rules | Institution/account boundaries, configurable windows, rule version and reasons |
| Investigation workspace | Evidence timeline, ownership, notes, decisions and open questions |
| Case/action store | Persist case transitions and simulated protection/recovery actions |
| Audit and evaluation | Trace decisions and measure scenario outcomes without truth-label leakage |

## Planned contracts
Events: event ID, institution/account ID, session/device identifiers where applicable, event type, event time, ingestion time, synthetic attributes and quality flags. Transfer events additionally include transfer/beneficiary references, amount and currency. Journey truth labels are stored separately for evaluation.
Cases: case ID, related evidence IDs, status, owner, score/rule version, disposition and timestamps.
Actions: action ID, case ID, actor, action type, simulated outcome, reason, related transfer/session/hold, prior/new state and timestamp.

Missing evidence must be visible. Scores are heuristic prioritization signals, not fraud probabilities. Currency totals must stay separate unless an explicit conversion method is provided.

## Existing software baseline
The repository currently contains the V1 v0.1 Streamlit prototype, category rules and independent synthetic events. It does not yet establish the V2 temporal workflow, persistent cases or simulated recovery. Successful runtime and UI verification remain unconfirmed in this revision.

## Boundaries
Synthetic data only. No real customer accounts, payment execution, bank feeds or protection guarantees. Authentication, authorization and secure deployment remain additional engineering work before any non-local use.
