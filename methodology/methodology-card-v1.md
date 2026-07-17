# Methodology Card — v1

**WFM Labs Workforce Intelligence · Labor Conservation Register**
*This card is the promise. Every quarterly issue is checked against it; a change to
anything here is a dated amendment, never a silent edit.*

## What this is

We register claims and forecasts about AI's effect on contact-center and BPO labor
**before** their resolution windows, in a public, append-only repository where the
commit history is the timestamp. Every forecast carries a numeric probability, a hard
horizon date, and an external referee named at issue. Every resolution — hit or miss —
is recorded. We publish our calibration, not our highlight reel.

## The causal model (and its honesty clause)

We model AI's labor effects as: capability (measured by third-party benchmark data)
enabling deployment (which we cannot observe directly and proxy through corporate
language and hiring patterns), which produces two effects — absorption of simple
work, and concentration of harder residual work. We track both through audited
financials, mandated disclosures, and posting composition. We explicitly model what
else moves these numbers — the business cycle, acquisitions, offshoring — and our
design choices (control sectors, composition-over-level metrics, boundary-event
exclusions) exist to separate those from AI effects. **Public data cannot prove
*why* any single company cut jobs, and we never claim it can.** What it can show is
whether claimed reductions are visible anywhere in the system — and that is the
question we score. We grade *their* stated attribution; we never assert our own.

## Forecast policy

- **Every registered call carries:** numeric probability · hard horizon date ·
  external referee named at issue · a complete six-slot argument record behind it.
  A call missing any of these is an opinion, and opinions don't enter the register.
- **Three states, nothing evaporates:** OPEN → HIT | MISS. No quiet deletions.
  A call whose referee source ceases to exist gets a dated amendment naming a
  successor referee, or resolves MISS.
- **Calibration over batting average:** we grade whether ~70% of our 70% calls land,
  published as a calibration curve with Brier scores, updated quarterly. A
  well-calibrated forecaster at 70% *should* miss 3 in 10 — a miss is the system
  working.
- **Three cohorts, never merged:**
  - **Prospective** — pre-registered via this repository. "Our track record" refers
    to this cohort only.
  - **Retrospective** — historical claims (2023-01→2025-06) with elapsed windows,
    graded at launch under a mechanical selection rule published *before* grading
    (see disclosure below). Permanently labeled; separate directory; separate curve.
  - **Wagers** — claims with no available public referee, bounty-backed, excluded
    from all calibration curves, described as wagers everywhere they appear.

## Referee policy (including the self-referee problem)

External referees in preference order: SEC filings > government series (BLS/WARN) >
official company disclosures > industry bodies (DIRECTIONAL tier only). Where a call
resolves against our own posting mix-index, three mitigations apply: (1) the
taxonomy and classifier version are published and frozen at registration; (2) raw
data is retained so anyone can recompute the ratio; (3) a government co-referee
(OES Customer Service Representatives series / JOLTS) is paired at its slower
cadence — if the co-referee and our index disagree at resolution, **the call
resolves on the co-referee** and the divergence is published.

## Verification floor

Nothing publishes below **filing-verified**: every load-bearing number traces to an
SEC accession number, government series, or equivalent primary source, with the
verbatim quote recorded. Filers round; we record their language ("approximately
455,000", "over 60,000") and never invent precision an instrument doesn't support.
Aggregators are cross-checks, never sources. Reporting-boundary events (M&A,
divestitures) are excluded by a published event table, never silently adjusted.

## Retrospective-scoring disclosure

Retrospective grading cannot prove the grader ignorant of outcomes. That is exactly
why the retrospective cohort exists as *baseline evidence about the claim landscape*,
not as *evidence of our foresight*. The claim universe is defined by rule, not
judgment — a fixed source set, a fixed window, captured by the same extraction
patterns as the prospective register (discovery via Bellingcat's `edgar-tool`,
version pinned; the exported result set is retained raw so the sweep is re-runnable
by anyone). Every claim matching the rule enters; no claim is dropped without a
published exclusion note.

## Abandonment conditions (the thesis is a prior, not a doctrine)

The standing dark-signal pattern: aggregate panel breach **plus** class-neutral mix
shift everywhere **plus** control-arm co-movement = macro (thesis unaffected). Breach
**with** treatment-only, frontline-biased mix shift = deflection arriving — the
Thesis Tracker moves to *strained*, and two consecutive quarters moves it to
*breaking*, in print. Evidence against ourselves is reported fast, prominently, and
converted into better instrumentation.

## Data sources & licensing

| Source | Use | License / terms | Status |
|---|---|---|---|
| SEC EDGAR (submissions, XBRL, full-text, documents) | Panel financials, headcount, language track | U.S. Government work — public domain; fair-access ≤10 req/s, declared UA | In use |
| Epoch AI datasets | Capability trajectory (exogenous root) | CC-BY (attributed) | In use |
| WARN Firehose / openICPSR backfill | Displacement events | Free tier / academic redistribution | Planned (collectors) |
| edgartools (MIT) | Filing section/segment parsing, subprocess | MIT | Planned |
| Bellingcat `edgar-tool` v2.1.2 | Retrospective claim-sweep discovery, panel-orbit RSS | GPL-3.0 — unmodified CLI at a process boundary; never vendored | Approved 2026-07-17 |
| Earnings-call transcripts | Language track | Hybrid (official IR + licensed API + own ASR of public webcasts); **published quotes always trace to our own transcription or official company transcripts** | Pending tier approval (D5) |
| Job-posting data (mix-index) | Concentration instrument | Provider ToS review precedes first use; taxonomy + classifier versions published | Pending build |

## Amendment policy

Records are append-only. Post-registration corrections are dated amendment blocks
inside the record file — never edits. The git history of this repository is the
audit trail; every file reads correctly without it. How to verify any registration
yourself: see the repository README.

---
*v1 — registered at the Gate 2 sitting of 2026-07-17. The head-commit SHA of this
registration is printed in the next dated publication.*
