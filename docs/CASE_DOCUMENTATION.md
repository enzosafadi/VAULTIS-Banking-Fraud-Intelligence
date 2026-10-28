# VAULTIS — Case Documentation Workspace
**Documentation V2 | 2026-10-28 | Planned; not implemented**

## Purpose and users
Give authorized financial-institution staff a dedicated place inside each account takeover case to log observations, investigation findings, customer-contact summaries, decisions and handover instructions. Here, users means analysts, reviewers and support staff working the case. A customer self-service reporting portal is outside this feature's current scope.

## Workspace
Each case includes a Documentation tab with an entry composer, searchable chronological journal, linked evidence, decision records and a handover summary. The journal is distinct from the automatically generated event timeline, but entries can link to those events.

| Entry type | Information to log |
|---|---|
| Investigation note | Observed facts, interpretation, uncertainty and next step |
| Customer-contact summary | Simulated contact channel, time, verification outcome and relevant account-holder statement |
| Evidence reference | Synthetic event/document ID, source and relevance |
| Decision | Disposition, evidence references, rationale and reviewer where required |
| Handover | Current risk, outstanding work, next owner and follow-up time |
| Recovery/closure note | Completed checks, unresolved concerns and outcome |

## Entry contract
Required fields: entry ID, case ID, institution ID, entry type, title, body, author identity, created-at timestamp and revision number. Optional fields: observed-at time, referenced event/action/document IDs, assigned follow-up owner and due time. Timestamps are stored in UTC and displayed with a stated timezone. Author identity and creation time come from the application context rather than editable free text.

The first local demonstration may use clearly labelled simulated staff identities; selecting a demo identity is not authentication. Enforced user permissions require an authenticated application context.

## Save, correction and retrieval
- Validate required fields and referenced evidence belongs to the same authorized institution/case.
- Preserve draft text if saving fails; show Saved only after durable persistence succeeds.
- Deduplicate retried submissions using a stable submission identifier.
- Submitted entries retain their original content. Corrections create a linked revision with editor, time and reason; the original remains available.
- Record who submitted, corrected, reviewed or exported an entry. Staff cannot silently overwrite or delete the audit history.
- Search and filter authorized case entries by text, type, author and date. Render user text safely without executing embedded HTML.
- Persist entries across reloads and sessions. Detect concurrent revisions and require the editor to resolve conflicts rather than overwrite newer work.
- Allow an authorized case report export containing notes, revisions and evidence references; audit the export. Exported text must not cause spreadsheet formulas to execute if CSV output is supported.

## Roles and case lifecycle
Analysts contribute to assigned/authorized cases. Reviewers can review decisions and add supervisory notes. Support roles may contribute permitted contact summaries without unrestricted access to unrelated investigations. A production role model is planned, not currently present in V1.

Closed cases are read-only for ordinary contributions. A reviewer can add a labelled addendum with a reason; further investigation requires documented reopening. A note that says "hold released" does not perform a release: protective actions remain separate validated workflow operations.

## Worked journal example
**Case:** CASE-ATO-001, fictional account A-1042. **Author:** Analyst DEMO-07, simulated identity. **Created:** 09:12 on the scenario day, America/Toronto.

**Type:** Investigation note  
**Title:** Contact change and beneficiary addition precede transfer attempt  
**Facts:** E-001 records an unfamiliar-device login; E-002 records the recovery-phone change; E-003 records beneficiary B-778; E-004 records the CAD 4,800 attempt.  
**Interpretation:** The seven-minute sequence warrants review under candidate rule ATO-SEQ-001. It does not establish confirmed fraud or a settled loss.  
**Next step:** Perform simulated verification through the previously established trusted channel. Record the result separately and escalate if unresolved.  
**Evidence links:** E-001, E-002, E-003, E-004.

A later handover entry records the verification outcome, any simulated containment action ID, outstanding recovery checks and the receiving analyst. It must not silently alter the earlier observation.

## Why it helps
The next analyst can see what was checked, which evidence supported a decision, what remains uncertain and who owns the next step. A reviewer can reconstruct the case without relying on scattered messages. These are intended benefits; handling-time savings and review quality have not been measured.

## Acceptance criteria
1. A valid note saves once, survives reload and shows its author, time and linked case.
2. Empty submissions, unrelated evidence links and unauthorized writes are rejected.
3. A save failure retains the draft and does not claim success.
4. A correction preserves the original, revision author, timestamp and reason.
5. Concurrent edits surface a conflict; retries do not duplicate entries.
6. Text search and filters retrieve only authorized records.
7. Closed-case edits follow the addendum/reopening rules.
8. Notes cannot bypass recovery checks or execute protective actions.
9. A case export includes the selected documentation history and records the export event.
10. The demonstration uses synthetic information only; real customer documents, credentials and banking records are not uploaded.

## References and status
See [V2 scope](V2_SCOPE.md), [use case](USE_CASE.md) and [roadmap](ROADMAP.md). This specification adds a V2 requirement; the documentation workspace, permissions and persistence are not yet implemented in the V1 application. The first demonstration uses synthetic text and evidence references. Binary document uploads and their storage controls are deferred.
