# VAULTIS — Business Case
## Executive summary
Financial crime investigation teams must distinguish payment anomalies, phishing-related compromise, and identity misuse. VAULTIS proposes a centralized, explainable triage workspace across a fictional network of eight banks.

## Stakeholders
Fraud analysts; fraud operations leads; risk management; financial crime compliance; security teams; executive management.

## Problems and proposed responses
| Problem | VAULTIS design response | Success metric to validate |
|---|---|---|
| Fragmented alert queues | Unified multi-bank command center | Median time to triage |
| Alert overload | Explainable category-specific scoring | Precision at top-K; false positive rate |
| Disconnected attack stages | Cross-category signal correlation | Investigator-confirmed linked cases |
| Limited case context | Investigation details and evidence reasons | Analyst handling time |
| Weak network visibility | Bank and category risk comparisons | Detection coverage by institution |

## Example scenario (fictional)
A customer receives a phishing message, credentials appear compromised, a new identity detail is observed, and a payment anomaly follows. VAULTIS would surface the associated indicators for human review. The current v0.1 demo only flags signal co-occurrence within events; full cross-event causal/entity correlation is on the roadmap.

## Value and measurement
Potential savings = (baseline minutes per alert − new minutes per alert) × reviewed alerts × fully loaded analyst cost per minute. This is a **planning formula**, not a measured ROI. Pilot studies must establish baseline volumes, quality, and investigator outcomes.

## Risks and controls
- False positives: evaluate against labelled synthetic and eventually consented/authorized data.
- Bias and drift: test across groups and channels with appropriate privacy safeguards.
- Security: require access controls, audit logging, encryption, retention limits before production.
- Governance: human review; no autonomous customer blocking in prototype.
- Data: synthetic only, no live banking feeds.

## Scope
Current: rule-based triage prototype and eight-bank synthetic demonstration.
Future: auditable cases, entity graph, streaming integrations, validated ML and model governance.
