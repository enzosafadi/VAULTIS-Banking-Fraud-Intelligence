# System Overview
## Functional architecture
```text
Eight fictional banks
        |
Synthetic event generator
        |
Fraud taxonomy (phishing / card fraud / identity theft)
        |
Explainable rule-based risk engine
        |
Severity, evidence reasons, possible linked signals
        |
Streamlit analyst workspaces
  | Command Center | Investigations | Fraud Chains | Bank Network |
```

## Data contracts
Each event includes a synthetic event ID, timestamp, bank, country, fraud category, synthetic customer and account IDs, nominal amount, currency, channel, indicators, risk score, severity, possible linked-fraud flag, investigation status, and recommendation.

## Risk methodology
Risk score = min(100, baseline 8 + sum of category-specific indicator weights + possible linked-signal bonus 10). Thresholds: Critical ≥80, High ≥60, Medium ≥35, otherwise Low. This is demonstrative and not calibrated to empirical loss rates.

## Security and production gaps
No authentication, persistent audit log, live integrations, real-time ingestion, trained ML, or case management writes. Do not use for production decisions. Source remains private.
