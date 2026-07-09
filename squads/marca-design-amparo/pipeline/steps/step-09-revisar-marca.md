---
execution: inline
agent: marina-marca
inputFile: squads/marca-design-amparo/output/design-system.md
outputFile: squads/marca-design-amparo/output/revisao-marca.md
---

# Step 9: Revisar Marca

## Context Loading

Load these files before executing:
- `squads/marca-design-amparo/output/identidade-visual.md` — identidade
  visual aprovada (Flávia)
- `squads/marca-design-amparo/output/design-system.md` — design system
  aprovado no checkpoint Step 8 (Tomás)
- `squads/marca-design-amparo/output/brief-design.md` — brief de marca
  original
- `squads/marca-design-amparo/output/pesquisa-cor-publico.md` — pesquisa
  calibrada de Renata, usada para verificar coerência das escolhas
- `squads/marca-design-amparo/pipeline/data/quality-criteria.md` —
  rubrica completa de revisão
- `.agents/skills/manual-identidade-visual-premium/references/
  vocabulario-design.md` — seção "Palavras a evitar", usada como régua
  extra de precisão de linguagem (lida diretamente, sem invocar a skill
  inteira via Skill tool — essa skill é usada de fato só no Step 11 por
  Helena Manual)

Nota: este step apenas LÊ o projeto Claude Design e os documentos de saída
— não publica nada novo via `DesignSync`. Por isso não há uma mutação
visual a aprovar diretamente aqui; a aprovação de mutações já ocorreu nos
checkpoints anteriores (Steps 1, 3, 5, 7). Este é um step de avaliação.

## Instructions

### Process

1. Carregar todos os materiais de referência (identidade, design system,
   brief, pesquisa de Renata, `quality-criteria.md`) antes de revisar
   qualquer item — entender o que foi prometido antes de avaliar o que foi
   entregue.
2. Percorrer 100% das direções de identidade (mesmo as não recomendadas) e
   100% dos tokens/componentes do design system publicados no Claude
   Design — nunca avaliar por amostragem.
3. Recalcular de forma independente o contraste WCAG AA de cada par de
   cor texto/fundo documentado por Tomás — registrar concordância ou
   divergência explicitamente, nunca apenas aceitar o valor relatado.
4. Auditar consistência de tokens (nenhum componente com valor solto fora
   de um token nomeado) e verificar conformidade trauma-informada
   (nenhuma imagética literal de violência; nenhum vermelho/laranja
   saturado dominante sem justificativa; nome/ícone não expõem o
   propósito do app) — qualquer violação aqui é gatilho de rejeição
   automática.
5. Checar precisão de linguagem: ler `identidade-visual.md` e
   `design-system.md` contra a seção "Palavras a evitar" de
   `vocabulario-design.md` (skill `manual-identidade-visual-premium`) —
   qualquer frase genérica não-quantificada (ex. "cores que transmitem
   confiança", "use com moderação") é correção obrigatória de linguagem,
   citando o trecho exato.
6. Pontuar cada critério (1-10) com justificativa — incluindo o critério
   "Precisão de linguagem" —, calcular o veredito conforme a tabela de
   decisão (média ≥7 sem critério <4 e sem gatilho de discrição/
   trauma-informado violado = APROVAR), incluir ao menos um "Ponto
   forte:", apontar frame/seção/página exata em cada correção obrigatória,
   e salvar em `output/revisao-marca.md`.

## Output Format

The output MUST follow this exact structure:
```
==============================
 VEREDITO DA REVISÃO: [APROVAR | REJEITAR | APROVAR COM RESSALVAS]
==============================
Data: [data]
Material revisado: [identidade-visual.md + design-system.md, projeto Claude Design]

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
 VEREDITO DA REVISÃO: APROVAR COM RESSALVAS
==============================
Data: 2026-06-27
Material revisado: identidade-visual.md (Direção 1 "Porto Seguro") +
design-system.md, publicados no projeto Claude Design "Amparo — Marca &
Design System".

| Critério | Nota | Resumo |
|---|---|---|
| Conformidade trauma-informada | 9/10 | Nenhuma imagética literal de violência; nenhuma cor de alarme dominante |
| Contraste WCAG AA (recalculado) | 5/10 | Branco sobre color-action-emergency = 3.9:1, abaixo de 4.5:1 |
| Consistência de tokens | 8/10 | 1 componente usa opacidade direta em vez de token nomeado |
| Coerência com o brief de marca | 9/10 | Os 3 adjetivos do brief estão claramente refletidos |
| Precisão de linguagem (anti-genérico) | 7/10 | 1 ocorrência de "cores que transmitem confiança" em identidade-visual.md, sem quantificação |
| Qualidade de apresentação no Claude Design | 8/10 | Falta 1 preview HTML de componente |
MÉDIA GERAL: 7.7/10

Nenhum gatilho de rejeição automática violado.

FEEDBACK DETALHADO:

Ponto forte: a Direção 1 ("Porto Seguro") resolve simultaneamente o
requisito de discrição e os 3 adjetivos do brief.

Correção obrigatória: ajustar color-action-emergency para terracotta-600
— no estado atual reprova WCAG AA para texto normal (3.9:1 contra mínimo
de 4.5:1). Localização: design-system.md, seção "Tokens Semânticos", e
design-system/tokens-cor.html no Claude Design.

Correção obrigatória: reescrever "cores que transmitem confiança" em
identidade-visual.md, seção "Justificativa" da Direção 1, substituindo
por uma frase que nomeie a função específica das cores (ex.: "tons frios
cuja função é reduzir alarme visual, calibrados pela pesquisa de Renata")
— frase genérica listada em `vocabulario-design.md` "Palavras a evitar".

Sugestão (não-bloqueante): publicar o preview HTML do componente
Molecules/Alert-Banner.

VEREDITO: APROVAR COM RESSALVAS — média 7.8/10, nenhum gatilho de
segurança/discrição violado, mas a correção de contraste é obrigatória.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. A revisão foi produzida sem percorrer 100% das direções de identidade e
   100% dos componentes do design system.
2. O veredito contradiz a tabela de decisão (ex.: APROVAR com um gatilho
   de discrição/trauma-informado violado).

## Quality Criteria

- [ ] Toda nota tem justificativa escrita com "porque".
- [ ] O contraste WCAG AA foi recalculado de forma independente, não
      apenas copiado do valor de Tomás.
- [ ] Toda correção obrigatória aponta a localização exata (frame, seção
      ou página do projeto Claude Design) e a correção específica.
- [ ] O veredito é consistente com as regras de decisão documentadas.
- [ ] Há ao menos um "Ponto forte:" registrado, mesmo em rejeição.
- [ ] Toda frase genérica encontrada foi checada contra
      `vocabulario-design.md` "Palavras a evitar" e apontada como
      correção obrigatória, com o trecho exato citado.
