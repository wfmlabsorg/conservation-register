# The Labor Conservation Register

A public, append-only register of claims and forward calls about AI's effect on
contact-center and BPO labor, maintained by **WFM Labs Workforce Intelligence**.

Every forecast we make is registered here **before** its resolution window, with
a probability, a horizon date, and a named external referee. Every resolution —
hit or miss — is recorded. The scorecard and calibration curve regenerate from
the files in this repository alone. The willingness to be tracked and be wrong
is the point.

## How to verify a registration yourself (trust nothing we say)

1. **Find the record.** Each record is one canonical JSON file plus a readable
   Markdown rendering, e.g. `calls/FC-2026-0001.json` + `FC-2026-0001.md`.
2. **Find the commit that registered it:**
   ```
   git log --diff-filter=A --format='%H %cI' -- calls/FC-2026-0001.json
   ```
3. **Don't trust our timestamps — check GitHub's.** Git author/committer dates
   are settable by us; the **push** is attested by a third party. Check any of:
   - **GH Archive** (gharchive.org) preserves every public GitHub push event
     permanently — query the commit SHA.
   - **A dated publication:** each newsletter issue and quarterly Print states
     the register's head-commit SHA at press time. A third-party-archived
     publication carrying the SHA bounds every record beneath it in history.
   - The commit page on github.com.
4. **Confirm the content is what was registered.** Git SHAs are content hashes:
   `git show <commit>:calls/FC-2026-0001.json` is byte-for-byte what entered
   the register at that commit.
5. **Audit for tampering.** Records are append-only: corrections appear as
   dated amendment blocks inside the record, never as edits.
   `git log --follow <file>` exposes any rewrite.

## Layout

| Directory | Contents |
|---|---|
| `claims/` | Registered claim records (`CL-*`) — graded public AI-labor claims and standing wagers |
| `calls/` | Our forward calls (`FC-*`) — probability + horizon + named referee |
| `resolutions/` | Grading records, one per resolved claim or call |
| `retrospective/` | The retrospective baseline cohort — **physically separated, never merged** with prospective records |
| `scorecard/` | Generated: HIT/MISS/OPEN table + calibration curves, regenerated from this repo alone |
| `methodology/` | The methodology card, causal model, taxonomy versions, amendment policy, wager/bounty terms |

## Standing rules

- **Cohorts never merge.** The prospective register is the track record;
  the retrospective cohort is baseline evidence about the claim landscape,
  permanently labeled and separately scored. Wagers (no available referee)
  are excluded from the calibration curve entirely and say so.
- **Nothing publishes below filing-verified.** Every load-bearing number in a
  record traces to an SEC accession number, government series, or equivalent
  primary source, with the verbatim quote recorded.
- **A named human approves every record** before registration. There is no
  automated path into this register.
- **This repository is machine-written.** Commits to `main` are made by the
  publisher script (and scorecard regeneration) by design; the commit history
  *is* the notarization mechanism.

## What is *not* here

The quarterly intelligence briefing (the Print) is a separate, paid product.
This register makes the **accountability** public, not the analysis.

---
*WFM Labs · wfmlabs.com · register opened 2026*
