# VAULTIS — Verification Record
**2026-10-28 | v2.0.0-demo**

## V1 owner-side evidence
Windows/Python 3.13 dependency installation succeeded; the six original tests passed in 5.18s. The owner ran the app locally and supplied actual dashboard and investigation captures. Later captures confirm the readable v0.1.2 layout and ascending fraud-type bars. See [gallery](SCREENSHOTS.md).

The V1 Python 3.15 attempt failed during a pandas source build. Streamlit also warned about deprecated width arguments. V2 uses the newer width API with a raised Streamlit minimum. No V2 Windows execution is claimed yet.

## V2 automated validation
24 tests pass in the development environment, including the six retained V1 checks, eight detector tests, eight case-store tests and two Streamlit interaction tests. Coverage includes unrelated-account isolation, event ordering, duplicates, session/beneficiary boundaries, missing evidence, legitimate false positives, stale versions, role restrictions, denied actions, note revisions, reload persistence, closed-case rules and exports. AppTest opens all five workspaces; note validation retains the draft and a saved note survives rerun.

Reproduce with:
```powershell
.\.venv313\Scripts\python.exe -m pytest -q
.\.venv313\Scripts\python.exe scripts\validate_demo.py
```

The walkthrough uses a temporary database and completes note → review → failed verification → simulated hold → session/credential reset → recovery → reviewer release → confirmed-takeover closure → JSON export. It does not modify the operator database.

## Synthetic evaluation
[Machine-readable summary](../reports/EVALUATION.json): seed 42; 120 account journeys; 60 attacks and 60 legitimate journeys; 438 delivered records, 426 unique events, 12 duplicate deliveries removed. Rules: ato-rules-1.0; 15-minute event-time window.

| TP | FP | TN | FN | Precision | Recall | False-positive rate |
|---:|---:|---:|---:|---:|---:|---:|
| 54 | 12 | 48 | 6 | 81.8% | 90.0% | 20.0% |

Missing contact evidence causes six misses. Urgent legitimate sequences cause twelve false positives. Development seed 7 and evaluation seed 42 share authored scenario families; this is not independent real-bank validation. No timing reduction, ROI, real prevented loss or bank adoption is measured.

## Remaining acceptance
Automated Streamlit interactions are not a rendered desktop visual review. V2 Windows launch, browser layout review and actual V2 captures remain pending. Browser screenshot tooling could not be installed in the development environment; no V2 screenshots were fabricated. The launcher is supplied for the owner's local check.
