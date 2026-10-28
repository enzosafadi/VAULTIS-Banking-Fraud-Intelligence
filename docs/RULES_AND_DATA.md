# VAULTIS — Rules and Data Dictionary
**Synthetic contracts | ato-rules-1.0**

## Rule catalogue
| Rule | Required ordered observations | Score |
|---|---|---:|
| ATO-SEQ-001 | Unfamiliar-device login → recovery-contact change → beneficiary addition → transfer to that beneficiary | 90 |
| ATO-SEQ-002 | Recovery-contact change → beneficiary addition → transfer, without the unfamiliar-login observation | 75 |

All required observations must share institution/account and session references, occur in order and fall within 15 event-time minutes of the transfer. Beneficiary references must match. Missing session references do not imply continuity. The strongest matched score is retained in one account alert, with all matched evidence IDs. Scores ≥85 are Critical; the other emitted score is High. Scores are not fraud probabilities.

Unfamiliar devices, location or payment amount alone do not trigger these rules. Low-value transfer sequences can trigger. Failed verification appears as evidence but is not a detector input bonus. A sequence with missing contact evidence can be missed; a legitimate urgent sequence can be flagged.

## Event fields
| Field | Meaning |
|---|---|
| event_id | Stable synthetic event identifier |
| institution / account_id | Correlation boundary |
| event_type | login, contact_change, beneficiary_added, transfer_attempt, verification_failed |
| event_time / ingested_at | Timezone-aware ISO timestamps; fixtures use UTC |
| session_id / device_id | Synthetic references; shared devices do not join different accounts |
| unfamiliar_device | Login-context flag in synthetic history |
| beneficiary_id / transfer_id | Payment destination and attempted-transfer references |
| amount / currency | Nominal attempted-transfer amount; CAD in V2 fixtures |
| quality_flag | Declared incomplete upstream evidence where applicable |

Identical duplicate deliveries are removed; conflicting payloads with the same institution/event ID are rejected. Ingestion order does not determine event order. Late arrival does not imply that the alert existed before its evidence was available.

## Separate simulation manifest
The manifest contains journey/account/institution, scenario, attack truth label and split. Ground truth is used only in evaluation, not operational case data or detection. Each evaluation account contains one authored journey, so the unit is an account journey, not individual events. This is a finite synthetic corpus, not general multi-journey production correlation.

## Case and note contracts
Cases store ID, institution, account, journey, status, owner, revision and response state. Journals store entry type/title/body, author, timestamp, linked evidence IDs, submission token, parent revision and correction reason. Evidence links are restricted to the current case by the application. JSON exports retain structured data; no executable spreadsheet export is supplied.
