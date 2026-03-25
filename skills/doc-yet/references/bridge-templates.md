# Bridge Templates

Bridge files exist so different AI tools can discover the same canonical docs without duplicating them.

## Shared rules

Every bridge file should:

- Point to `.agents/project/documentation-index.md`
- Tell the tool to also read the nearest local `.agents/` when working inside a subtree that has one
- Remind the tool to update `.agents` docs and the root `README.md` after meaningful architecture or workflow changes
- Stay short and operational

Do not paste the full documentation into bridge files.

## `AGENTS.md` template for Codex

```md
# Project Instructions

- Canonical project documentation lives in `.agents/project/`.
- Start with `.agents/project/documentation-index.md`.
- When working inside a subtree that contains its own `.agents/`, read that local `documentation-index.md` too.
- Treat `.agents` docs as the internal source of truth and `README.md` as the public entrypoint.
- After meaningful architecture, workflow, or setup changes, update the affected `.agents` docs and the root `README.md`.
```

## `CLAUDE.md` template

```md
# Project Memory

- Canonical project documentation lives in `.agents/project/`.
- Read `.agents/project/documentation-index.md` before making large structural changes.
- If the current subtree has its own `.agents/`, consult the nearest local `documentation-index.md` too.
- Keep `.agents` docs and the root `README.md` aligned with real code changes.
```

## `.claude/commands/doc-yet.md` template

Use a slash command as a thin shortcut to the documentation workflow.

```md
Review the repository and refresh project documentation using the canonical docs in `.agents`.

Requirements:
- Start with `.agents/project/documentation-index.md`.
- Inspect the current repository structure before editing docs.
- Update the relevant global docs in `.agents/project/`.
- If the affected app, package, service, or feature has a local `.agents/`, update it too.
- Improve the root `README.md` when the change affects onboarding or project understanding.
- Keep assumptions clearly labeled.
```

## `GEMINI.md` template

```md
# Project Context

- Canonical documentation lives in `.agents/project/`.
- Start with `.agents/project/documentation-index.md`.
- When editing code in a subtree that has its own `.agents/`, read the nearest local `documentation-index.md` too.
- Keep `.agents` docs and the root `README.md` synchronized with repository changes.
```

## `.cursor/rules/doc-yet-project-docs.mdc` template

```md
---
description: Use `.agents` documentation as the source of truth for architecture, onboarding, and scoped project context. Apply when planning, implementing, refactoring, or updating docs in this repository.
alwaysApply: true
---

# Project Documentation

- Canonical internal documentation lives in `.agents/project/`.
- Start with `.agents/project/documentation-index.md`.
- When working inside a subtree that has its own `.agents/`, consult the nearest local `documentation-index.md` too.
- Keep `.agents` docs and the root `README.md` aligned with significant code or workflow changes.
```

## Merge strategy

If any of these files already exist:

- Preserve strong project-specific instructions already present.
- Add `.agents` discovery guidance without deleting unrelated policies.
- Prefer a short merge over a full rewrite.
