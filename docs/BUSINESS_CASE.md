# VAULTIS — V2 Business Case
**Account Takeover Detection & Response | Simulated portfolio project**

## Problem
A suspicious login, changed contact details, beneficiary addition and transfer attempt can appear separately. An analyst needs a time-ordered account view to decide whether these signals indicate takeover or legitimate activity, then document an appropriate response and recovery.

## Intended users
Fraud analysts own triage and case evidence. Fraud operations leads review escalations and simulated release decisions. Security and customer-support roles supply session and recovery context in the demonstration.

## Design response and measurement
| Need | Planned response | Evidence to collect |
|---|---|---|
| Connect suspicious stages | Account-scoped event timeline | Scenario-level coverage and missed sequences |
| Explain prioritization | Versioned rules and evidence reasons | Reproducible scores and analyst review |
| Protect without excessive friction | Simulated verification and holds | Benign restriction rate and action outcomes |
| Resolve consistently | Persistent cases and recovery checks | Valid transitions, unresolved cases and closure evidence |
| Assess detection quality | Separate truth labels and held-out scenarios | Confusion matrix, precision, recall and false-positive rate |

## Demonstration
A fictional customer account shows compromised access, security changes, a new beneficiary and an attempted transfer. The analyst reviews evidence, records a disposition, simulates containment and completes recovery checks. Legitimate travel and device replacement provide comparison cases.

## Scope and delivery status
The V2 design is defined; implementation remains pending. The private repository retains the V1 broad fraud code baseline. Runtime success and UI verification are not confirmed here. The first V2 demonstration concentrates on one fictional institution rather than expanding the eight-bank comparison.

## Value hypothesis
Improved investigative context and consistent response are hypotheses. Synthetic evaluation cannot establish production accuracy, customer safety, actual financial savings or operational adoption. No ROI or loss-prevention result is claimed. See [V2 scope](V2_SCOPE.md) and [roadmap](ROADMAP.md).
