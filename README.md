# skills

This repository publishes agent skills in a layout compatible with `npx skills`.
Each skill keeps its own README inside its folder with documentation about the skill itself.

## Available skills

- `doc-yet`: document real repositories into `.agents` and keep bridge files aligned across AI tools

## Skill documentation

- `skills/doc-yet/README.md`
- `skills/doc-yet/README.pt-BR.md`

## Install

```bash
npx skills add dirosaki/skills --skill doc-yet -a codex
```

To inspect the skill before installing:

```bash
npx skills add dirosaki/skills --list
```

## Repository layout

```text
skills/
  doc-yet/
    SKILL.md
    README.md
    README.pt-BR.md
    agents/openai.yaml
    evals/evals.json
    references/
```

## Contributing

Contributions should be made through pull requests against this repository.
The full guide lives in [CONTRIBUTING.md](./CONTRIBUTING.md).

1. Fork the repository and create a branch for your change.
2. Add or update a skill under `skills/<skill-name>/`.
3. Update the skill README and evals when behavior changes.
4. Validate the changed skill locally before opening the PR:

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/<skill-name>
```

5. Open a pull request using the provided PR template and describe what changed, which skill was affected, and how you validated it.

## License

This repository is licensed under the MIT License. See [LICENSE](./LICENSE).

## Community

- Contribution guide: [CONTRIBUTING.md](./CONTRIBUTING.md)
- Code of conduct: [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)
