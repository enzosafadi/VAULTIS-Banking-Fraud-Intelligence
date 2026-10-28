# VAULTIS — Documentation Change Log

## Software v0.1.2 — ascending fraud-type bars — 2026-10-28
- Sort severity bars by alert count from lowest to highest within each fraud type; retain stable severity colors and legend.
- Recalculate positions under filters; preserve gaps and numeric labels.
- Automated Streamlit checks confirmed ascending counts in all three groups and with a severity subset. Owner-side visual review remains pending.
- Preserve v0.1.1 source on `archive/v0.1.1-before-ascending-bars` in the private repository. V2 remains planned.

## Software v0.1.1 — chart readability — 2026-10-28
- Give each Command Center chart its own full-width row.
- Separate grouped severity bars, use stable severity colors and show counts.
- Increase bank-row spacing, sort by score and display numeric score labels on a fixed 0–100 axis.
- Preserve the preceding private source on `archive/v0.1-before-chart-spacing`.
- Validation: six existing tests passed; Streamlit AppTest loaded the Command Center and checked single-bank and empty-filter states.
- Owner-side visual confirmation of this patch is pending. SS1 remains an accurate historical screenshot of v0.1, not v0.1.1. V2 remains planned.

## Verification evidence — 2026-10-28
- Record owner-provided Windows/Python 3.13 installation, six passing V1 tests (5.18s), local launch and Command Center rendering.
- Publish actual screenshot SS1 under screenshots/V1; other workspace captures remain pending.
- Record Python 3.15 installation failure and Streamlit width deprecation warnings without claiming a code fix.
- Preserve the pre-update repository state on archive/pre-verification-2026-10-28. V1 documentation archives and runtime code remain unchanged.

## V2 — 2026-10-28
- Specify a case documentation workspace for staff notes, contact summaries, evidence, decisions and handovers, with persistence, authorship, revision history and acceptance checks; implementation pending.
- Add UC-ATO-001: fictional event timeline, explicit candidate suspicion trigger, legitimate comparisons, analyst response, institutional usefulness and acceptance evidence.
- Select account takeover detection and response for digital banking as the single project orientation.
- Replace broad phishing/card/identity monitoring as the active roadmap with one connected investigation and recovery journey.
- Define synthetic scenarios, case workflow, simulated protective actions and evaluation gates.
- Distinguish approved design from the existing unverified V1 v0.1 software baseline.
- Preserve the exact preceding README and documentation in docs/V1, including their historical claims.
- Keep private implementation and public portfolio documentation separate; repository visibility is unchanged.

V2 is a documentation and direction revision, not a software v2.0 release. Application code, dependencies and existing tests are unchanged by this revision.

## V1 — preserved historical baseline
Original broad multi-bank fraud prototype documentation, referring to software v0.1. See [V1 archive](docs/V1/README.md). Archived claims are historical and do not establish current runtime verification.
