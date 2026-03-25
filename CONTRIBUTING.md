# Contributing

Thanks for contributing to this repository.

## Repository model

- Skills live under `skills/<skill-name>/`.
- Each skill must contain `SKILL.md`.
- Each skill should keep its own `README.md` with skill-specific documentation.
- Longer reusable guidance should live in `references/`.
- UI metadata should live in `agents/openai.yaml` when needed.
- Evaluation scenarios should live in `evals/evals.json`.

## How to contribute

1. Fork the repository.
2. Create a branch for your change.
3. Add a new skill or update an existing one under `skills/<skill-name>/`.
4. Keep `SKILL.md` concise and focused on when the skill should be used and how it should operate.
5. Add or update the skill README.
6. Add or update `agents/openai.yaml` if the skill should expose UI metadata.
7. Add or expand `evals/evals.json` with realistic prompts and expected outputs.
8. Validate the changed skill locally:

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/<skill-name>
```

9. Open a pull request with:
   - a short summary of the change
   - the skill name
   - validation steps you ran
   - screenshots or examples if the change affects docs or UX materially

## What makes a good contribution

- stronger eval coverage
- more precise triggering descriptions in `SKILL.md`
- cleaner reference material with less duplication
- clearer bridge templates
- better examples for real repository topologies

## Pull request checklist

- The skill remains valid.
- The README matches the current skill behavior.
- New guidance is fact-based and avoids generic filler.
- Added files are necessary and support the skill directly.
- Evals were updated when behavior changed.
