---
execution: inline
agent: carla-criterio
inputFile: squads/brainstorm-amparo/output/ideias-brainstorm.md
outputFile: squads/brainstorm-amparo/output/revisao-ideias.md
on_reject: 4
---

# Step 5: Revisar e Priorizar

## Context Loading

Load these files before executing:
- `squads/brainstorm-amparo/output/ideias-brainstorm.md` — backlog de ideias
  gerado por Bruno Brainstorm (Step 4).
- `squads/brainstorm-amparo/pipeline/data/research-brief.md` — brief de
  conhecimento de Sofia Sabedoria, usado para verificar se cada ideia está de
  fato ancorada em uma dor/gap documentado.
- `squads/brainstorm-amparo/pipeline/data/domain-framework.md` — seções 3
  (checklist DFV) e 4 (RICE), com a regra de decisão completa (critérios
  bloqueantes, limiar de aprovação de 5/7).
- `squads/brainstorm-amparo/pipeline/data/quality-criteria.md` — critérios de
  qualidade da revisão de Carla, incluindo a regra de veredito geral do
  backlog.

## Instructions

### Process

1. Executar a task `avaliar-e-priorizar-ideias.md`: ler o backlog completo de
   Bruno e o brief de Sofia antes de pontuar qualquer ideia isoladamente.
2. Para cada ideia, avaliar os 7 critérios do checklist DFV, marcando os 2
   critérios bloqueantes (alinhamento à missão, risco de segurança) como
   OK/FALHA de forma explícita — falha em qualquer um dos dois rejeita a
   ideia, independentemente da pontuação nos demais 5 critérios.
3. Aplicar RICE apenas às ideias aprovadas pelos bloqueantes, gerando o
   ranking de prioridade (Score = Reach × Impact × Confidence / Effort).
4. Compilar o veredito geral do backlog (APROVAR / REJEITAR / APROVAÇÃO
   CONDICIONAL), com pelo menos um "Ponto forte" registrado mesmo em caso de
   rejeição, e salvar em `squads/brainstorm-amparo/output/revisao-ideias.md`.
   Se o veredito geral for REJEITAR, o pipeline retorna ao Step 4
   (`on_reject: 4`) para Bruno Brainstorm reformular o backlog com base nas
   mudanças obrigatórias listadas.

## Output Format

The output MUST follow this exact structure:
```
==============================
 VEREDITO DA REVISÃO: {APROVAR | REJEITAR | APROVAÇÃO CONDICIONAL}
==============================

Conteúdo: {descrição do que foi revisado}
Revisão: {N} de 3

------------------------------
 TABELA DE AVALIAÇÃO POR IDEIA
------------------------------
| Ideia | Alinhamento (bloqueante) | Risco Segurança (bloqueante) | Diferenciação | Esforço/Impacto | Veredito |
|---|---|---|---|---|---|
{linhas por ideia}

------------------------------
 RANKING RICE (IDEIAS APROVADAS)
------------------------------
| Ideia | Reach | Impact | Confidence | Effort | Score RICE |
|---|---|---|---|---|---|
{linhas por ideia aprovada, ordenadas por Score RICE decrescente}

FEEDBACK DETALHADO:

{Ponto forte: ...}
{Mudança obrigatória: ... (se houver)}

CAMINHO PARA APROVAÇÃO:
{lista numerada, se aplicável}

VEREDITO GERAL: {repetição do veredito com justificativa de 1-2 frases}
```

## Output Example

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
| 3. Rede de apoio com papéis definidos | OK | FALHA — papel "pode acionar polícia" pode gerar notificação identificável ao agressor | - | - | REJEITAR |

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

## Veto Conditions

Reject and redo if ANY of these are true:
1. Uma ideia que falhou em um critério bloqueante aparece no ranking RICE.
2. O veredito geral foi emitido sem ao menos um "Ponto forte" registrado, ou
   é inconsistente com a proporção de ideias aprovadas/rejeitadas.

## Quality Criteria

- [ ] Toda ideia tem os 7 critérios avaliados, com os 2 bloqueantes
      explicitamente marcados OK/FALHA.
- [ ] RICE foi aplicado apenas às ideias já aprovadas pelo filtro de
      bloqueantes.
- [ ] O número da revisão atual está registrado no cabeçalho do veredito.
