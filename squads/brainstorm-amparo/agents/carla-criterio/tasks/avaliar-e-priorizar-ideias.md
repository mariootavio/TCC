---
task: "Avaliar e Priorizar Ideias"
order: 1
input: |
  - backlog_ideias: Conteúdo de squads/brainstorm-amparo/output/ideias-brainstorm.md (backlog de Bruno Brainstorm)
  - research_brief: Conteúdo de squads/brainstorm-amparo/pipeline/data/research-brief.md (brief de conhecimento de Sofia Sabedoria)
output: |
  - tabela_avaliacao: Tabela com os 7 critérios DFV avaliados por ideia, com os 2 bloqueantes marcados OK/FALHA
  - ranking_rice: Ranking RICE das ideias aprovadas pelos bloqueantes
  - veredito_geral: Veredito final do backlog (APROVAR | REJEITAR | APROVAÇÃO CONDICIONAL) com feedback detalhado
---

# Avaliar e Priorizar Ideias

Avalia cada ideia do backlog contra os 7 critérios de qualidade do checklist
DFV (com 2 bloqueantes), aplica RICE para priorizar as aprovadas, e emite
veredito final estruturado (APROVAR/REJEITAR/APROVAÇÃO CONDICIONAL por ideia e
no geral).

## Process

1. Ler o backlog completo de Bruno Brainstorm e o brief de conhecimento de
   Sofia Sabedoria antes de avaliar qualquer ideia isoladamente.
2. Para cada ideia, aplicar os 7 critérios: (1) alinhamento com a
   missão/público do Amparo, (2) esforço vs. impacto, (3) diferenciação vs.
   benchmarking, (4) risco de segurança da própria funcionalidade caso
   descoberta pelo agressor, (5) validação do problema/dor antes da solução,
   (6) viabilidade técnica realista para o escopo do projeto, (7) ausência de
   scope creep (está dentro do MoSCoW combinado).
3. Tratar os critérios 1 e 4 como bloqueantes: se uma ideia falhar em qualquer
   um dos dois, REJEITAR a ideia independentemente da pontuação nos demais
   critérios.
4. Para as ideias não rejeitadas pelos bloqueantes, aplicar RICE (Reach ×
   Impact × Confidence / Effort) para gerar uma ordem de prioridade.
5. Compilar o veredito final: tabela de pontuação por ideia, ranking RICE das
   aprovadas, e veredito geral do backlog (APROVAR / REJEITAR / APROVAÇÃO
   CONDICIONAL).
6. Se o veredito geral for REJEITAR ou APROVAÇÃO CONDICIONAL, listar mudanças
   obrigatórias específicas por ideia antes de devolver a Bruno Brainstorm.

## Output Format

```yaml
tabela_avaliacao:
  - ideia: "Nome da ideia"
    alinhamento_bloqueante: "OK | FALHA — motivo"
    risco_seguranca_bloqueante: "OK | FALHA — motivo"
    diferenciacao: "Alta | Média | Baixa | -"
    esforco_impacto: "Descrição qualitativa | -"
    veredito_ideia: "APROVAR | REJEITAR"
ranking_rice:
  - ideia: "Nome da ideia aprovada"
    reach: 0
    impact: 0
    confidence: "0%"
    effort: 0
    score_rice: 0.0
veredito_geral: "APROVAR | REJEITAR | APROVAÇÃO CONDICIONAL"
feedback_detalhado: "Pontos fortes, mudanças obrigatórias, caminho para aprovação"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
==============================
 VEREDITO DA REVISÃO: APROVAÇÃO CONDICIONAL
==============================

Conteúdo: Backlog de Bruno Brainstorm — Funcionalidades de rede de apoio e prevenção
Revisão: 1 de 3

------------------------------
 TABELA DE AVALIAÇÃO POR IDEIA
------------------------------
| Ideia | Alinhamento (bloqueante) | Risco Segurança (bloqueante) | Diferenciação | Esforço/Impacto | Veredito |
|---|---|---|---|---|---|
| 1. Alerta silencioso por padrão de comportamento | OK | OK | Alta | Médio/Alto | APROVAR |
| 2. Confirmação anti-falso-positivo | OK | OK | Média | Baixo/Alto | APROVAR |
| 3. Rede de apoio com papéis definidos | OK | FALHA — papel "pode acionar polícia" pode gerar notificação identificável ao agressor se o celular for verificado | - | - | REJEITAR |

------------------------------
 RANKING RICE (IDEIAS APROVADAS)
------------------------------
| Ideia | Reach | Impact | Confidence | Effort | Score RICE |
|---|---|---|---|---|---|
| 2. Confirmação anti-falso-positivo | 8 | 2 | 80% | 1 | 12,8 |
| 1. Alerta silencioso por padrão de comportamento | 6 | 3 | 50% | 4 | 2,25 |

FEEDBACK DETALHADO:

Ponto forte: As ideias 1 e 2 estão diretamente ancoradas em gaps de
mercado documentados por Sofia Sabedoria, com diferenciação clara
frente ao benchmarking.

Mudança obrigatória: A ideia 3 falha no critério bloqueante de risco
de segurança — o rótulo de papel "pode acionar polícia" pode ser
visível se o agressor acessar o celular. Reformular para que os
papéis dos contatos não sejam nomeados de forma identificável na
interface.

CAMINHO PARA APROVAÇÃO:
1. Reformular a ideia 3 com rótulos não identificáveis.
2. Reenviar como Revisão 2.

VEREDITO GERAL: APROVAÇÃO CONDICIONAL — 2 de 3 ideias aprovadas e
priorizadas por RICE; a ideia 3 precisa de ajuste de segurança antes
de entrar no backlog final.
```

## Quality Criteria

- [ ] Toda ideia tem os 7 critérios avaliados, com os 2 bloqueantes
      explicitamente marcados OK/FALHA.
- [ ] Nenhuma ideia que falhe em um critério bloqueante aparece no ranking
      RICE.
- [ ] O veredito geral é consistente com a proporção de ideias aprovadas vs.
      rejeitadas.

## Veto Conditions

Reject and redo if ANY are true:
1. Uma ideia que falhou em um critério bloqueante aparece no ranking RICE.
2. O veredito geral foi emitido sem ao menos um "Ponto forte" registrado.
