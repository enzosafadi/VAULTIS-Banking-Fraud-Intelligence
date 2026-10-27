# VAULTIS
### Banking Fraud Detection & Decision Intelligence
**Enterprise portfolio case study | Prototype v0.1 | Fictional banking network**

VAULTIS is an interactive banking fraud intelligence prototype designed to illustrate how investigators could prioritize and investigate suspicious activity across **eight fictional financial institutions**.

## The business problem
Financial institutions face fragmented signals across authentication, payments, and onboarding. Separate alert queues can obscure multi-stage attacks and increase manual triage effort. VAULTIS explores a unified approach that differentiates:
1. **Phishing:** credential theft and suspicious authentication signals.
2. **Credit card fraud:** card testing, unusual velocity, geographical inconsistencies.
3. **Identity theft:** synthetic identities, mismatched identities, fraudulent onboarding.
4. **Potential attack chains:** signals spanning these categories, surfaced for investigation rather than asserted as confirmed causal links.

## Solution and workflow
**Synthetic events → category-specific detection rules → explainable 0–100 risk score → severity-based queue → investigator review → network intelligence.**

### Prototype features implemented
- Multi-bank command center with risk KPIs and category distribution.
- Explainable risk scores, severity classification, and recommended triage action.
- Investigation workspace with event evidence and case context.
- Potential multi-stage fraud indicator view.
- Eight-bank comparative monitoring view.
- Reproducible simulated dataset (2,500 events by default).

### Eight fictional institutions
Meridian Capital Bank (Switzerland), Northbridge Financial (Canada), Altrix International Bank (UK), Cedarstone Banking Group (Lebanon), Vantara Financial (Singapore), Helix Commercial Bank (Germany), Novaris Bank (USA), and Atlas Continental Bank (France).

## Business value hypothesis
VAULTIS is designed to explore **faster alert prioritization, better investigative context, and visibility into linked fraud signals**. These are intended benefits, **not measured improvements**. Real-world performance requires labelled cases, false-positive analysis, precision/recall evaluation, analyst time studies, security testing, and deployment validation.

## Architecture
- UI: Streamlit + Plotly.
- Processing: Python / pandas.
- Detection: deterministic, category-specific heuristic rules with interpretable reasons.
- Dataset: seeded, fictional, synthetic events; no actual customer records.
- Status: working prototype code in private repository, not a live banking service.

## Deliverables and evidence
See [Business Case](docs/BUSINESS_CASE.md), [Architecture](docs/SYSTEM_OVERVIEW.md), and [Roadmap](docs/ROADMAP.md).

**Screenshots:** SS1 — Command Center; SS2 — Fraud Investigation; SS3 — Cross-Category Intelligence. Screenshots will be added after verification of the running UI. No fabricated screenshots.

## Limitations and responsible representation
**No production AI model is implemented in v0.1.** This is a rule-based prototype, not a validated AI-powered fraud prevention system. No live bank feeds, payment decisions, or customer identities are involved. Synthetic event amounts have multiple currencies; do not sum them without FX conversion. Bank names are fictional and not endorsements or verified trademarks.

**Source code:** Maintained privately. This public repository documents the portfolio business case and architecture.

**Project:** VAULTIS — Banking Fraud Detection & Decision Intelligence
