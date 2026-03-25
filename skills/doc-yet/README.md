# doc-yet

`doc-yet` is a skill for documenting real repositories consistently, using `.agents` as the canonical internal documentation layer and lightweight bridge files for `Codex`, `Claude`, `Cursor`, and `Gemini`.

## What the skill does

- inspects the repository structure before proposing documentation
- detects topology such as single app, monorepo, multi-service, or feature-based frontend
- creates or updates `.agents/project/*`
- improves the root `README.md` without turning it into a full internal wiki
- generates or updates bridge files for AI tools
- records assumptions and documentation gaps instead of inventing architecture

## Structure

```text
skills/doc-yet/
  SKILL.md
  README.md
  README.pt-BR.md
  agents/openai.yaml
  evals/evals.json
  references/
    bridge-templates.md
    documentation-blueprints.md
    topology-playbook.md
```

## Main files

- `SKILL.md`: core skill instructions and workflow
- `references/documentation-blueprints.md`: blueprints for `.agents` documents
- `references/topology-playbook.md`: rules for deciding between global and local docs
- `references/bridge-templates.md`: templates for `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, and related bridge files
- `evals/evals.json`: evaluation scenarios for the skill
- `agents/openai.yaml`: UI-facing skill metadata

## Installation

Locally, from this repository:

```bash
npx skills add . --skill doc-yet -a codex
```

From GitHub, installing the skill by name from the repository:

```bash
npx skills add dirosaki/skills --skill doc-yet -a codex
```

## Usage

Example prompt:

```text
Use $doc-yet to document this repository into .agents and refresh bridge files.
```

## Validation

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/doc-yet
```
