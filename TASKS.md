# TASKS — active work tracker (done / in-progress / next)

> Repo-persisted session memory. The agent reads this at session start and writes updates back at the end.
> This survives context resets, model swaps, and tool changes. Keep it current and short.

## In-Progress (one item only — finish before starting another)

| # | Task | Files | Success criterion | Status |
|---|------|-------|-------------------|--------|
| — | (none) | — | — | — |

## Next (priority order, grab the top one when In-Progress is empty)

| Priority | Task | Why next? | Depends on |
|----------|------|-----------|------------|
| 1 | Fill in `PROJECT_BRIEF.md` (what the app is, core flow, feel) | Blocks the first feature — nothing can be scoped without it | — |
| 2 | Scaffold the Next.js app (`create-next-app`, TypeScript + Tailwind) per `docs/adr/0001-tech-stack.md` | First code in the repo | PROJECT_BRIEF.md |

## Done (this session)

| # | Date | Task | Commit |
|---|------|------|--------|
| 1 | 2026-08-13 | Ran `/setup-project`: tech-stack decisions locked, ADR/CONTEXT/DECISIONS/TASKS scaffolded | (uncommitted) |

## How to use
- **One In-Progress at a time.** Finish, commit, move from In-Progress to Done, promote the top Next item.
- **Agent responsibility:** at session start, read TASKS.md and resume In-Progress or start Next.
  At session end, update statuses and commit.
- **Director responsibility:** reprioritize Next list; nothing starts without being on this list.
- **Never fold adjacent work into the current task** — park it as a new Next entry instead.
