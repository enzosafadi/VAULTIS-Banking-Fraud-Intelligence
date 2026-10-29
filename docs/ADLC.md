# VAULTIS — ADLC Delivery Evidence
**v2.0.1-demo | Traceable delivery lifecycle | 2026-10-28**

VAULTIS uses ADLC to connect requirements, design decisions, implementation, verification and owner acceptance. The product owner sets direction and accepts the result; AI-assisted implementation and automated checks supply evidence. The running application is deterministic and rule-based, with no trained AI model.

| Stage | Recorded evidence | State |
|---|---|---|
| Define | Business case, focused account takeover scope and twelve traced requirements | Recorded |
| Design | Architecture, rule/data contracts and decision register in private core | Recorded |
| Build | Private implementation; previous versions retained | Implemented v2.0.1 |
| Verify | 26 passing tests; metrics and saved starter states reproduced | Local automated check passed |
| Accept | Actual Windows overview accepted; five hands-on checks pending | Partial |
| Final portfolio release | Latest populated screenshots and completed owner review | Pending acceptance |
| Maintain | Repeatable validator, source/runtime evidence and CI configuration | Established |

## Requirement coverage
The private core matrix maps ATO-01 through ATO-12 to implementation artifacts and named tests: reproducible journeys, temporal isolation, explanations, persistence, simulated controls, recovery, evaluation, audit, staff documentation, populated startup, data quality and current screenshot evidence.

## Current evidence
[Machine-readable status](../reports/ADLC_STATUS.json) records 26 passing tests, twelve traced requirements and the expected synthetic counts: 54 true positives, twelve false positives, 48 true negatives and six false negatives. Fresh saved case histories contain eight active simulated holds and twelve closed cases.

The recorded run is a local development check, not evidence that a GitHub CI run or real-bank validation has passed. CI is configured in the private repository for Python 3.11 and 3.13.

## Owner acceptance
UAT-01, Windows launch and the populated overview, is supported by [actual V2 SS1](../screenshots/V2/SS1.png). UAT-02 through UAT-06 still require owner review of active investigation evidence, durable notes/corrections, simulated recovery/reviewer release, audit/export, and evaluation/current screenshots.

Passing tests cannot accept these steps on the owner's behalf. The strict release check deliberately reports pending acceptance rather than declaring the demonstration fully accepted.

## Boundaries and history
This is an independent local simulation, not client experience, a production security service or real account protection. Demo roles are not authentication. Prior source/docs remain archived, including the pre-ADLC baseline at `archive/v2.0.1-before-adlc` in each repository.

[Verification](VERIFICATION.md) · [Release checkpoint](RELEASE_CHECKPOINT.md) · [Current screenshots](SCREENSHOTS.md) · [History](HISTORY.md)
