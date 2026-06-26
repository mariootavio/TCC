---
execution: inline
agent: wagner-wcag
inputFile: squads/design-ux-ui-amparo/output/telas-prototipo.md
outputFile: squads/design-ux-ui-amparo/output/revisao-design.md
---

# Step 9: Revisar Design

## Context Loading

Load these files before executing:
- `squads/design-ux-ui-amparo/output/telas-prototipo.md` — telas e protótipo entregues por Telma Tela (Step 8)
- `squads/design-ux-ui-amparo/output/design-system.md` — design system aprovado (Flávia)
- `squads/design-ux-ui-amparo/output/fluxos-ux.md` — fluxos de UX aprovados (Joana)
- `squads/design-ux-ui-amparo/pipeline/data/quality-criteria.md` — rubrica completa de revisão
- `squads/design-ux-ui-amparo/agents/wagner-wcag/tasks/revisar-design.md` — task completa com processo e formato de output

Nota: este step apenas LÊ o arquivo Figma (via `get_design_context` /
`get_screenshot`, nativos do ambiente) — não faz nenhuma mutação/escrita no
Figma. Por isso não há checkpoint imediatamente anterior a este step: a
mutação visual já foi aprovada nos checkpoints anteriores (Steps 1, 3, 5, 7);
esta é uma etapa de leitura e avaliação, não de criação ou publicação.

## Instructions

### Process

1. Carregar todos os critérios de referência (design system, fluxos de UX,
   `quality-criteria.md`) antes de revisar qualquer tela — entender o que é
   "bom" antes de avaliar.
2. Percorrer TODAS as telas e o protótipo completo do início ao fim pelo
   menos uma vez antes de pontuar qualquer critério — nunca avaliar por
   amostragem.
3. Pontuar cada critério em escala 1-10 com justificativa: consistência com
   design system, acessibilidade WCAG 2.2 AA, heurísticas de Nielsen,
   aderência à marca, integridade do protótipo navegável, padrões de
   segurança/discrição (este último com prioridade máxima — qualquer
   violação é gatilho de rejeição automática).
4. Calcular o veredito conforme a tabela de decisão (média ≥7 sem critério <4
   e sem gatilho violado = APROVAR). Para toda rejeição, apontar o frame/
   página exato e a correção específica. Incluir ao menos um "Ponto forte:"
   mesmo em rejeição. Registrar o número da revisão atual e salvar em
   `output/revisao-design.md`.

## Output Format

The output MUST follow this exact structure:
```
==============================
 VEREDITO DA REVISÃO: [APROVAR | REJEITAR | APROVAR COM RESSALVAS]
==============================
Revisão: [X de 3]
Data: [data]

| Critério | Nota | Resumo |
|---|---|---|
[uma linha por critério]
MÉDIA GERAL: [X.X/10]

[GATILHO DE REJEIÇÃO AUTOMÁTICA, se aplicável]

FEEDBACK DETALHADO:
[Ponto forte: ...]
[Correção obrigatória: ... / Sugestão (não-bloqueante): ...]

VEREDITO: [resumo final com justificativa]
```

## Output Example

```
==============================
 VEREDITO DA REVISÃO: REJEITAR
==============================
Revisão: 1 de 3
Data: 2026-06-26

| Critério | Nota | Resumo |
|---|---|---|
| Consistência com design system | 8/10 | 1 cor hardcoded detectada |
| Acessibilidade WCAG 2.2 AA | 6/10 | 3 botões abaixo do touch target mínimo |
| Heurísticas de Nielsen | 7/10 | Confirmação ausente em 1 ação irreversível |
| Aderência à marca | 8/10 | Consistente na maior parte das telas |
| Integridade do protótipo | 7/10 | 1 tela morta no fluxo de rede de apoio |
| Padrões de segurança/discrição | 3/10 | Saída rápida ausente em 4 das 22 telas |
MÉDIA GERAL: 6.5/10

GATILHO DE REJEIÇÃO AUTOMÁTICA: Padrões de segurança/discrição pontuou 3/10
— rejeição obrigatória independente da média geral.

FEEDBACK DETALHADO:

Correção obrigatória: saída rápida ausente nos frames "Modal-Captura" e
"Modal-Confirmação-Denúncia" (página "04. Fluxo de Denúncia"). Adicionar o
componente App-Header a esses frames.

Ponto forte: a Tela Neutra de saída rápida está bem executada nas telas em
que o botão está presente — o disfarce é convincente.

VEREDITO: REJEITAR — gatilho de segurança automático (saída rápida ausente em
4 telas) somado a outras correções obrigatórias.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. A revisão foi produzida sem percorrer 100% das telas e do protótipo
   completo.
2. O veredito contradiz a tabela de decisão (ex.: APROVAR com um gatilho de
   segurança violado).

## Quality Criteria

- [ ] Toda nota tem justificativa escrita com "porque".
- [ ] Toda correção obrigatória aponta frame/página exato e correção específica.
- [ ] O veredito é consistente com as regras de decisão documentadas.
- [ ] Há ao menos um "Ponto forte:" registrado, mesmo em rejeição.
