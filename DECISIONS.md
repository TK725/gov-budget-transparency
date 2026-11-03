# DECISIONS — Budget Transparency

Standing decisions. Never re-litigated without genuinely new information from the user — and a change is logged as a **new row that supersedes the old one**, never by editing the old row.

| ID | Date | Decision | Rationale |
|----|------|----------|-----------|
| D1 | 2026-08-13 | **Strictly non-partisan, data-first, constructive framing.** No "them against us" narrative, ever. | User's explicit founding constraint; also the project's credibility depends on it. |
| D2 | 2026-08-13 | **Free public service; no monetization.** Small out-of-pocket costs (domain/hosting) acceptable. | User's stated intent. |
| D3 | 2026-08-13 | **Start with the federal budget only** (not Länder, not municipalities, not general legislation tracking). | Specific, bounded, best data availability; user chose it as the starting point. |
| D4 | 2026-08-13 | **Before anything goes public, the project moves to its own dedicated repo.** This career repo stays private and is never the publishing vehicle. | Repo root contains sensitive personal data (salary, employer, career plans); a public website repo must have zero shared history with it. |
| D5 | 2026-08-13 | **German-language first** audience (citizens + journalists in Germany). | Subject matter and audience are German; English can follow later. |
| D6 | 2026-08-13 | **Positioning: the problem is digestibility, not secrecy.** The data is public; the project makes it understandable and checkable. | Research finding (RESEARCH.md Phase 1 calibration); factually accurate and keeps the project out of conspiracy-adjacent territory. |
| D7 | 2026-11-03 | **The user's skills repository (`TK725/claude-skills`) is the single source of his own skills.** A skill is changed there, never by copying it into this project; a project-local skill exists only if that repo's `SOURCES.json` says so. | One source per skill prevents divergent copies; user confirmed 2026-11-03. |
| D8 | 2026-11-03 | **The project's home is `TK725/gov-budget-transparency`** (this repo), moved here with fresh history — zero commits shared with the career repo. Fulfils D4 ahead of schedule; going public remains a separate, later step gated by GUARDRAILS.md and Tracker #7a. | User decided the career repo was the wrong home and moved the project immediately rather than waiting for launch (KI-02). |
