# Known issues — Budget Transparency

*Generated from `known_issues.json` by the known-issues skill's script; edit the JSON, never this file. Each issue is written the moment a problem comes up that the session could not solve on its own, with how to solve it; a solved one is marked done, never deleted.*

Every problem a session could not solve on its own in the budget-transparency project, each with how to solve it. Owner's part is in the Start here list; the session's part is worked through in priority order.

**1 open, 1 done.** Open by topic: Data access 1.

## Start here: your part

- Five minutes: KI-01 — download one budget data file (CSV/XLSX) from bundeshaushalt.de in your browser and drop it into this chat.

By where you do it:

- **This chat:** KI-01.
- **bundeshaushalt.de, in your browser:** KI-01.
- **Nothing from you** (the session's alone): none.

### How to send

- **Data files:** Download in your browser, then drag the file into this chat — or, if you work locally, commit it under data/ and push.

## Open issues

### Data access

- **KI-01 Budget data files cannot be downloaded by an automated session** (bundeshaushalt.de, bundesfinanzministerium.de). *Source access, opened 2026-11-03.* 2026-08-13: bundeshaushalt.de was blocked by the research environment's egress proxy. Re-checked 2026-11-03: the proxy now allows both federal domains, but bundeshaushalt.de (JSON API and static PDFs alike) and bundesfinanzministerium.de each answer HTTP 503 with a bot-protection 'Security Check' HTML page to non-browser clients. A browser session passes the check; curl/WebFetch do not.
  *Where:* TRACKER.md #1 (hands-on data verification) — blocked until a data file is in hand.
  *How to solve:*
  - **You**, *bundeshaushalt.de, in your browser*: Open https://www.bundeshaushalt.de/DE/Bundeshaushalt-digital/bundeshaushalt-digital.html and use the open-data download (CSV or XLSX). Quickest useful version: one file, budget year 2025, Soll. Optional: also 2024 Ist, for the plan-vs-actual angle. *Send:* The downloaded file(s) in this chat, or committed under data/.
  - **You**, *This chat*: Optional, only if no CSV/XLSX download exists on the page: say which download formats the page actually offers. *Send:* A short reply: 'KI-01: formats are …'.
  - **Me:** Before relying on the owner: try the Dezernat Zukunft Haushaltstracker dataset (their downloadable scientific dataset covers every Titel, ~10 years) and GovData-listed mirrors — neither tried yet as of 2026-11-03; they may serve the same data without bot protection.
  - **Me:** Once a file is in hand: inspect structure (Einzelplan/Kapitel/Titel columns, Soll/Ist), reproduce the official headline total for that year as a sanity check, record findings as RESEARCH.md Phase 2, close Tracker #1.
  - **Done when:** One full budget year at Titel level sits under data/ and its computed total matches the official headline figure.

## Done

- **KI-02 The project lives in the wrong repo — owner creates the dedicated one** (Project home): done 2026-11-03: owner created TK725/gov-budget-transparency; files pushed as a fresh initial commit (no shared history with the career repo); career-repo copy removed.

## See also

- TRACKER.md — backlog and session log
- DECISIONS.md — standing decisions
- RESEARCH.md — findings with sources
