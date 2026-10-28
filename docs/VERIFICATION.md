# VAULTIS — Verification Record
**2026-10-28 | Current software: v2.0.1-demo**

## Current verified state
| Check | Result | Evidence scope |
|---|---|---|
| Automated suite | 26 passing tests recorded | Development environment; code matches committed source |
| Synthetic walkthrough | Completed note → containment → recovery → reviewer release → closure → export | Reproducible temporary-database workflow |
| Windows launch | Confirmed | Owner-side runtime and screenshots |
| Populated V2 overview | Confirmed | [Actual V2 SS1](../screenshots/V2/SS1.png) |
| Other V2 workspaces | Automated interactions checked | Owner-side visual acceptance and captures pending |

## Automated coverage
The suite contains six retained V1 tests, eight temporal-detector tests, eight case-store tests, two Streamlit UI tests and two starter-history tests. It covers account/session/beneficiary isolation, event ordering, duplicates, missing evidence, false positives, stale revisions, role checks, denied actions, note corrections, durable reload, closed-case handling, exports, startup idempotence and preservation of operator work.

Streamlit AppTest opens all five workspaces, checks an unassigned identity, retains a note draft on validation failure and confirms saved notes survive rerun. These checks do not replace a desktop visual review.

Reproduce from the project folder:
```powershell
.\.venv313\Scripts\python.exe -m pytest -q
.\.venv313\Scripts\python.exe scripts\validate_demo.py
```

The walkthrough runs in a temporary database and does not alter the operator's saved cases. Simulated recovery checks are recorded assertions, not verification by a bank.

## Detection evaluation
[Machine-readable summary](../reports/EVALUATION.json): seed 42; 120 account journeys; 60 attack and 60 legitimate journeys; 438 delivered records, 426 unique events, 12 duplicates removed; ato-rules-1.0; 15-minute event-time window.

| TP | FP | TN | FN | Precision | Recall | False-positive rate |
|---:|---:|---:|---:|---:|---:|---:|
| 54 | 12 | 48 | 6 | 81.8% | 90.0% | 20.0% |

Missing contact evidence causes six misses. Urgent legitimate sequences cause twelve false positives. Development and evaluation seeds differ but share the same authored scenario families. These figures do not estimate real-world accuracy, customer safety or prevented loss.

## Populated operating history
[Startup summary](../reports/DEMO_ACTIVITY.json) records the fresh-database state: eight active simulated holds and twelve closed cases. These counts derive from validated saved actions and case records, with labelled fictional notes and audit history. Repeat starts do not duplicate the activity. Existing operator notes and changed cases are skipped rather than overwritten.

The owner applied v2.0.1, restarted Streamlit and supplied SS1 showing the expected counts and closed/released rows. This verifies the Windows overview and populated startup.

## Historical baseline
The V1 owner-side Python 3.13 run reported six tests passed in 5.18s and rendered the original dashboard/investigation views. The earlier Python 3.15 setup failed while building pandas. V1 width warnings were addressed by the new V2 UI's width API and raised Streamlit minimum. See [historical evidence](HISTORY.md).

## Remaining acceptance
Review the V2 active investigation, documentation, response/recovery and evaluation layouts on the owner's computer. Capture populated current-version screenshots before using them in LinkedIn or Upwork materials. A current overview is available now; additional captures must not be fabricated or replaced with V1 images.

Production authentication, live bank integrations, security hardening and independent real-data validation are outside this local demonstration.
