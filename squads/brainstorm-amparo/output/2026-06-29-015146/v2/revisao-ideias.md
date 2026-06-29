==============================
 VEREDITO DA REVISÃO: APROVAÇÃO CONDICIONAL
==============================

Conteúdo: Backlog de Bruno Brainstorm — Expansão da biblioteca de disfarces (extensão informal da Rodada 2 / RF-CORE-02): 11 ideias
Revisão: 1 de 3

------------------------------
 TABELA DE AVALIAÇÃO POR IDEIA
------------------------------
| Ideia | Alinhamento (bloqueante) | Risco Segurança (bloqueante) | Diferenciação | Esforço/Impacto | Veredito |
|---|---|---|---|---|---|
| 1. Conversor de moedas/unidades | OK | OK | Alta | Baixo/Baixo | APROVAR |
| 2. Lista de tarefas (to-do) | OK | OK | Média — mesmo gatilho de palavra-chave do bloco de notas; diferenciação está na categoria do app, não no mecanismo. Registrar como observação, não como motivo de rejeição | Baixo/Baixo | APROVAR |
| 3. Lista de compras/mercado | OK | OK | Média — terceira ocorrência do gatilho de palavra-chave (após notas e to-do); mesma observação da ideia 2 | Baixo/Baixo | APROVAR |
| 4. Despertador/alarme | OK | OK — com mudança obrigatória: diferente de um campo de texto/número que apenas "calcula errado" silenciosamente, um alarme malconfigurado pode permanecer agendado e disparar som real mais tarde. A implementação precisa garantir que nenhuma tentativa de código incorreta resulte em um alarme de fato agendado | Alta | Baixo/Médio | APROVAÇÃO CONDICIONAL |
| 5. Rádio/sintonizador de estações | OK | OK | Alta | Médio/Baixo | APROVAR |
| 6. Previsão do tempo (clima) | OK | OK — com mudança obrigatória: a cidade-código não pode ser salva na lista de "cidades favoritas" do app, pois ficaria visível na tela inicial do disfarce a cada abertura (vestígio mais exposto que uma nota perdida em uma lista, Gap 9) | Alta | Baixo/Médio | APROVAÇÃO CONDICIONAL |
| 7. Calendário/Agenda | OK | OK | Média — mesma observação de sobreposição de mecanismo das ideias 2 e 3 | Baixo/Médio | APROVAR |
| 8. Contatos (agenda telefônica) | OK | OK | Alta | Baixo/Baixo | APROVAR |
| 9. Tradutor | OK | OK — com mudança obrigatória: muitos apps de tradução exibem o histórico de traduções recentes diretamente na tela inicial; a frase-código não pode persistir nesse histórico | Alta | Médio/Baixo | APROVAÇÃO CONDICIONAL |
| 10. Mapas/Navegação | OK | OK — com mudança obrigatória: histórico de buscas/locais salvos precisa do mesmo tratamento de limpeza de rastro já exigido na ideia 6 | Alta | Alto/Baixo — para cumprir o padrão "totalmente funcional" (Rodada 2, ideia 1), exigiria geocodificação e navegação reais, esforço desproporcional ao ganho marginal de mais uma opção de disfarce no escopo de um TCC | APROVAÇÃO CONDICIONAL |
| 11. Cronômetro/Timer | OK | OK — com a mesma mudança obrigatória da ideia 4 (nenhuma tentativa incorreta pode resultar em um timer real disparando som ao final) | Alta | Baixo/Baixo | APROVAÇÃO CONDICIONAL |

------------------------------
 RANKING RICE (IDEIAS APROVADAS)
