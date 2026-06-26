---
task: "Revisar Relatório e Argumentação"
order: 1
input: |
  - relatorio_tcc: Conteúdo de squads/tcc-documentacao/output/relatorio-tcc.md
  - argumentacao_defesa: Conteúdo de squads/tcc-documentacao/output/argumentacao-defesa.md
  - research_brief: Conteúdo de squads/tcc-documentacao/pipeline/data/research-brief.md
  - quality_criteria: Conteúdo de squads/tcc-documentacao/pipeline/data/quality-criteria.md
  - numero_revisao: Número da rodada de revisão atual (1, 2 ou 3 — máximo de 3 antes de escalar ao usuário)
output: |
  - veredito: Documento estruturado com tabela de pontuação, feedback detalhado e veredito final (APROVAR | REJEITAR | APROVAÇÃO CONDICIONAL) salvo em squads/tcc-documentacao/output/revisao.md
---

# Revisar Relatório e Argumentação

Revisão combinada do relatório de Helena Hipótese e do pacote de
argumentação de Diana Defesa, com scoring por critério e veredito final —
verificando especialmente consistência factual cruzada com o research brief
original.

## Process

1. Carregar quality-criteria.md, o research-brief.md original, o relatório e
   o pacote de argumentação. Ler o relatório completo do início ao fim sem
   pontuar nada durante a leitura.
2. Ler o pacote de argumentação e verificar consistência cruzada: toda tese
   deve corresponder a um trecho específico do relatório e a uma fonte do
   research brief — qualquer divergência factual é registrada para a seção
   de feedback.
3. Pontuar individualmente (escala 1-10, com justificativa escrita) os
   critérios: conformidade ABNT, alinhamento problema-objetivos-resultados,
   solidez das evidências citadas, qualidade da argumentação de defesa,
   clareza/legibilidade.
4. Para cada nota que não seja 10, identificar a passagem exata (capítulo,
   seção, parágrafo ou slide) responsável pela perda de pontos.
5. Aplicar a regra de decisão: APROVAR se média >= 7/10 e nenhum critério < 4;
   REJEITAR se média < 7 ou qualquer critério < 4; APROVAÇÃO CONDICIONAL se
   média >= 7 mas houver critério não-crítico entre 4-6.
6. Para toda rejeição ou condicional, fornecer correção específica e
   acionável, separando "Mudança obrigatória" de "Sugestão (não-bloqueante)".
7. Reconhecer pelo menos um "Ponto forte" explícito, mesmo em rejeição.
8. Registrar o número da revisão atual e o limite de 3 ciclos antes de
   escalar para o usuário no cabeçalho do veredito.

## Output Format

```yaml
veredito:
  conteudo_revisado: "Descrição do que foi revisado"
  revisao_numero: 1
  pontuacao:
    - criterio: "Conformidade ABNT"
      nota: 8
      justificativa: "..."
  media_geral: 8.0
  feedback:
    - tipo: "mudanca_obrigatoria | sugestao | ponto_forte"
      descricao: "..."
      localizacao: "Capítulo/seção/parágrafo/slide exato"
  veredito_final: "APROVAR | REJEITAR | APROVAÇÃO CONDICIONAL"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
==============================
 VEREDITO DA REVISÃO: APROVAÇÃO CONDICIONAL
==============================

Conteúdo: Capítulo 1 (Introdução) + Pacote de Argumentação de Defesa
Revisão: 1 de 3

------------------------------
 TABELA DE PONTUAÇÃO
------------------------------
| Critério                          | Nota  | Resumo                         |
|------------------------------------|-------|--------------------------------|
| Conformidade ABNT (citação/refs)  | 8/10  | 1 referência sem ano completo  |
| Alinhamento problema-objetivos     | 9/10  | Bem ligados                    |
| Solidez das evidências citadas     | 9/10  | Todos rastreáveis ao brief     |
| Qualidade da argumentação de defesa| 6/10  | 1 contra-argumento sem resposta|
| Clareza e legibilidade             | 8/10  | 1 parágrafo longo demais       |
------------------------------
 MÉDIA GERAL: 8,0/10
------------------------------

FEEDBACK DETALHADO:

Ponto forte: A Introdução conecta de forma eficaz o dado de subnotificação
(61%, DataSenado) com os dados de feminicídio do FBSP.

Mudança obrigatória: Na Tese 3 do pacote de argumentação, a resposta
preparada para o contra-argumento da banca está marcada como pendência.
Finalizar com base na documentação técnica real do Amparo antes da
aprovação final.

Sugestão (não-bloqueante): A referência ao TechTudo (2024) está sem ano
completo na lista de referências — conferir conforme NBR 6023:2025.

CAMINHO PARA APROVAÇÃO:
1. Finalizar a resposta da Tese 3.
2. Reenviar como Revisão 2.

VEREDITO: APROVAÇÃO CONDICIONAL — Conteúdo em patamar alto (8,0/10), mas a
resposta pendente da Tese 3 deve ser corrigida antes da aprovação final.
```

## Quality Criteria

- [ ] Toda nota vem com justificativa escrita de pelo menos uma frase.
- [ ] Toda mudança obrigatória aponta localização exata e correção
      específica.
- [ ] O veredito final é consistente com a regra de decisão (média e
      critério mínimo).

## Veto Conditions

Reject and redo if ANY are true:
1. O veredito final não corresponde à regra de decisão aplicada às notas
   atribuídas (ex.: REJEITAR atribuído quando média >= 7 e nenhum critério
   < 4).
2. Uma divergência factual entre o conteúdo revisado e o research-brief.md
   foi identificada na leitura, mas não foi registrada como mudança
   obrigatória/gatilho de rejeição.
