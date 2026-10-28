# VAULTIS V2 — Delivered Scope and Acceptance
**v2.0.0-demo | 2026-10-28 | Local simulation**

VAULTIS now implements one deep account takeover workflow for one fictional institution. V1 broad multi-bank monitoring remains in historical GitHub versions.

| Requirement | Delivered evidence | Limit |
|---|---|---|
| ATO-01 Reproducible journeys | Ten scenario families; seeds 7 and 42 | Authored synthetic data |
| ATO-02 Temporal correlation | Account/session/beneficiary joins and 15-minute rule tests | Complete-fixture processing; no streaming updates |
| ATO-03 Explainability | Rule version, score, reasons and source event IDs | Uncalibrated rule signals |
| ATO-04 Persistent cases | SQLite, ownership, versions and reload tests | Local single-file store |
| ATO-05 Protective actions | Verification, hold and session/credential actions | Simulated outcomes only |
| ATO-06 Recovery | Required checks, reviewer release and closure tests | Operator-asserted simulation |
| ATO-07 Evaluation | TP/FP/TN/FN, precision, recall and failure discussion | Shared scenario families; no real validation |
| ATO-08 Audit | Before/after history, denied actions and export | Not tamper-proof or authenticated |
| ATO-09 User documentation | Saved notes, revisions, filters, handover and JSON report | Binary uploads and structured task scheduling deferred |

## Scenario coverage
S01 routine banking; S02 travel/new device; S03 genuine recovery; S04 credential takeover; S05 hijacked existing session; S06 failed verification/cash-out; S07 small transfer attempts; S08 missing/late/duplicate evidence; S09 shared device; S10 urgent legitimate sequence. Duplicate actions and early-release denial are separate workflow tests rather than an attack family.

## Demonstration completion status
Implementation, 24 automated tests and the reproducible end-to-end walkthrough are complete. V1 local visual evidence is published. V2 desktop visual acceptance and V2 screenshots are the remaining portfolio presentation gate. Production deployment is outside scope.

No general-fraud coverage, actual account safety, real payment decision, live bank integration, trained AI or real-world performance result is claimed.
