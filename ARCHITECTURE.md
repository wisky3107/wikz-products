# ARCHITECTURE — Product gallery

## Modules
| Module | Responsibility |
|---|---|
| `app/layout.tsx` | Root document metadata and global styles |
| `app/page.tsx` | Semantic, server-rendered gallery presentation |
| `data/products.ts` | Typed, verified product facts and display order |
| `app/globals.css` | Design tokens, responsive layout, focus and reduced-motion styling |

## Route registry
| Route | Component | Authentication |
|---|---|---|
| `/` | `Home` | None |

Data flows one way from the local product module into the page. There is no runtime state, remote fetch, or client-side data requirement.
