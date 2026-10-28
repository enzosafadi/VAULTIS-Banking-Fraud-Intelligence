# VAULTIS V2 — Account Takeover Detection & Response
**Documentation revision V2 | 2026-10-28 | Design approved; implementation pending**

## Purpose
Demonstrate how a digital banking fraud team detects, investigates, contains, and resolves suspected account takeover using synthetic evidence. One primary fictional institution and linked customer journeys form the first V2 demonstration. The eight-bank V1 dataset remains a legacy baseline; cross-bank expansion is deferred.

## Primary journey
Compromised access → unfamiliar login → security/contact change → new beneficiary → attempted transfer → analyst investigation → simulated protection → verified recovery.

Signals establish suspicion, not proof. An unfamiliar device alone must not be treated as confirmed takeover. The workspace must explain contributing evidence, time order, rule version, missing signals, and analyst decisions.

## Boundaries
In scope: authentication/device events, security changes, beneficiary activity, transfer attempts, temporal correlation, analyst cases, simulated protective actions, recovery, audit evidence, and labelled evaluation.
Out of scope for the first V2 demonstration: standalone card-fraud monitoring, identity onboarding, insider-fraud programs, general AML/mule-network detection, live banking integrations, autonomous real-account restrictions, and trained ML.
Phishing is a possible entry point into the takeover journey. V2 does not claim to detect every phishing message or every form of bank fraud.

## Required capabilities
| ID | Requirement | Demonstration evidence |
|---|---|---|
| ATO-01 | Generate reproducible, time-ordered customer journeys with synthetic truth labels | Seeded fixtures and scenario manifest |
| ATO-02 | Correlate events within the same institution/account and declared time windows | Timeline with source event IDs; cross-account isolation tests |
| ATO-03 | Explain rule scores and confidence limitations | Rule version, reasons, thresholds and missing-data indicators |
| ATO-04 | Persist analyst cases, ownership, notes and decisions | Reload retains state; transition tests |
| ATO-05 | Simulate step-up verification, session revocation and transfer holds | Action state and audit record; no live enforcement |
| ATO-06 | Enforce controlled resolution and account recovery | Recovery checklist, authorized release and closure evidence |
| ATO-07 | Measure detection and customer friction | Case-level confusion matrix and action outcomes |
| ATO-08 | Preserve a traceable decision history | Actor, timestamp, prior/new state, reason and related evidence |

## User documentation requirement
| ID | Requirement | Demonstration evidence |
|---|---|---|
| ATO-09 | Provide a case documentation workspace for staff notes, contact summaries, evidence references, decisions and handovers | Durable save/reload, attributed entries, revision history, access boundaries and safe export |

See [Case Documentation Workspace](CASE_DOCUMENTATION.md) for entry fields, correction rules, a worked example and acceptance criteria. This is planned V2 functionality.

## Scenario catalogue
| ID | Synthetic scenario | Expected review focus |
|---|---|---|
| S01 | Returning customer, familiar device, routine payment | Benign baseline; avoid restriction |
| S02 | Legitimate travel and a new device | Context and successful verification; avoid location-only conclusions |
| S03 | Genuine lost-phone recovery and contact change | Approved recovery without treating every security change as fraud |
| S04 | Compromised credentials followed by new beneficiary and transfer | Escalate correlated suspicious sequence |
| S05 | Hijacked existing session without a new-device signal | Detect downstream security/payment sequence; expose coverage gaps |
| S06 | Repeated failed verification and attempted cash-out | Simulated containment and specialist escalation |
| S07 | Several small attempts after beneficiary addition | Aggregate within declared window; avoid single-amount dependence |
| S08 | Late, missing or duplicate events | Deduplication, event-time handling and incomplete-evidence warning |
| S09 | Same device used by separate legitimate accounts | Prevent cross-account contamination and shared-device assumptions |
| S10 | Duplicate analyst action or release before recovery | Idempotent action handling and denied invalid transition |

Scenario outcomes are acceptance expectations, not observed detection results. Attack labels must not be inputs to the risk engine.

## Case workflow
New → In review → Verification pending → Containment simulated → Recovery review → Closed.
Benign cases may close from In review or Verification pending with recorded rationale. Unresolved verification remains open. Reopening requires a reason. A simulated hold may only be released after the configured recovery checks and authorized review; the release must identify its original hold. A closed case retains its timeline and action history.

## Operating procedure to implement
1. Review event provenance, timing and data quality.
2. Compare device/login context with the synthetic account history.
3. Inspect security changes, beneficiary activity and transfer sequence.
4. Record a disposition and the evidence supporting it.
5. Select a simulated verification/containment action under the configured policy.
6. Escalate unresolved or repeated suspicious activity.
7. Complete simulated recovery checks before releasing restrictions.
8. Close with outcome, residual concerns and audit evidence.

## Evaluation and completion gate
Separate rule-tuning fixtures from a held-out seeded scenario set. Report dataset size, seed, class balance, rule version, threshold and unit of analysis. Evaluate at account-journey/case level with TP, FP, TN, FN, precision, recall, false-positive rate and false negatives by scenario. Report undefined metrics explicitly when a denominator is zero. Track alert volume, simulated restrictions on benign cases and unresolved cases. Synthetic time-to-detection is measured from a declared attack onset; it is not a production latency claim.

V2 demonstration completion requires: reproducible execution; scenario and persistence tests; visible end-to-end investigation/recovery; an evaluation report including failures; and screenshots captured from the actual UI. No accuracy, loss-prevention, ROI or account-safety guarantees are asserted.

## Version meaning
V1 documentation describes the original v0.1 broad fraud prototype. V2 is the current project orientation and documentation baseline. It does not designate a shipped software v2.0. Existing runtime code remains the V1 baseline until implementation and verification are completed.
