# VAULTIS
### Account Takeover Detection & Response
**Independent simulated portfolio project | Documentation V2 | Implementation baseline v0.1**

VAULTIS focuses on how a digital banking fraud team investigates and responds when an attacker gains access to a customer account and attempts to move funds.

## One connected fraud journey
Compromised access → unfamiliar login → security change → new beneficiary → attempted transfer → investigation → simulated protection → account recovery.

The planned workspace joins events into an evidence timeline, explains risk signals, supports analyst decisions and records simulated verification, containment and recovery. Benign travel, device replacement and genuine recovery requests are part of the evaluation.

## What exists and what comes next
| Area | Status |
|---|---|
| Private V1 code | Broad fraud prototype: category rules, Streamlit workspaces and synthetic eight-bank events |
| V1 execution and initial visual check | Local launch and Command Center screenshot confirmed; 6 existing tests passed in 5.18s; other views pending |
| V2 account takeover scope and scenarios | Defined |
| Temporal account journeys, persistent cases and action history | Planned |
| Simulated controls and recovery workflow | Planned |
| V2 evaluation results and screenshots | Pending implementation and verification |

V2 denotes the new documentation and project orientation. It does not mean a software v2.0 release has shipped.

## V1 runtime evidence
![SS1 — Actual V1 Command Center and local test output](screenshots/V1/SS1.png)

V1 screenshot, supplied from the running local application on 2026-10-28. V2 features are planned and are not shown here.

## Documentation
- [V1 verification results and screenshot](docs/VERIFICATION.md)
- [Case documentation workspace: user notes, evidence and handovers](docs/CASE_DOCUMENTATION.md)
- [Detailed use case: suspicion triggers, analyst response and institutional value](docs/USE_CASE.md)
- [Business case](docs/BUSINESS_CASE.md)
- [System overview](docs/SYSTEM_OVERVIEW.md)
- [V2 scope and acceptance criteria](docs/V2_SCOPE.md)
- [Roadmap](docs/ROADMAP.md)
- [Change log](CHANGELOG.md)
- [Preserved V1 documentation](docs/V1/README.md)

## Intended users and value
Fraud analysts and fraud operations leads. Intended benefits are clearer evidence, consistent case decisions and visibility into recovery. No adoption, time savings, loss prevention or detection accuracy has been measured.

## Representation
All data is simulated. Protective actions are planned simulations, with no live bank access or payment enforcement. The approach is rule-based; no trained AI model or guarantee of account safety is claimed. Source code remains private. This public repository contains portfolio documentation and an actual V1 screenshot; V2 screenshots await implementation and verification.
