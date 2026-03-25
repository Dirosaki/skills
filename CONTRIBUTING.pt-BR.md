# Contribuindo

Obrigado por contribuir com este repositorio.

## Modelo do repositorio

- As skills ficam em `skills/<nome-da-skill>/`.
- Cada skill deve conter `SKILL.md`.
- Cada skill deve manter seu proprio `README.md` com documentacao especifica da skill.
- Guias reutilizaveis e mais longos devem ficar em `references/`.
- Metadata de interface deve ficar em `agents/openai.yaml` quando necessario.
- Cenarios de avaliacao devem ficar em `evals/evals.json`.

## Como contribuir

1. Faca um fork do repositorio.
2. Crie uma branch para a sua mudanca.
3. Adicione uma nova skill ou atualize uma skill existente em `skills/<nome-da-skill>/`.
4. Mantenha o `SKILL.md` conciso e focado em quando a skill deve ser usada e como ela deve operar.
5. Adicione ou atualize o README da skill.
6. Adicione ou atualize `agents/openai.yaml` se a skill precisar expor metadata de interface.
7. Adicione ou expanda `evals/evals.json` com prompts realistas e saidas esperadas.
8. Valide localmente a skill alterada:

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/<nome-da-skill>
```

9. Abra um pull request com:
   - um resumo curto da mudanca
   - o nome da skill
   - os passos de validacao executados
   - screenshots ou exemplos se a mudanca afetar bastante a documentacao ou a UX

## O que faz uma contribuicao boa

- melhor cobertura de evals
- descricoes de trigger mais precisas no `SKILL.md`
- material de referencia mais limpo e com menos duplicacao
- templates de bridge mais claros
- exemplos melhores para topologias reais de repositorio

## Checklist do pull request

- A skill continua valida.
- O README corresponde ao comportamento atual da skill.
- O novo conteudo e baseado em fatos e evita texto generico.
- Os arquivos adicionados sao necessarios e apoiam a skill diretamente.
- Os evals foram atualizados quando o comportamento mudou.
