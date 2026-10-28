# VAULTIS — Operator Manual
**v2.0.0-demo | Synthetic data only**

## Start and preserve your work
Extract V2 into a new Documents folder and keep V1. With Python 3.13 installed, double-click `launch.bat`. The launcher binds to localhost. To stop, press Ctrl+C in its terminal. Case data lives in `data/vaultis_v2.sqlite3`; preserve it between launches and back it up before upgrading. Changing the application files does not replace a local database.

## Workspaces
| Workspace | Use |
|---|---|
| Operations overview | Review accessible case counts, holds, closure and priority queue; filter status |
| Investigate a case | Select an account; inspect event timeline, reasons and quality flags |
| Case documentation | Log staff information and inspect revision history |
| Detection evaluation | Inspect truth-labelled scenario outcomes, metrics and failure modes |
| Operator guide | Follow the simulated case-resolution sequence |

## End-to-end takeover walkthrough
1. Keep demo identity ANALYST-01 and select CASE-evaluation-S04-000 in Investigate a case.
2. Inspect the ordered login, contact change, beneficiary and transfer evidence. Scores establish suspicion, not proof.
3. In Response & recovery, select Start review, enter a rationale and submit.
4. Request verification, then record Verification failed for this attack demonstration.
5. Place simulated hold; revoke sessions and reset credentials using the separate actions.
6. Select Complete recovery review, check prior trusted-channel verification and recovery-contact restoration, enter rationale and submit.
7. Switch to LEAD-01, return to the same case and release the simulated hold.
8. Close case as Confirmed takeover with a rationale. Inspect the retained audit history and prepare/download its JSON report.

Each action requires its own submission. Disabled-by-policy combinations are rejected and logged. These actions do not contact or affect a bank. Simulated checks are recorded operator assertions, not externally verified results.

## Documentation and handover
In the Documentation tab or workspace, select type, title, body and evidence links, then Save journal entry. Use facts, interpretation, uncertainty and next step. Customer-contact notes use synthetic summaries only. A handover should name outstanding work and the receiving staff identity in its text.

Search text and filter type, author or created-date range. Corrections select the latest entry revision and require a reason; original content is retained. Save errors retain the draft. Closed cases accept reviewer addenda with reasons; further investigation requires reviewer reopening.

## Demo roles
Analysts operate their assigned cases. Reviewers can reassign, release recovered holds and reopen cases. Support staff can read case context and add customer-contact notes, but cannot execute response actions or export full cases. These are UI/backend role demonstrations without authentication; do not expose the server or use real customer information.

## Evaluation and interpretation
Detection evaluation deliberately reveals truth labels separately from the operational workspace. Clearing a false-positive case does not erase that detection failure. Read precision/recall with scenario counts and known misses. There is no real-time monitoring, live enforcement or guarantee that an unflagged account is safe.
