# SCOPE — Product gallery

## Goal
Ship a minimal public gallery for the two verified products.

## In scope
- `app/` presentation and metadata
- `data/products.ts` typed local product facts
- Package and TypeScript configuration
- Required project and verification documentation
- Responsive, semantic presentation with visible keyboard focus
- Non-interactive Coming soon states while URLs remain unverified

## Out of scope
Source-product edits, deploys, authentication, databases, search, filters, comments, ratings, analytics, external assets, and additional products.

## Invariants
Exactly two products appear in the approved order. Product facts remain local and typed. No launch URL or screenshot is invented.
