# VAULTIS — Case Documentation Workspace
**Implemented local V2 demonstration**

Authorized-staff behavior is simulated through selectable demo identities. Every case has a journal for investigation notes, customer-contact summaries, evidence, decisions, handovers and recovery/closure records.

## Available features
- Required entry type, title and body; server-supplied author/time and case linkage.
- Synthetic event references validated against the selected case in the app.
- Durable SQLite save and reload, with draft retention on validation/storage errors.
- Search and filters by entry type, author and UTC created-date range.
- Linked corrections with reason, original preservation and stale-parent conflict checks.
- Idempotent submission tokens and application audit records.
- Reviewer-only reasoned closed-case addenda and documented reopening for new work.
- JSON case export with journal and action history; preparation is audited.

## Worked note
**Case:** CASE-evaluation-S04-000  
**Type:** Investigation note  
**Title:** Linked recovery change and transfer attempt  
**Body:** Observed a new-device login, contact change, beneficiary addition and transfer within seven minutes. This supports suspicion under ATO-SEQ-001. Verify using the prior trusted channel; record the outcome before recovery decisions.  
**Evidence:** select the four source event IDs from this account.

A subsequent Handover note can record the active simulated hold reference, outstanding recovery checks, uncertainty and receiving analyst. A note saying “release approved” cannot perform the release action.

## Boundaries and remaining work
There are no binary uploads, customer self-service portal, production sign-in or tamper-resistant storage. Follow-up owner/due-time details are free-text handover information, not a task scheduling engine. Permissions illustrate roles in a local demo. Report download completion is not tracked. See [manual](USER_MANUAL.md), [verification](VERIFICATION.md) and [feature matrix](V2_SCOPE.md).
