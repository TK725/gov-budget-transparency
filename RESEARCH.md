# RESEARCH — German Budget Transparency

Append-only research record. Every claim carries a source link. Research date noted per phase.

---

## Phase 1 — Feasibility: Is the federal budget public, detailed, and legally reusable? (2026-08-13)

### Q1: Is the budget public? — YES, by constitutional design.

- The Grundgesetz (Art. 110 GG) requires that **all** federal revenues and expenditures be set out in the budget plan, which is enacted **as a law** (Haushaltsgesetz + Bundeshaushaltsplan). As a law it is by definition published — in the Bundesgesetzblatt and on the official portal bundeshaushalt.de. There is no "secret master budget"; secrecy is the narrow exception, not the rule (see caveats below).
- The budget is debated publicly in the Bundestag across multiple readings (the televised "Haushaltswoche", the Haushaltsausschuss committee work, the final "Bereinigungssitzung"). Process explainer: [bpb — Wie der Haushalt Gesetz wird](https://www.bpb.de/kurz-knapp/hintergrund-aktuell/573114/bundeshaushalt-2026-wie-der-haushalt-gesetz-wird/).
- **Current status:** the 2026 federal budget was passed by the Bundestag on 28 Nov 2025: total expenditures **€524.54bn**, net new borrowing €97.96bn, investments €58.35bn. Largest single plan: Labor & Social Affairs at €197.34bn (over a third of the whole budget). Sources: [Bundestag — 3rd reading](https://www.bundestag.de/dokumente/textarchiv/2025/kw48-de-haushaltsgesetz-2026-dritte-lesung-1126152), [Bundestag — Haushaltsgesetz 2026](https://www.bundestag.de/dokumente/textarchiv/2025/kw48-de-haushaltsgesetz-2026-zweite-lesung-1126156), [BMF — Bundeshaushalt 2026](https://www.bundesfinanzministerium.de/Web/DE/Themen/Oeffentliche_Finanzen/Bundeshaushalt/Bundeshaushalt-2026/bundeshaushalt-2026.html).

### Q2: Is the FULL detail available (not just headline numbers)? — YES, down to individual line items.

**Structure** (the budget's "chart of accounts"):
- **Gesamtplan** (overview) → ~25 **Einzelpläne** (one per ministry plus constitutional bodies plus Epl 60 "Allgemeine Finanzverwaltung") → **Kapitel** (chapters, per agency/area) → **Titel** (individual line items).
- Every line item has a 10-digit **Haushaltsstelle** (2 digits Einzelplan + 2 digits Kapitel + 5 digits Titel + check digit); the Titel encodes the type of revenue/expense. There are thousands of Titel, each with amount, legal basis, and explanatory notes (Erläuterungen). Sources: [Wikipedia — Bundeshaushaltsplan](https://de.wikipedia.org/wiki/Bundeshaushaltsplan_(Deutschland)), [BMF Glossar — Haushaltsplan](https://www.bundesfinanzministerium.de/Content/DE/Glossareintraege/H/haushaltsplan.html?view=renderHelp).
- Both **Soll** (planned/appropriated) and **Ist** (actually spent/received) values exist — the raw material for "did they do what they said" checks. The Haushaltsrechnung (final accounts) and the Bundesrechnungshof's audit remarks (Bemerkungen) cover the accountability back-end.

**Access channels:**
1. **bundeshaushalt.de ("Bundeshaushalt digital")** — official BMF portal: interactive visualization of the full budget, revenues and expenses, Soll and Ist, multiple years; per-Einzelplan PDFs at predictable URLs (e.g. [Epl 16, 2024](https://www.bundeshaushalt.de/static/daten/2024/soll/epl16.pdf); 2026 draft PDFs exist under `/static/daten/2026/soll/draft/`). Machine-readable data is offered as open data. Source: [bundeshaushalt.de — Bundeshaushalt digital](https://www.bundeshaushalt.de/DE/Bundeshaushalt-digital/bundeshaushalt-digital.html). *(Note: this domain was blocked by the research environment's egress proxy on 2026-08-13 — verify hands-on from the user's own machine; Tracker #1.)*
2. **JSON API** — bundeshaushalt.de exposes `GET https://bundeshaushalt.de/internalapi/budgetData` with params `year`, `account` (income/expenses), `quota` (target/actual), `unit` (single/function/group), `id` (budget-number drill-down); returns JSON with the item, its children, parents, and related classifications. Community OpenAPI documentation: [github.com/bundesAPI/bundeshaushalt-api](https://github.com/bundesAPI/bundeshaushalt-api) (spec there lists 2012–2021; likely stale — verify live coverage hands-on).
3. **BMF Datenportal** — official open-data portal of the finance ministry with budget datasets in CSV/XML, updated annually, series back to 2014 (some series much further; the historical Finanzberichte go back decades): [Datenportal des BMF](https://www.bundesfinanzministerium.de/Datenportal/start.html), [Bundeshaushalt Gesamtübersicht dataset](https://www.bundesfinanzministerium.de/Datenportal/Daten/offene-daten/haushalt-oeffentliche-finanzen/s05-bundeshaushalt-Gesamtuebersicht/s05-bundeshaushalt-Gesamtuebersicht.html).
4. **GovData** — the national open-data portal aggregates these datasets: [govdata.de](https://www.govdata.de/informationen/lizenzen).

**Honest caveats — where transparency genuinely ends:**
- **Intelligence services** (BND, BfV, MAD): only lump sums are public; detailed Wirtschaftspläne are approved by a confidential parliamentary panel (Vertrauensgremium). This is a deliberate, legally defined exception. `[verify: exact current mechanism before publishing]`
- **Sondervermögen (special funds)** — e.g. the €100bn Bundeswehr fund, the Klima- und Transformationsfonds, the 2025 infrastructure fund — sit **outside** the core budget with their own Wirtschaftspläne. They are published, but their separation is itself a major transparency topic and a promising angle for this project. `[verify: current list of active Sondervermögen and where each Wirtschaftsplan is published]`
- **Social insurance** (pension, health, unemployment funds) have separate budgets not inside the Bundeshaushalt, though large federal subsidies to them appear as Titel.

### Q3: Can we legally reuse it on a public website? — YES, including commercially; attribution required.

- All open data on the BMF Datenportal is licensed under **Datenlizenz Deutschland – Namensnennung – 2.0 (DL-DE BY 2.0)**: free reuse for commercial and non-commercial purposes, including modification, combination with other data, and integration into products — with attribution ("Bundesministerium der Finanzen" + license name + link). Sources: [BMF Nutzungshinweise](https://www.bundesfinanzministerium.de/Datenportal/Nutzungshinweise/Nutzungshinweise_text.html), [DL-DE BY 2.0 license text](https://www.govdata.de/dl-de/by-2-0).
- The Haushaltsgesetz and budget plan are **amtliche Werke** under **§ 5 UrhG** — official works exempt from copyright; anyone may reproduce them (no-alteration and source-citation duties apply for § 5 Abs. 2 works). Sources: [§ 5 UrhG — dejure.org](https://dejure.org/gesetze/UrhG/5.html), [Wikipedia — Amtliches Werk](https://de.wikipedia.org/wiki/Amtliches_Werk).
- A free, non-commercial citizen website is squarely within what these licenses were created for. Remaining legal to-dos are about **running a German website**, not the data: Impressumspflicht, privacy/DSGVO if any analytics, correct attribution on every page (Tracker #5).

### Q4 (unasked but important): Who is already doing this?

- **[Dezernat Zukunft — Haushaltstracker](https://www.dezernatzukunft.org/publikationen/der-neue-haushaltstracker-eine-anleitung)** — the strongest active player: interactive dashboard + search + downloadable scientific dataset, every federal revenue/expense line item, ~10 years of history, built from automated collection of budget plans and Sondervermögen Wirtschaftspläne since 2016, plus BMF Finanzberichte back to 1952. Also publishes a [Bundeshaushaltsmonitor](https://dezernatzukunft.org/en/bundeshaushaltsmonitor-2026/). Non-partisan think tank.
- **[offenerhaushalt.de](https://offenerhaushalt.de/)** (Open Knowledge Foundation Deutschland) — the pioneering volunteer project (mainly municipal budgets) — **discontinued / no longer updated**. Confirms both that the niche has real demand and that volunteer projects die without a sustainability plan.
- The official **bundeshaushalt.de** itself already visualizes the budget interactively — decent for browsing, weak on interpretation, comparisons, and accountability.
- Media do one-off visualizations at budget season; bpb does civic-education explainers.

**Implication:** "visualize the budget" alone is a solved problem. The open space is the **accountability layer** the user described: plan-vs-actual deviation tracking, what changed quietly year-over-year, Sondervermögen consolidation ("the real total budget"), plain-language per-Titel explanations, promise-vs-budget checks. That's Phase CONCEPT work (Tracker #2).

### Calibration of the initial hypotheses (honest read)

- "Maybe the budget is hidden/secret" → **No.** It is among the most publicly documented artifacts of German politics; publication is constitutionally mandated and the data is machine-readable and openly licensed.
- "Media covers ~5% of what's in there" → **Directionally fair.** Coverage concentrates on the total, the borrowing figure, and 2–3 contested items; thousands of Titel go undiscussed. That gap is exactly this project's opportunity.
- "Laws pass without being talked about" → **Overstated for the budget specifically** (it gets a full televised parliament week and months of committee work), but *effective* public understanding is thin — which supports the project's premise from a more defensible angle: the problem is digestibility, not secrecy. This framing is also safer territory (see GUARDRAILS.md).
