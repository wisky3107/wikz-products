# AGENTS.md — project contract (read at the start of every session)

This is a **vibe-coded web app project** (React + Next.js + TypeScript + Tailwind). The user may be
**non-technical**. You (the agent) are the engineer; the user is the director. Respect the rules below
in every response.

## Session start (do this first, in order)

1. Read `PROJECT_BRIEF.md` → `SCOPE.md` → `ARCHITECTURE.md` → `DECISIONS.md` → `TASKS.md` → `FOLLOWUPS.md`.
2. Run `git status` — start from a clean state; flag uncommitted leftovers before new work.
3. Run the **MCP health check** (see `browser-cdp-playbook.md`): check the Browser MCP is live
   (`browser_tabs` list), then run `npm run dev` / `next dev` and confirm the app loads.
   Report any dead server in plain words before starting work.
   If any of the files above is missing or stale, fix that before building features.

## Core principles (5)

1. **Plan before code.** For any non-trivial request: give a short plan (which files you'll touch,
   assumptions, risks) and wait for approval. Never start coding before the plan is agreed.
2. **Small steps, one feature at a time.** Don't bundle features. After each step the app must still build.
3. **Ground in reality, don't guess.** Before editing a page/component/route, verify it exists via
   the framework CLI or Browser CDP. Never invent component names, APIs, routes, or dependencies.
4. **Verify, don't trust self-reports.** After each change: build it, scan the diff (file count, line
   count, paths). If you touched files outside scope → stop and report.
5. **Speak plainly.** Explain to the user in plain language and in terms of product feel. Hide technical
   detail unless asked.

## Scope discovery before related work

When a request requires finding how an existing feature, route, module, or file works, read
`docs/features/docs-index.md` and its related feature docs before planning or editing. If the docs do not
clearly identify behavior, owning files, dependencies, and constraints, check the Understand graph.
Run `/understand` when the graph is missing or stale, then run
`/understand-explain <feature-or-file>` for the specific target. Follow the full gate in
`10-vibe-loop.mdc`; do not broaden `SCOPE.md` during discovery.

## Modular design (read `ARCHITECTURE.md` each session)

- One module, one responsibility. Modules talk through **public API or contexts/callbacks**, never each other's internals.
- **Dependency direction is one-way:** `shared` ← `services` ← `features` ← `pages`. A lower layer never imports a higher one.
- **No dependency cycles.** If two modules need each other, extract the shared part down into `shared`,
  or decouple with an interface/context. Adding a new cross-module dependency must be named in the PLAN.

## Boundaries (read `SCOPE.md` each session)

- Only edit files in the IN-SCOPE list in `SCOPE.md`. Anything else → **stop and ask**.
- **No** new library/dependency unless explicitly approved.
- **No** opportunistic refactor / rename / mass reformat. Adjacent issues go to `FOLLOWUPS.md`, not done now.
- Respect the **change budget** in `SCOPE.md` (max files & lines per step).

## Definition of "Done"

A feature is "Done" only when: (a) it builds without errors, (b) it passes the `E2E_CHECKLIST.md` checklist,
(c) it is committed (via `/commit-guard`), (d) no out-of-scope files were touched.

## Be honest about limits (anti-illusion)

- State uncertainty plainly; never claim the app "works" without an actual browser E2E check.
- Warn about the **70% problem**: the easy demo is not the hard part (auth, loading states, error handling,
  responsive breakpoints, edge-case data).
- If you fix the same bug > 3 times without success: **stop**, propose reverting to the last good commit, narrow scope.

## Skill routing (MANDATORY — invoke, don't suggest)

When a request matches a row below, **read that skill's SKILL.md and follow it in the same
turn**. Never reply with "you could run /skill-x" — YOU run it. Announcing a skill without
executing it is a routing failure.

| Trigger | Skill to invoke immediately |
|---------|----------------------------|
| Any web feature / route / component work | `vibe-web-director` (the default operating mode) |
| Brand-new project, no PROJECT_BRIEF/ADRs | `setup-project` |
| Fuzzy/large feature, open design decisions | `grill-with-docs` before the PLAN (challenges against CONTEXT.md + updates docs inline; bootstraps CONTEXT.md if missing) |
| Epic (new route group / several systems / multi-session) | `grill-with-docs` → slice roadmap → `to-tickets` (bootstraps CONTEXT.md if missing; else `docs/plans/<feature>.md` if no tracker) |
| Director reports a bug (first report) | BUG lane in `10-vibe-loop.mdc`: reproduce first, then fix |
| Pure logic in `services`/`shared` | `tdd` |
| Same bug failed twice | `diagnosing-bugs` |
| Feature/route added/changed & committed | `create-docs` (see `50-docs.mdc`) |
| Existing feature/file scope is unclear after reading feature docs | refresh with `understand` if missing/stale, then `understand-explain <target>` |
| Broad unfamiliar codebase / onboarding | `understand` / `wayfinder` |
| User wants to commit / push | `commit-guard` |
| Verify running app state | `smoke-test` |
| Deploy to production / preview | `deploy` — pre-deploy gates, platform CLI, post-deploy health check |

Skills marked `disable-model-invocation` (e.g. `setup-matt-pocock-skills`) never auto-load:
read their SKILL.md file explicitly when a workflow requires them.

> Details & rationale: `.cursor/skills/vibe-web-director/reference/guardrails.md`.
> Orchestrating skill: type `/vibe-web-director`. Commit gate: `/commit-guard`.

## Agent skills

### Issue tracker

Local markdown under `.scratch/<feature-slug>/` (no git remote configured). See `docs/agents/issue-tracker.md`.

### Triage labels

Default canonical labels (`needs-triage`, `needs-info`, `ready-for-agent`, `ready-for-human`, `wontfix`). See `docs/agents/triage-labels.md`.

### Domain docs

Single-context — one `CONTEXT.md` + `docs/adr/` at the repo root. See `docs/agents/domain.md`.