------------------------------
| Ideia | Reach | Impact | Confidence | Effort | Score RICE |
|---|---|---|---|---|---|
| 7. Calendário/Agenda | 10 | 1,5 | 80% | 1 | 12,00 |
| 6. Previsão do tempo (condicional) | 10 | 1,5 | 60% | 1 | 9,00 |
| 1. Conversor de moedas/unidades | 10 | 1 | 80% | 1 | 8,00 |
| 2. Lista de tarefas | 10 | 1 | 80% | 1 | 8,00 |
| 3. Lista de compras/mercado | 10 | 1 | 70% | 1 | 7,00 |
| 8. Contatos | 10 | 1 | 70% | 1 | 7,00 |
| 11. Cronômetro/Timer (condicional) | 10 | 1 | 60% | 1 | 6,00 |
| 5. Rádio/sintonizador | 10 | 1 | 70% | 1,5 | 4,67 |
| 4. Despertador/alarme (condicional) | 10 | 1 | 60% | 1,5 | 4,00 |
| 9. Tradutor (condicional) | 10 | 1 | 60% | 1,5 | 4,00 |
| 10. Mapas/Navegação (condicional) | 10 | 1 | 50% | 5 | 1,00 |

FEEDBACK DETALHADO:

Ponto forte: as 11 ideias mantêm o padrão já validado na Rodada 2 — cada gatilho de destrave imita o uso normal daquele tipo de app (número como código em apps numéricos, palavra-chave em campos de texto livre), o que preserva o princípio central de neutralidade do disfarce sem reinventar a lógica de segurança a cada nova opção. Nenhuma ideia falhou em um critério bloqueante.

Mudança obrigatória (4 itens em Aprovação Condicional, todos com correção objetiva e de baixo esforço):
1. Ideia 4 (Despertador) e Ideia 11 (Timer): garantir, na implementação, que uma tentativa de código incorreta nunca resulte em um alarme/timer real agendado — diferente de um campo de texto, esses dois disfarces têm um "modo de falha" que pode se tornar audível no futuro, não apenas na hora da digitação.
2. Ideia 6 (Previsão do tempo): a cidade-código não pode ser salva na lista de cidades favoritas/persistentes — precisa ser tratada como busca descartável, nunca como item salvo visível na tela inicial do disfarce.
3. Ideia 9 (Tradutor): a frase-código não pode persistir no histórico de traduções recentes exibido na tela inicial do app.
4. Ideia 10 (Mapas/Navegação): recomenda-se reduzir o escopo para um "buscador de endereço simples" (sem navegação/rotas reais) antes de avançar — manter a versão de navegação completa tornaria o esforço desproporcional ao ganho de ter mais uma opção de disfarce, no contexto de um TCC.

Observação não bloqueante: as ideias 2, 3 e 7 (to-do, lista de compras, agenda) compartilham o mesmo mecanismo de gatilho do bloco de notas já aprovado (palavra-chave em campo de texto) — não é motivo de rejeição, mas registra-se como redundância de mecanismo a considerar ao decidir quantas dessas opções entram de fato na biblioteca final de disfarces, para não inflar a lista com variações repetidas do mesmo padrão.

CAMINHO PARA APROVAÇÃO (dos 4 itens condicionais):
1. Despertador (4) e Timer (11): especificar, na fase de design técnico, que o caminho de "código incorreto" nunca chega a agendar um disparo real.
2. Clima (6): especificar que a cidade-código é tratada como busca volátil, não como cidade salva.
3. Tradutor (9): especificar que a frase-código é excluída do histórico de traduções recentes.
4. Mapas (10): decidir entre reduzir escopo para busca de endereço simples ou mover para "Won't have" nesta fase, dado o esforço.

VEREDITO GERAL: APROVAÇÃO CONDICIONAL — as 11 ideias passam nos 2 critérios bloqueantes (nenhuma rejeição de alinhamento ou risco de segurança fundamental); 4 delas têm uma condição de implementação específica e de baixo esforço para resolver antes de entrarem em desenvolvimento. O backlog está arquivado para uso futuro — nenhuma decisão de quais itens implementar foi tomada nesta rodada, a pedido do usuário.
