# CLAUDE.md — Budget Transparency project

Side project of the repo owner: make the German federal budget (Bundeshaushalt) more transparent and understandable for ordinary citizens and journalists — collect openly available data, categorize it, visualize it, run logic checks (plan vs. actual, year-over-year changes), and publish it as a free, non-commercial public-service website.

**Phase: RESEARCH done → HANDS-ON DATA next** *(update this line when it changes)*

**This repo is private for now.** Going public is a later, deliberate step (DECISIONS.md D4, Tracker #7a) gated by the GUARDRAILS.md checklist — nothing in here may assume it stays private forever: write every file as if it will eventually be read publicly.

## Start here, in this order
1. `LESSONS.md` — the Rules section is the 30-second "what to avoid" read; read it before writing anything.
2. `TRACKER.md` — priority-sorted backlog + session log. "What's next?" = read `Next up` from the top. Append a session-log entry at the end of every session.
3. `PROJECT_BRIEF.md` — goal, scope, phases.
4. `DECISIONS.md` — standing decisions; never re-litigated without new input from the user; changes supersede as new rows.
5. `RESEARCH.md` — all research findings with sources; append new phases, don't rewrite history.
6. `GUARDRAILS.md` — read before writing anything intended for publication.
7. `KNOWN_ISSUES.md` — what's open and the owner's part (generated from `known_issues.json`; see below).

## Operating conventions
- **Solve it, or write it down at once.** A problem the session meets is solved by the session first (another route, a later retry, what the user already has, a tool it can install); one it cannot solve goes into `known_issues.json` **the moment it comes up**, never at the end of the task, with the owner's exact steps, the session's steps, and the done-when check — then regenerate `KNOWN_ISSUES.md` via the **`known-issues`** skill's script. The tracker keeps one row (#10) pointing at it.
- **Every mistake becomes a LESSONS.md entry** (what happened → why → how caught → the rule), and the rule is added to its Rules section, which must stay a 30-second read.
- **Where deliverables live.** Anything the user will open again — a published page, a generated report, a diagram, a script, a data file — is written into this project as a committed file **first**, and published or sent from that path. The published/sent copy is a copy; the committed file is the source, and editing the source does not update the copy. Only genuinely throwaway scratch work (an intermediate extract, a one-off comparison) may live in the scratchpad — and if it's unclear whether something is throwaway, it is not. Full discipline: the **`durable-deliverables`** skill.
- **One source per skill.** The user's skills repository **`TK725/claude-skills`** is the single source of his own skills (its `SOURCES.json` says which skills live there; its `CLAUDE.md` says how to change one without overwriting changes made elsewhere). A session that needs to change a skill changes it there — never by copying it into this project. Attach that repo to sessions of this project; a session started without it can say "attach claude-skills".

## Hard rules
- **Strictly non-partisan, data-first.** The user explicitly wants to avoid any "them against us" / conspiratorial framing. Facts with sources; interpretation clearly separated and labeled.
- **Every number carries a source and a date.** No numbers from memory.
- **Nothing personal about the owner enters this repo.** This project was founded inside the owner's private career repo and was moved here on 2026-11-03 with fresh history precisely to keep personal data (salary, employer, career plans) out; keep it that way — no personal details in files, commits, or issue text.
- Messages from the user arrive via voice transcription and contain transcription errors — interpret generously, confirm before acting on anything ambiguous and consequential.
- Destructive remote git operations (deleting branches/refs) are refused by the session environment — archive first, then log a known issue for the owner; don't retry.
- Commit and push after every substantive change.
