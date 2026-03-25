# Topology Playbook

Decide documentation placement based on architecture, not aesthetics.

## Rule of thumb

Create the smallest documentation surface that still makes future work easier.

- Start with global docs in `.agents/project/`.
- Add local `.agents/` only for high-value boundaries.
- Link global and local indexes both ways.

## Scenario: single repo, one main app or service

Default:

- `.agents/project/` for nearly everything

Add local `.agents/` only when there is a subsystem with heavy internal logic, such as:

- `src/domains/billing/.agents/`
- `src/features/analytics/.agents/`
- `services/worker/.agents/`

## Scenario: monorepo

Always create:

- `.agents/project/`

Usually add local `.agents/` for:

- Each deployable app in `apps/*`
- Each important backend service in `services/*`
- Each shared UI or domain package in `packages/*` or `libs/*`

Examples:

- `apps/web/.agents/`
- `apps/api/.agents/`
- `packages/ui/.agents/`
- `packages/domain-orders/.agents/`

Do not add local `.agents/` to tiny config-only packages unless they genuinely need local context.

## Scenario: feature-based frontend

Always create:

- `.agents/project/`

Consider local `.agents/` for major feature folders when they have:

- Dedicated routes
- State, API, and UI boundaries
- Distinct business rules
- Enough complexity to deserve local onboarding

Examples:

- `src/features/billing/.agents/`
- `src/features/customers/.agents/`
- `src/features/reporting/.agents/`

If there is a shared design system or UI package, document it separately:

- `src/components/.agents/` when the shared UI lives there
- `packages/ui/.agents/` when it is a package

## Scenario: multi-service backend

Always create:

- `.agents/project/`

Usually add local `.agents/` for:

- API service
- Worker service
- Admin or internal tooling service
- Data pipeline or ETL service

Examples:

- `services/api/.agents/`
- `services/worker/.agents/`
- `services/etl/.agents/`

## Scenario: libraries or SDK repos

Keep global docs in `.agents/project/`, then add local `.agents/` only where the public API or internal architecture is large enough to justify it.

Common examples:

- `packages/react/.agents/`
- `packages/core/.agents/`
- `packages/cli/.agents/`

## When to add a local `.agents/`

Add one when the subtree has clear local questions such as:

- How does this app boot?
- What are the internal module boundaries?
- Which commands or env vars matter only here?
- Which business rules or design rules apply only here?

If those questions would clutter the global docs, create a local `.agents/`.

## When not to add a local `.agents/`

Avoid local `.agents/` for:

- Tiny helper folders
- Pure asset folders
- Generated output
- Thin config wrappers
- Subtrees with no meaningful local behavior

## Linking rules

When local `.agents/` exist:

- The global `.agents/project/documentation-index.md` should link to them.
- Each local `.agents/documentation-index.md` should link back to `.agents/project/documentation-index.md` at the repo root.
- Bridge files should instruct tools to read both the global docs and the nearest local `.agents/` when working in that subtree.

## Frontend-specific placement rules

Document frontend design systems and tokens near their real source of truth:

- Shared UI package: `packages/ui/.agents/`
- App-local design system: `apps/web/.agents/` or `src/components/.agents/`
- Feature-specific UI patterns: `src/features/<feature>/.agents/`

Do not split design guidance across unrelated folders unless the architecture itself is split.

## Naming guidance for local docs

Inside a local `.agents/`, prefer:

- `documentation-index.md`
- `feature-overview.md` for feature folders
- `service-overview.md` for services
- `package-overview.md` for packages
- `architecture.md`
- Additional targeted docs only when needed
