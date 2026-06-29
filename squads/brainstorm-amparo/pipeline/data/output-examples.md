# Output Examples — Brainstorm Amparo

Três exemplos completos de outputs finais da squad: o brief de conhecimento de
Sofia Sabedoria, o backlog de ideias de Bruno Brainstorm, e o veredito de revisão
de Carla Critério. Servem como referência de qualidade e profundidade — não como
templates rígidos a copiar literalmente.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Exemplo 1: Brief de Conhecimento (Sofia Sabedoria)

```
BRIEF DE CONHECIMENTO — AMPARO
Foco desta rodada: Funcionalidades de rede de apoio e prevenção
Preparado em: 2026-06-26

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CONHECIMENTO INTERNO DO PROJETO

Funcionalidades já definidas (squad design-ux-ui-amparo): botão de
emergência com acionamento discreto, cofre de documentação segura,
rede de apoio pessoal (contatos de confiança), acesso a profissionais
(psicólogos/assistência jurídica parceira).
Tom de voz: acolhedor, empático, seguro, sem jargão técnico.
Dado-chave já levantado (tcc-documentacao): subnotificação de 61% dos
casos de violência doméstica no Brasil (Fonte: DataSenado, Confiança: ALTA).

CONHECIMENTO EXTERNO — BENCHMARKING

| App | Funcionalidade-chave | Gap documentado |
|---|---|---|
| bSafe | Follow Me + fake call | Acionamento manual, sem detecção automática |
| Circle of 6 | Círculo de 6 contatos pré-definidos | Sem cofre de evidências |
| Guardiã Maria da Penha/SP Mulher Segura | Cruzamento com tornozeleira do agressor | Depende de integração institucional, não replicável sem órgão público |

GAPS DE MERCADO (ESPAÇO EM BRANCO)

1. Nenhum app revisado usa IA ou sinais comportamentais para alertas
   proativos — todos dependem de acionamento manual.
2. Falta de mecanismo anti-falso-positivo padronizado.
3. Foco quase exclusivo em resposta emergencial, pouca prevenção primária.

RECOMENDAÇÃO PARA O BRAINSTORM

Priorizar ideias que explorem os gaps acima, evitando duplicar
funcionalidades já commodity (botão de pânico genérico) sem
diferenciação clara.
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Exemplo 2: Backlog de Ideias (Bruno Brainstorm)

```
BACKLOG DE IDEIAS — BRAINSTORM AMPARO
Foco desta rodada: Funcionalidades de rede de apoio e prevenção
Baseado no brief de conhecimento de Sofia Sabedoria (2026-06-26)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. ALERTA SILENCIOSO POR PADRÃO DE COMPORTAMENTO
   Descrição: monitoramento opcional de padrões de uso do celular
   (ex.: buscas repetidas por "delegacia da mulher", quedas abruptas
   de localização compartilhada) que sugere à usuária, de forma
   discreta, ativar o plano de segurança — sem acionar terceiros
   automaticamente.
   Dor/gap que resolve: gap de mercado #1 do brief (nenhum app revisado
   usa IA/sinais comportamentais para alertas proativos).
   MoSCoW: Should have
   Kano: Encantadora (delighter)
   Diferenciação: nenhum app de benchmarking pesquisado oferece isso;
   não é commodity de mercado.

2. CONFIRMAÇÃO ANTI-FALSO-POSITIVO NO BOTÃO DE EMERGÊNCIA
   Descrição: ao acionar o botão de emergência, um cancelamento
   silencioso de 5 segundos (gesto discreto, não um pop-up visível)
   evita disparo acidental sem expor a usuária a uma tela óbvia.
   Dor/gap que resolve: gap de mercado #2 (falta de mecanismo
   anti-falso-positivo padronizado).
   MoSCoW: Must have
   Kano: Básica (esperada em qualquer app de emergência sério)
   Diferenciação: bSafe e Circle of 6 não documentam esse mecanismo.

3. REDE DE APOIO COM PAPÉIS DEFINIDOS
   Descrição: ao montar a rede de apoio, a usuária define um papel
   para cada contato (ex.: "pode buscar provas", "pode acionar
   polícia", "só para conversar") — evita que todos os contatos
   recebam o mesmo alerta genérico.
   Dor/gap que resolve: Circle of 6 usa círculo fixo sem diferenciação
   de papel; falta de granularidade é uma limitação observada.
   MoSCoW: Could have
   Kano: Performance (quanto mais clara a rede, melhor a resposta)
   Diferenciação: adiciona granularidade ausente no benchmarking.

(Notas de Won't have nesta rodada, registradas para evitar scope
creep: integração com tornozeleira eletrônica do agressor —
depende de órgão público, inviável para o escopo do TCC.)
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Exemplo 3: Veredito de Revisão (Carla Critério)

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
interface (ex.: usar codinomes neutros definidos pela própria
usuária).

CAMINHO PARA APROVAÇÃO:
1. Reformular a ideia 3 com rótulos não identificáveis.
2. Reenviar como Revisão 2.

VEREDITO GERAL: APROVAÇÃO CONDICIONAL — 2 de 3 ideias aprovadas e
priorizadas por RICE; a ideia 3 precisa de ajuste de segurança antes
de entrar no backlog final.
```
