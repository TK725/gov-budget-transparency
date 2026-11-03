# Testing the handoff on a fresh agent

After a large change to `HANDOFF.md`, test it on an agent that has not seen the session. The same questions every time, so results can be compared from session to session. The checker covers paths and counts; this test covers what a script cannot: whether a new session would act rightly.

## How to run it

Start one agent that has not seen this session (in Claude Code: the Agent tool, a general-purpose agent, in the foreground) with the prompt below. Fix every gap it finds in the file it concerns, or say why not; a gap that was only true while you were still working (uncommitted files) is not a gap. Add a row to the results.

## The prompt

```
You are testing a handoff document for a new working session, as if you were that new session.
Repository: /home/user/gov-budget-transparency. READ ONLY: do not edit, commit or run anything
that writes files; do not access the network.

Read, in this order and as a new session would: CLAUDE.md, HANDOFF.md, the Rules section of
LESSONS.md, and TRACKER.md's "Next up" table. Open other files only when the handoff points you
to them and you need them to answer.

Then answer, briefly and concretely (file paths, item IDs):
1. If the user's first message is the saved prompt in docs/first-prompt.md, what do you reply?
   If it is just "go", what exactly do you start, in what order, and what do you say first?
   What budget or stop rules apply?
2. The user drops a budget CSV file into the chat with no further words. What do you do, step
   by step, and where does each result go?
3. Which data sources are usable by an automated session right now and why — and which are not?
4. What waits on the user, and what would you recommend they do first?
5. Has the user left input anywhere outside the repository (picks, answers, comments)? How would
   you check, for every place that can hold it?
6. Gaps: anything in the handoff that is unclear, contradicts another file (check at least the
   tracker's rows for the next job, CLAUDE.md's status line, and the files the handoff names),
   points to a missing file, or that you had to guess. List each gap with the line it concerns.
   Be strict: a gap is anything that would make a new session act wrongly or ask a needless
   question.

Reply in under 500 words.
```

## Results

| Date | Handoff of | Answers right | Gaps found | Fixed |
|---|---|---|---|---|
| 2026-11-03 | 2026-11-03 (first handoff) | 1–5 all right | 5 (4 real: placeholder skill paths, test status unstated, tracker #1 status contradicted handoff, outside-input places incomplete; 1 minor: first-prompt/handoff read-order inconsistency) | 5 of 5 |
