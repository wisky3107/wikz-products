# ARCHITECTURE — project module map

> Keep this short and current. The agent reads it to respect module boundaries and dependency direction.
> Update it whenever a module or a cross-module dependency is added.

## Layers (dependencies point downward only)

```
pages        → features, services, shared
features     → services, shared
services     → shared
shared       → (nothing)
```

## Modules

| Module | Layer | Responsibility | Public API (methods/exports) | May depend on |
|--------|-------|----------------|------------------------------|---------------|
| _(none yet — no code scaffolded)_ | | | | |

## Cross-module communication
- Context providers: `src/providers/` for app-wide state (auth, theme).
- Feature hooks for feature-specific state.
- Props for parent→child data flow; callbacks for child→parent events.

## Route registry

| Route | Page component | Auth required? | Layout group |
|-------|---------------|----------------|--------------|
| _(none yet)_ | | | |

## State ownership (single source of truth)

| State | Owned by | Others access via |
|-------|----------|-------------------|
| _(none yet)_ | | |

## Rules of this project
- No upward dependencies (lower layer never imports a higher one).
- No dependency cycles. If two modules need each other, extract shared logic to `shared`.
- Cross-module calls use public API or context/callbacks only — never another module's internals.
