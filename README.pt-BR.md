# skills

Este repositorio publica skills de agentes em um formato compativel com `npx skills`.
Cada skill mantem seu proprio README dentro da pasta dela, com documentacao sobre a skill em si.

## Skills disponiveis

- `doc-yet`: documenta repositorios reais em `.agents` e mantem os arquivos de bridge alinhados entre ferramentas de IA

## Documentacao das skills

- `skills/doc-yet/README.md`
- `skills/doc-yet/README.pt-BR.md`

## Instalacao

```bash
npx skills add dirosaki/skills --skill doc-yet -a codex
```

Para inspecionar a skill antes de instalar:

```bash
npx skills add dirosaki/skills --list
```

## Estrutura do repositorio

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

## Como contribuir

As contribuicoes devem ser feitas por pull request neste repositorio.
O guia completo esta em [CONTRIBUTING.pt-BR.md](./CONTRIBUTING.pt-BR.md).

1. Faca um fork do repositorio e crie uma branch para a sua mudanca.
2. Adicione ou atualize uma skill em `skills/<nome-da-skill>/`.
3. Atualize o README da skill e os evals quando o comportamento mudar.
4. Valide localmente a skill alterada antes de abrir o PR:

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/<nome-da-skill>
```

5. Abra um pull request usando o template do repositorio e descreva o que mudou, qual skill foi afetada e como voce validou.

## Licenca

Este repositorio usa a licenca MIT. Veja [LICENSE](./LICENSE).

## Comunidade

- Guia de contribuicao: [CONTRIBUTING.pt-BR.md](./CONTRIBUTING.pt-BR.md)
- Codigo de conduta: [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)
