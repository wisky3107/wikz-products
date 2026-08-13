# E2E CHECKLIST — Product gallery

- [x] `/` loads without browser load or console errors.
- [x] The hero clearly introduces the collection.
- [x] Exactly two cards render in the approved order.
- [x] Both cards show verified status, description, and feature tags.
- [x] Both cards have an `Open App` link to the verified product URL.
- [x] Both product links open successfully in a new tab.
- [x] Keyboard links have visible focus styling.
- [x] The layout has desktop and mobile responsive rules.
- [x] Reduced-motion preference removes smooth scrolling.
- [x] `npm run build` passes.
- [x] `npm run typecheck` passes.

## Evidence

- `npm run build` — exit 0; Next.js compiled and prerendered `/`.
- `npm run typecheck` — exit 0.
- Browser smoke check at `http://localhost:3001/` — title `Wikz — Product Gallery`, no load error, exactly two `<article>` cards, exactly two accessible `Open App` links with `target="_blank"` and `rel="noreferrer"`, and no horizontal overflow at a 1034px viewport.
- Public product checks — `https://orca-hermes-guide.vercel.app/` returned HTTP 200 with title `Học cùng AI`; `https://typing-trainer.vercel.app/` returned HTTP 200 with title `Typing Practice`.
- Production smoke check at `https://wikz-products.vercel.app/` — title `Wikz — Product Gallery`, exactly two cards, exactly two verified `Open App` links, no `Coming soon` states, and no horizontal overflow at a 1034px viewport; both linked products loaded completely with their expected titles.
