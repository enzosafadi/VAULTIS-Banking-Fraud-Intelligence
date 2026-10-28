# VAULTIS — V1 Local Verification
**Evidence recorded: 2026-10-28 | V1 software v0.1 | V2 remains planned**

## Evidence source and scope
The project owner ran the private V1 baseline locally on Windows with Python 3.13 in a dedicated virtual environment. The results below come from the supplied terminal transcript and actual running-app screenshot, not an independent CI rerun.

| Check | Observed result | Scope |
|---|---|---|
| Dependency installation | Successfully installed using Python 3.13 | Owner-provided terminal output |
| Existing unit tests | 6 passed in 5.18s | Existing V1 suite only |
| Local application launch | Streamlit served the app on localhost:8501 | Terminal and screenshot |
| Command Center rendering | Sidebar, metrics, charts and priority queue visible | Screenshot SS1 |
| Other workspaces and filter interactions | Not yet reviewed | Pending |
| V2 takeover workflow and case documentation | Not implemented | No V2 verification claimed |

## Reproduction commands used
Run from the repository folder in Windows PowerShell:
```powershell
py -3.13 -m venv .venv313
.\.venv313\Scripts\python.exe -m pip install -r requirements.txt
.\.venv313\Scripts\python.exe -m pytest -q
.\.venv313\Scripts\python.exe -m streamlit run app.py
```

Observed test output:
```text
......                                                               [100%]
6 passed in 5.18s
```

## Screenshot SS1 — V1 Command Center and local test evidence
![SS1: actual V1 dashboard with local passing-test and launch output](../screenshots/V1/SS1.png)

Original owner-supplied screenshot, published without generated content or alterations. It includes the app and terminal side by side. This is historical V1 evidence, not a V2 interface preview.

The visible 2,500 monitored events, 406 critical alerts, 904 high/critical events and 484 linked signals are outputs of the synthetic demonstration. They are not measured detection performance, real bank activity or prevented losses.

## Known compatibility findings
- The initial Python 3.15 environment attempted a pandas source build and failed because the build toolchain was unavailable. The Python 3.13 environment installed successfully. This does not establish support for all other Python versions.
- Streamlit emitted deprecation warnings for `use_container_width`, recommending `width='stretch'` or `width='content'`. The dashboard still rendered. Updating these calls remains a code-maintenance task; this documentation update does not fix them.
- An earlier interrupted environment creation was retried successfully. It is not counted as an application defect.

## Remaining checks
Inspect Fraud Investigations, Cross-Category Intelligence and Bank Network; exercise filters and empty selections; capture additional actual screenshots only after reviewing each view. Preserve the V1 runtime while implementing and evaluating the V2 account takeover workflow.

Passing six V1 tests and rendering one page do not validate fraud accuracy, persistent case handling, access control, recovery or protection of real accounts.
