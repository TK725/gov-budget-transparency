# Handoff for the next session

**Written 2026-11-03**, at the end of the founding-and-migration sessions (2026-08-13 and 2026-11-03). **Next:** Tracker #1 — get one full budget year at Titel level, starting with the session route in KI-01's `me` steps (standing go, see section 4). What happened is in `TRACKER.md`'s session log; the project's rules are in `CLAUDE.md`. This file's paths are checked by `python3 -I "$(ls -d /root/.claude/skills/synced/*/handoff | head -1)/scripts/check_handoff.py" --root .` (the skills sync under `/root/.claude/skills/synced/<id>/`, and the id changes — always glob, never hard-code).

**Fresh-agent test:** ran 2026-11-03 against this handoff; results and the standing prompt in `docs/handoff-test.md`. Nothing pending.

**Is it still current?** It describes the repository as of its own last commit, when nothing was running and nothing was uncommitted. Run `git fetch`, then:

```
git log --oneline "$(git log -1 --format=%H -- HANDOFF.md)..HEAD"
```

No output means nothing has changed. If commits are listed, a session stopped before rewriting this file: read them and the end of the session log first.

## 1. The first ten minutes

1. `CLAUDE.md` loads by itself; then read the Rules section of `LESSONS.md` (30 seconds), the `Next up` table of `TRACKER.md`, and this file. `DECISIONS.md` for anything that feels re-litigable — it probably isn't.
2. **Branch:** everything on `main`; no pull requests.
3. **Build and checks:** none — the project has no code yet, only records. The known-issues format check is `python3 -I "$(ls -d /root/.claude/skills/synced/*/known-issues | head -1)/scripts/known_issues.py" --file known_issues.json --out KNOWN_ISSUES.md --check`.
4. **The user's first message:** usually the saved prompt in `docs/first-prompt.md`, or a KI reply ("KI-01: …", a dropped data file) — see section 5. He speaks via voice transcription (expect transcription errors; `CLAUDE.md` has the rule).

## 2. Where things stand

- **Records:** complete and current — brief, tracker, decisions (D1–D8), research Phase 1 (all sourced), guardrails, lessons (2 rules), known issues (KI-01 open; KI-02/KI-03 done).
- **Research:** Phase 1 (feasibility) answered the founding questions: data public to Titel level, machine-readable, DL-DE BY 2.0 reusable; strongest existing player Dezernat Zukunft. Open `[verify]` markers in `RESEARCH.md` are covered by Tracker #8.
- **Data:** none in the repo yet — that is the next job. No `data/` directory exists until #1 lands it.
- **Code/website:** none yet by design; stack decision is Tracker #4, gated on #2.
- **Running or half done:** nothing. **Ended with this session:** nothing (no watches, no background jobs). **User input outside the repository:** none to check as of 2026-11-03 — no published pages exist, and this repo has no GitHub issues or pull requests. If that changes, the handoff of that session must name where to look.

## 3. Waiting on the user

| Item | What | Our recommendation |
|---|---|---|
| KI-01 | A budget CSV/XLSX downloaded in his browser (exact steps: Start here in `KNOWN_ISSUES.md`) | Only needed if the session route fails — try that first, don't nag |
| Brief cadence | `PROJECT_BRIEF.md` Timeline still has a `[placeholder]` for his working cadence | Ask once, low priority, bundled with other questions |

## 4. Next: Tracker #1 — one budget year at Titel level

**The user's go:** standing. #1 sits atop `Next up`; the founding instruction (2026-08-13, "collect data, categorize it, visualize it") covers data acquisition, and the owner has twice confirmed the plan since (setup upgrade and migration, both 2026-11-03). Start at once; the first-prompt's "no big jobs without a go" does not bite — this is the recorded next job. No budget caps set; stop and ask before anything that costs money.

1. **Try the session route** (~30 min): fetch the Dezernat Zukunft Haushaltstracker dataset (and failing that, GovData mirrors) — untried as of 2026-11-03; federal portals themselves bot-block automated clients (HTTP 503, see KI-01). First action: find the dataset download link via web search from `RESEARCH.md`'s Dezernat Zukunft sources.
2. **If a file lands** (either route): inspect structure (Einzelplan/Kapitel/Titel, Soll/Ist), reproduce the year's official headline total as sanity gate, commit under `data/`, write findings as Phase 2 in `RESEARCH.md`, close #1 and KI-01.
3. **If both routes fail:** update KI-01's detail with what was tried, lean on the owner's browser-download step, move to #8 (Sondervermögen deep-dive, pure web research) meanwhile.

**Already in hand:** all Phase 1 source links in `RESEARCH.md`; KI-01's `me` steps in `known_issues.json`.

## 5. Other arrivals

- **A data file dropped in chat:** run KI-01's `me` steps (inspect → sanity-check → `data/` → Phase 2 → close #1/KI-01).
- **"KI-01: formats are …":** record in KI-01, adapt the download advice, regenerate `KNOWN_ISSUES.md`.
- **"attach claude-skills":** the owner's skills repo — single source of his skills (`CLAUDE.md`, Operating conventions).
- **Anything interview-, CV- or career-related:** wrong project — that lives in his separate career repo, not here.

## 6. This session's warnings

- `RESEARCH.md` notes the bundesAPI OpenAPI spec lists years 2012–2021 — probably stale; verify live coverage before relying on it.
- The repo this project migrated FROM was renamed (`Claude-next-career-step` → `next-career-step`); the Provenance section in `PROJECT_BRIEF.md` is the only pointer back, and nothing here should need it.
- Git pushes through the proxy print scary-looking negotiation warnings ("expected 'acknowledgments', received 'packfile'") and still succeed — check the ref update line, not the warning.

## How things work (small-project map)

- **Data sources (all documented with links in `RESEARCH.md`):** bundeshaushalt.de (official portal + JSON API `internalapi/budgetData`), BMF Datenportal (CSV/XML), GovData, Dezernat Zukunft Haushaltstracker dataset. The two federal domains bot-block non-browser clients (KI-01).
- **Known issues:** edit `known_issues.json`, then regenerate the markdown with the `known-issues` skill's script (command in section 1.3 minus `--check`); never delete an issue, mark it `done YYYY-MM-DD: how`.
- **Conventions:** commit+push after every substantive change; session-log entry at session end; every number with source and date; non-partisan framing per `GUARDRAILS.md`.
