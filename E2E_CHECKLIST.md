# E2E CHECKLIST — Product gallery

- [x] `/` loads without browser load or console errors.
- [x] The hero clearly introduces the collection.
- [x] Exactly two cards render in the approved order.
- [x] Both cards show verified status, description, and feature tags.
- [x] Both launch states say `Coming soon` and are not links.
- [x] Keyboard links have visible focus styling.
- [x] The layout has desktop and mobile responsive rules.
- [x] Reduced-motion preference removes smooth scrolling.
- [x] `npm run build` passes.
- [x] `npm run typecheck` passes.

## Evidence

- `npm run build` — exit 0; Next.js compiled and prerendered `/`.
- `npm run typecheck` — exit 0.
- Browser smoke check at `http://localhost:3000/` — title `Wikz — Product Gallery`, no load error, expected headings and lists, exactly two `<article>` cards, two non-link `Coming soon` states, three anchor focusables, and no horizontal overflow at a 1034px viewport.
