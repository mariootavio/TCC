---
execution: inline
agent: renata-referencia
inputFile: squads/tcc-documentacao/output/relatorio-tcc.md
outputFile: squads/tcc-documentacao/output/revisao.md
on_reject: 4
---

# Step 6: Revisão de Qualidade

## Context Loading

Load these files before executing:
- `squads/tcc-documentacao/output/relatorio-tcc.md` — relatório de Helena
  Hipótese (Step 4).
- `squads/tcc-documentacao/output/argumentacao-defesa.md` — pacote de
  argumentação de Diana Defesa (Step 5).
- `squads/tcc-documentacao/pipeline/data/research-brief.md` — research
  brief original, usado para verificar consistência factual cruzada.
- `squads/tcc-documentacao/pipeline/data/quality-criteria.md` — rubrica
  completa de critérios de avaliação por agente.

## Instructions

### Process

1. Executar a task `revisar-relatorio-e-argumentacao.md`: ler o relatório e
   o pacote de argumentação por completo antes de pontuar qualquer critério.
2. Pontuar cada critério (1-10, com justificativa): conformidade ABNT,
   alinhamento problema-objetivos-resultados, solidez das evidências,
   qualidade da argumentação de defesa, clareza/legibilidade.
3. Aplicar a regra de decisão (APROVAR / REJEITAR / APROVAÇÃO CONDICIONAL)
   com base na média geral e no critério individual mínimo, registrando
   qualquer divergência factual com o research brief como gatilho de
   rejeição automática.
4. Salvar o veredito estruturado completo em
   `squads/tcc-documentacao/output/revisao.md`. Se o veredito for REJEITAR,
   o pipeline retorna ao Step 4 (`on_reject: 4`) para Helena Hipótese
   corrigir o relatório.

## Output Format

The output MUST follow this exact structure:
```
==============================
 VEREDITO DA REVISÃO: {APROVAR | REJEITAR | APROVAÇÃO CONDICIONAL}
==============================

Conteúdo: {descrição do que foi revisado}
Revisão: {N} de 3

------------------------------
 TABELA DE PONTUAÇÃO
------------------------------
| Critério | Nota | Resumo |
|---|---|---|
{linhas por critério}
------------------------------
 MÉDIA GERAL: {X,X}/10
------------------------------

FEEDBACK DETALHADO:

{Ponto forte: ...}
{Mudança obrigatória: ...}
{Sugestão (não-bloqueante): ...}

CAMINHO PARA APROVAÇÃO:
{lista numerada, se aplicável}

VEREDITO: {repetição do veredito com justificativa de 1-2 frases}
```

## Output Example

```
==============================
 VEREDITO DA REVISÃO: APROVAÇÃO CONDICIONAL
==============================

Conteúdo: Capítulo 1 (Introdução) + Pacote de Argumentação de Defesa
Revisão: 1 de 3

------------------------------
 TABELA DE PONTUAÇÃO
------------------------------
| Critério | Nota | Resumo |
|---|---|---|
| Conformidade ABNT | 8/10 | 1 referência sem ano completo |
| Solidez das evidências | 9/10 | Todos os dados rastreáveis |
| Qualidade da argumentação | 6/10 | 1 contra-argumento sem resposta |
------------------------------
 MÉDIA GERAL: 7,7/10
------------------------------

FEEDBACK DETALHADO:

Ponto forte: A Introdução conecta de forma eficaz o dado de subnotificação
com os dados de feminicídio do FBSP.

Mudança obrigatória: Na Tese 3, a resposta ao contra-argumento da banca
está marcada como pendência. Finalizar com base na documentação técnica
real do Amparo.

CAMINHO PARA APROVAÇÃO:
1. Finalizar a resposta da Tese 3.
2. Reenviar como Revisão 2.

VEREDITO: APROVAÇÃO CONDICIONAL — Conteúdo em patamar alto (7,7/10), mas a
resposta pendente da Tese 3 deve ser corrigida antes da aprovação final.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O veredito final não corresponde à regra de decisão aplicada às notas.
2. Uma divergência factual com o research brief foi identificada mas não
   registrada como mudança obrigatória.

## Quality Criteria

- [ ] Toda nota vem com justificativa escrita.
- [ ] Existe ao menos um "Ponto forte" mesmo em rejeição.
- [ ] O número da revisão atual está registrado no cabeçalho.
