# doc-yet

`doc-yet` e uma skill para documentar repositorios reais de forma consistente, usando `.agents` como camada canonica de documentacao interna e arquivos-ponte leves para `Codex`, `Claude`, `Cursor` e `Gemini`.

## O que a skill faz

- inspeciona a estrutura do repositorio antes de propor a documentacao
- detecta topologias como app unico, monorepo, multi-service ou frontend por features
- cria ou atualiza `.agents/project/*`
- melhora o `README.md` raiz sem transformar ele em uma wiki interna completa
- gera ou atualiza arquivos de bridge para ferramentas de IA
- registra suposicoes e lacunas de documentacao em vez de inventar arquitetura

## Estrutura

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

## Arquivos principais

- `SKILL.md`: instrucoes centrais da skill e fluxo principal
- `references/documentation-blueprints.md`: blueprints dos documentos em `.agents`
- `references/topology-playbook.md`: regras para decidir entre docs globais e locais
- `references/bridge-templates.md`: templates de `AGENTS.md`, `CLAUDE.md`, `GEMINI.md` e outros arquivos de bridge
- `evals/evals.json`: cenarios de avaliacao da skill
- `agents/openai.yaml`: metadata de interface da skill

## Instalacao

Localmente, a partir deste repositorio:

```bash
npx skills add . --skill doc-yet -a codex
```

Via GitHub, instalando a skill pelo nome dentro do repositorio:

```bash
npx skills add dirosaki/skills --skill doc-yet -a codex
```

## Uso

Exemplo de prompt:

```text
Use $doc-yet to document this repository into .agents and refresh bridge files.
```

## Validacao

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/doc-yet
```
