# PROJECT_BRIEF — German Budget Transparency

**Phase: RESEARCH done → HANDS-ON DATA next** *(keep in sync with the status line in CLAUDE.md — update both when it changes)*

## Goal
Make the German federal budget (Bundeshaushalt) genuinely understandable to ordinary citizens and journalists: collect openly available official data, categorize it, visualize it, and run logic checks against it — so that policies and spending become easier to follow and accountability improves. Free public service; no monetization planned; the user is willing to cover small running costs (domain, hosting).

## Why it matters (user's motivation)
- Perception that government works inefficiently, that large legislative packages (1,000+ pages) get reduced to two headline issues in media coverage, and that follow-through on political promises is hard to track.
- Explicitly optimistic, constructive framing: society improves over time; better transparency → better accountability → better politics. **Not** an anti-state project.

## Scope
- **In scope (start):** the federal budget (Bundeshaushalt) — plan (Soll) and actual (Ist) figures, structure, year-over-year changes, plain-language explanation.
- **Later candidates:** Sondervermögen (special funds), subsidy reports, plan-vs-actual deviation tracking, possibly Länder budgets.
- **Out of scope:** anything partisan, claims about individual politicians without primary sources, paid products.

## Phases
1. **RESEARCH (current)** — verify data availability, legal reusability, existing landscape. Largely done, see `RESEARCH.md` Phase 1.
2. **HANDS-ON DATA** — actually download the data, inspect structure and quality, build first local analyses.
3. **CONCEPT** — define the differentiator vs. existing tools (esp. Dezernat Zukunft's Haushaltstracker) and the MVP.
4. **PROTOTYPE** — first visualizations, static site.
5. **PUBLISH** — domain, Impressum/legal checklist, launch (the "own repo" part happened early, on 2026-11-03 — see Provenance).

## Stakeholders / audience
Everyday citizens, journalists, and the interested public in Germany. German-language first.

## Timeline
Side project, no deadline pressure. [placeholder: user to confirm rough cadence, e.g. one session per week]

## Budget
Small out-of-pocket costs OK (domain, static hosting — realistically €10–50/year). No large spend.

## Provenance
Founded 2026-08-13 inside a private repo of the owner's, on branch `claude/german-budget-transparency-jr0s9o`, as a `budget-transparency/` subfolder (incubation commits there: `913cfb3` founding + Phase 1 research, `8c6e0cb` setup upgrade to the project-setup standard, `f28eace` KI-02 opened, `87cb30f` folder removed after migration). Moved to this dedicated repo on 2026-11-03 as a fresh root commit — deliberately **without** carrying git history, so this repo shares no commits with its private origin (DECISIONS.md D4/D8). The incubation branch was deleted after the move; this section is its record.
