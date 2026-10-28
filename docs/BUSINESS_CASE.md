# VAULTIS — Business Case
**Account takeover detection and response | v2.0.0-demo | Simulation**

## Problem and intended users
A login anomaly, recovery-contact change, new beneficiary and transfer attempt can appear in separate systems. A fraud analyst needs to understand the sequence, distinguish suspicion from proof, coordinate a proportionate response and leave a clear recovery record for colleagues.

The demonstration serves fraud analysts, fraud operations reviewers and support staff. One fictional institution, Northbridge Financial, is used to keep the workflow focused.

## Solution and institutional usefulness
| Operational need | Implemented demonstration | Evidence / limitation |
|---|---|---|
| Recognize linked activity | Account-scoped temporal rules and source-event timeline | Rule tests; incomplete evidence still creates misses |
| Explain prioritization | Rule version, matched events, score and reasons | Heuristic signals, not calibrated probabilities |
| Coordinate response | Persisted cases and simulated verification/containment | No real transfer or session enforcement |
| Preserve staff knowledge | Case notes, contact summaries, corrections, handovers and filters | Local SQLite; no production identity system |
| Complete recovery consistently | Required recovery checks and reviewer release | Executed synthetic walkthrough |
| Review decisions | Recorded action history and JSON report | App-level history, not tamper-proof evidence storage |

## Example suspicion trigger
An unfamiliar-device login at 09:02, recovery-phone change at 09:04, new beneficiary at 09:06 and CAD 4,800 transfer attempt at 09:09 are suspicious together. A 15-minute account/session sequence links the events. Each event alone can be legitimate. See the [worked use case](USE_CASE.md).

## Evidence of progress
The application and automated walkthrough are implemented. On a 120-journey synthetic set, detection produces 54 TP, 12 FP, 48 TN and 6 FN. False positives arise from an urgent legitimate sequence; missing evidence hides some attacks. These outcomes show both the mechanism and its limits, not real-bank effectiveness.

## Value hypothesis
The intended benefits are less context gathering, consistent response decisions and clearer handovers. No analyst-time study, adoption, real prevented loss or ROI has been measured. Actual institutional use would require authorized integrations, independent validation, security engineering and an approved operating policy.
