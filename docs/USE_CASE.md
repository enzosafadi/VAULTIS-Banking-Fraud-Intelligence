# VAULTIS — Account Takeover Use Case
**UC-ATO-001 | Documentation V2 | 2026-10-28**
**Fictional scenario and proposed system behavior; not an executed test or measured result.**

## Business purpose
Help a financial institution recognize a connected attempt to take over an existing digital banking account, investigate the evidence, and coordinate a proportionate response before completing recovery. The central question is: does this sequence fit the customer's normal activity, or does it warrant verification and containment?

## Actors and starting conditions
- Institution: Northbridge Financial, a fictional bank.
- Customer: synthetic customer C-1042; account A-1042.
- Primary actor: fraud analyst; escalation actor: fraud operations lead.
- Supporting roles: simulated customer-support and security functions.
- Data: synthetic account history, authentication events, security changes, beneficiary records and transfer attempts.
- Preconditions: event IDs are unique; institution/account references match; timestamps and data quality are inspectable. No real bank integration is assumed.

## Normal activity used for comparison
The synthetic 60-day history shows a familiar mobile device, stable contact details and recurring domestic CAD payments to existing beneficiaries. Routine transfers range from CAD 100 to CAD 900. This is an example account baseline, not a general banking threshold.

The scenario generator labels this journey as an attack for evaluation. The detector must not read that label or assume that stolen credentials are directly observable.

## Example event timeline
All times below are on a fictional simulation day in America/Toronto. Amounts are CAD.

| Time | Event ID | Observable event | Why it matters |
|---|---|---|---|
| 09:02 | E-001 | Successful login from a device absent from the account history | New context merits attention, but can be legitimate |
| 09:04 | E-002 | Recovery phone changed during that session | Changes how the bank could verify the customer |
| 09:06 | E-003 | New transfer beneficiary B-778 added | Establishes a new destination for funds |
| 09:09 | E-004 | CAD 4,800 transfer attempted to B-778 | Follows the preceding changes within seven minutes and exceeds this account's synthetic routine range |
| 09:10 | E-005 | Simulated independent verification fails | Adds evidence requiring continued review; failure alone does not prove takeover |

E-004 is an attempted transfer, not evidence that funds settled or were lost. The sequence must be joined using institution, account, session and beneficiary references where available. Similar timing on unrelated accounts must not create a combined case.

## What triggers suspicion?
**Illustrative candidate rule ATO-SEQ-001:** raise a priority investigation when an account has a new-device login, a recovery-contact change, a new beneficiary and a transfer attempt to that beneficiary within a 15-minute event-time window.

The 15-minute window is a design parameter for synthetic testing, not a validated bank policy. The unusual amount is additional context; the sequence rule must also be tested with smaller transfer attempts. E-004 completes the proposed trigger. E-005 strengthens the case after the initial alert.

The concern comes from the combination: access from an unfamiliar device, a change to recovery control, creation of a destination and an immediate attempt to move funds. None of these events independently establishes fraud. Travel, a replacement phone or an urgent legitimate payment can explain parts of the sequence.

If required signals are absent, this rule may not fire. Other scenarios, including hijacked existing sessions, need separate tested rules. Duplicate events must not add evidence weight. Late events should trigger a documented reevaluation with both event and ingestion times visible.

## How an analyst would use VAULTIS
| Stage | Planned VAULTIS behavior | Analyst responsibility / evidence |
|---|---|---|
| Detect | Correlate the sequence and attach rule version and source event IDs | Review why the alert exists; distinguish observation from inference |
| Investigate | Present one account timeline alongside the synthetic baseline | Inspect event provenance, session continuity, beneficiary and amount context |
| Decide | Show evidence reasons, missing signals and permissible actions | Record suspected takeover, benign explanation or insufficient evidence |
| Verify | Simulate verification through a previously established trusted channel | Do not rely only on the newly changed phone; record the simulated outcome |
| Contain | Record a simulated transfer hold and session-revocation request | Confirm target transfer/session, authority and outcome; prevent duplicate actions |
| Escalate | Keep unresolved verification open for lead review | Document uncertainty and the reason for escalation |
| Recover | Require simulated credential/session and recovery-contact checks | Record completion and authorized disposition of the original hold |
| Close | Retain disposition, evidence, action history and recovery outcome | Close only after required checks; unresolved work stays open |

For the attack fixture, the intended demonstration outcome is a suspected-takeover case with simulated containment, followed by a separately documented recovery review. A simulation may show an attempted cash-out being interrupted, but that is not proof of prevented real-world loss. A timeout or failed action must be recorded as such, rather than displayed as successful protection.

## Legitimate comparison
The same customer buys a new phone, logs in while travelling and sends an ordinary payment to an existing beneficiary. That is not a complete match for ATO-SEQ-001. It must not be escalated by this rule solely because the device or location changed.

A harder benign fixture deliberately includes a contact update, new beneficiary and urgent payment. It can match the sequence and produce a false-positive alert. Successful simulated verification and analyst review should provide a path to clearance and authorized release, with the restriction and inconvenience counted in the evaluation.

## Why this is useful to a financial institution
| Operational problem | Planned VAULTIS contribution | How usefulness would be assessed |
|---|---|---|
| Related events live in separate views | One ordered investigation timeline with traceable evidence | Correct linkage; analyst time to assemble context |
| Analysts struggle to explain priority | Explicit rule and contributing evidence | Reproducible decisions and evidence completeness |
| Response differs between analysts | Defined verification, escalation and recovery workflow | Correct transitions and completed required checks |
| Protective actions can inconvenience legitimate customers | Contextual review and documented clearance path | False-positive rate; benign restrictions and unresolved holds |
| Case closure lacks a clear record | Persistent decisions and action history | Traceability from alert through recovery and closure |

These are proposed operational benefits, not verified improvements. VAULTIS would support a bank's fraud process; actual protection would require authorized integrations, reliable data and a validated operating policy.

## Acceptance evidence to produce
1. The attack fixture creates one correlated case after E-004 with E-001 through E-004 and rule version visible.
2. E-005 updates the same case without duplicating the alert or overwriting earlier evidence.
3. An unrelated account's events never complete this account's sequence.
4. Routine travel/new-device activity alone does not satisfy ATO-SEQ-001.
5. The hard benign fixture is recorded as a false-positive alert when it triggers; successful clearance does not erase it from detection metrics.
6. Case notes, simulated actions and recovery decisions survive reload.
7. Duplicate holds are idempotent; release without required recovery review is denied and audited.
8. Missing/late evidence and simulated action failures remain visible.
9. A held-out scenario report records TP, FP, TN and FN, plus customer-friction outcomes. No numerical success target is claimed before baseline evaluation.

## Implementation status and references
This document specifies intended V2 behavior. The existing software is the V1 v0.1 broad fraud prototype; the workflow above is not yet implemented or verified.
See [V2 scope](V2_SCOPE.md), [roadmap](ROADMAP.md) and the [V1 archive](V1/README.md).
