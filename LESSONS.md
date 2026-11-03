# LESSONS — Budget Transparency

## Rules
<!-- The 30-second read before writing anything. One line per rule; when rules overlap, merge or generalize rather than letting the list grow. Full stories live in Entries below. -->

1. A new project starts in its own repo — ask the owner where it should live on day one; never incubate it inside an unrelated repo. (L1)
2. Destructive remote git operations (deleting branches/refs) are the owner's: preserve history on an archive ref first, then open a known issue with the owner's one-click step — don't retry the blocked call. (L2)

## Entries
<!-- Every mistake becomes an entry, every entry ends in a rule that is also added to Rules above. Format: **What happened → Why it happened → How it was caught → The rule.** Mistakes only — choices and their rationale belong in DECISIONS.md. -->

### L1 — 2026-11-03 — Project founded inside an unrelated private repo
**What happened:** At founding (2026-08-13) the project was created as a `budget-transparency/` subfolder on a branch of the owner's private career repo. **Why:** the founding session defaulted to the repo at hand instead of asking where a brand-new project should live. **How it was caught:** the owner, three months later ("oh no, that's the wrong repo") — costing a migration session, a provenance write-up, and an archive-branch rescue of commit history. **The rule:** a new project starts in its own repo; ask the owner where it should live on day one.

### L2 — 2026-11-03 — Remote branch deletion is refused by the session environment
**What happened:** Deleting the old incubation branch failed twice — `git push --delete` (HTTP 403 at the proxy) and the GitHub API via `gh` ("Write access to this GitHub API path is not permitted through this proxy"). **Why:** the cloud session's proxy forbids destructive ref operations by design. **How it was caught:** immediately, by the 403s; resolved by first pushing an archive branch to preserve the history the branch alone held, then handing the one-click deletion to the owner as KI-03. **The rule:** destructive remote git operations are the owner's — archive first, then log a known issue; don't retry.
