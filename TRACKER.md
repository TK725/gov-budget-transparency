# TRACKER — Budget Transparency

> **Rules:** Item numbers are stable IDs — never renumbered, never reused; the list is sorted by priority, so "what's next?" = read `Next up` from the top. A problem a session cannot solve goes into `known_issues.json` **the moment it comes up** (see the `known-issues` skill), never at the end of the task. Append a session-log entry at the end of EVERY session.

## Next up

| # | Task | Status | Depends on |
|---|------|--------|------------|
| 1 | **Hands-on data verification**: get one full budget year at Titel level and inspect it. First try the session route (Dezernat Zukunft dataset / GovData mirrors — KI-01 `me` steps); official federal sites bot-block automated clients. | in progress (blocked on data file, see KI-01) | KNOWN_ISSUES KI-01 |
| 10 | **Work the open known issues** — the owner's part is the "Start here" list in `KNOWN_ISSUES.md` (currently: KI-01, download one data file in your browser). | open | — |
| 8 | **Sondervermögen deep-dive**: current list of active special funds, where each Wirtschaftsplan is published, whether machine-readable. Clears the `[verify]` markers in RESEARCH.md. | not started | — |
| 2 | **Concept & differentiation**: study Dezernat Zukunft's Haushaltstracker hands-on; define what this project does that it doesn't (candidate angle: accountability layer — Soll-vs-Ist deviations, quiet year-over-year changes, Sondervermögen consolidation, plain-language Titel explanations). Decide MVP. | not started | 1 (partially startable now) |

## Unblocks

| # | Task | Waiting on |
|---|------|-----------|
| 3 | **First local analysis/prototype**: load one year's full Titel-level data, reproduce the headline numbers, build 2–3 first visualizations locally. | #1 (data in hand) |

## Later

| # | Task | Depends on |
|---|------|------------|
| 6 | Define "logic checks" concretely: which checks are computable from the data (plan-vs-actual deviation ranking, largest silent shifts, überplanmäßige Ausgaben), which need external data (promises, coalition agreement). | 2 |
| 4 | Stack & hosting decision: static site vs. app; hosting; cost check against the small-budget constraint. | 2 |
| 9 | Name & domain brainstorm. | 2 |
| 5 | Website legal checklist: Impressum, DSGVO/analytics choice, DL-DE BY 2.0 attribution wording on every data page. | 4 |
| 7a | **Flip this repo public** — only after the GUARDRAILS "going public" checklist and #5 are done. | 5 |

## Done & absorbed

| # | Task | Outcome |
|---|------|---------|
| 7 | Own repo migration: move the project out of the private career repo into a dedicated repo. | Done 2026-11-03 — this repo (`TK725/gov-budget-transparency`), pushed with fresh history, zero commits shared with the career repo (KI-02). The remaining "go public" gate became #7a. |

## Session log

- **2026-08-13** — Project founded (inside the career repo). Phase 1 feasibility research done (see RESEARCH.md): budget is fully public down to Titel level, machine-readable (JSON API + CSV), legally reusable under DL-DE BY 2.0 / § 5 UrhG; main existing player is Dezernat Zukunft's Haushaltstracker (active), offenerhaushalt.de discontinued. Foundation files created. Next: #1 hands-on data verification.
- **2026-11-03 (a)** — Setup upgraded to the current project-setup standard: added LESSONS.md, known_issues.json + KNOWN_ISSUES.md (known-issues skill), restructured this tracker into Next up / Unblocks / Later / Done, seeded conventions into CLAUDE.md/DECISIONS.md, logged D7 (skills repo as single skill source). Re-checked the August blocker: egress proxy now allows the federal domains, but both bot-block automated clients (HTTP 503 Security Check) → opened KI-01 with a browser-download path for the owner and a Dezernat-Zukunft/GovData route for the session.
- **2026-11-03 (b)** — **Moved to this dedicated repo** (`TK725/gov-budget-transparency`): owner created it (KI-02), files pushed as a fresh initial commit with no shared history with the career repo; career-repo copy removed. CLAUDE.md/GUARDRAILS.md adapted for standalone life; #7 closed, #7a (flip public) added. Next: #1 via the KI-01 `me` route (Dezernat Zukunft dataset), or owner delivers a file.
