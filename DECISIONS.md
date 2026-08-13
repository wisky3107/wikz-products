# DECISIONS — locked choices (do not relitigate without an ADR)

> When a question is settled, write the answer here. The agent reads this at session start and respects
> it. This prevents the AI from re-opening settled debates or silently switching approaches.

| # | Date | Decision | Why | Scope |
|---|------|----------|-----|-------|
| 1 | 2026-08-13 | React + Next.js (App Router) | Most popular, best AI support, TypeScript-first | Framework |
| 2 | 2026-08-13 | TypeScript strict, no `any` | Required by `20-web.mdc` | Language |
| 3 | 2026-08-13 | Tailwind CSS | Dominant in vibe-coding, fast iteration, no CSS-file sprawl | Styling |
| 4 | 2026-08-13 | React Context + hooks | No extra library needed for most apps | State management |
| 5 | 2026-08-13 | Server components for initial data; SWR/TanStack Query if client-side fetching needed | Fits Next.js data model | Data fetching |
| 6 | 2026-08-13 | NextAuth.js | Batteries-included, handles OAuth/sessions/CSRF | Authentication |
| 7 | 2026-08-13 | Prisma + PostgreSQL | Type-safe ORM, migrations, best AI tooling support | Database |
| 8 | 2026-08-13 | Vercel | Zero-config Next.js deploy, preview branches, CDN | Deployment |
| 9 | 2026-08-13 | Vitest (unit) + Playwright (E2E) | Fastest in JS ecosystem, colocated `.spec.ts` files | Testing |
| 10 | 2026-08-13 | pnpm | Disk-efficient, strict, fast | Package manager |
| 11 | 2026-08-13 | ESLint + Prettier | Standard web tooling, wide AI model knowledge | Linting/formatting |
| 12 | 2026-08-13 | GitHub Actions | Free for public repos, deep Vercel/Playwright integration | CI/CD |
| 13 | 2026-08-13 | Vercel Analytics + Sentry | Frontend analytics + error monitoring | Monitoring |

## How to use
- **Write it when a decision is locked.** Grill sessions, `/setup-project`, and ADRs produce decisions — record the outcome here.
- **Agent rule:** before proposing an alternative approach, check DECISIONS.md. If the proposed change
  contradicts a locked decision, flag the conflict and ask whether to open an ADR to re-litigate.
- **ADR for contested changes:** if a locked decision needs revisiting, write a new ADR in `docs/adr/`
  documenting the tradeoff, then update this file.

## Rules for agents
- Locked decisions are NOT suggestions. They are the project's current constitution.
- If you find yourself about to propose Zustand when the decision says "Context + hooks", stop.
  Either follow the decision or ask if the user wants to open an ADR to change it.
- New decisions are added at the bottom. Old decisions are never deleted — they are struck through
  with `~~strikethrough~~` and a note pointing to the replacement decision.
