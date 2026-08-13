# Tech stack: Next.js + TypeScript + Tailwind + Prisma/Postgres

Locked during project setup (`/setup-project`) using the vibe-coding skill's recommended defaults
across the board, since this is a brand-new repo with no prior stack decisions to react to.

- **Framework**: React + Next.js (App Router) — most popular, best AI support, TypeScript-first
- **Language**: TypeScript strict, no `any`
- **Styling**: Tailwind CSS — dominant in vibe-coding, fast iteration, no CSS-file sprawl
- **State management**: React Context + hooks — no extra library needed for most apps
- **Data fetching**: Server components (Next.js) for initial data; SWR or TanStack Query if client-side fetching is needed
- **Authentication**: NextAuth.js — handles OAuth, sessions, CSRF; batteries-included
- **Database**: Prisma + PostgreSQL — type-safe ORM, migrations, best AI tooling support
- **Deployment**: Vercel — zero-config Next.js deploy, preview branches, CDN
- **Testing**: Vitest (unit) + Playwright (E2E) — fastest in the JS ecosystem, colocated `.spec.ts` files
- **Package manager**: pnpm — disk-efficient, strict, fast
- **Linting/formatting**: ESLint + Prettier — standard web tooling, wide AI model knowledge
- **CI/CD**: GitHub Actions — free for public repos, deep Vercel/Playwright integration
- **Monitoring**: Vercel Analytics (frontend) + Sentry (errors)
