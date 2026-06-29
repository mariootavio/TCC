==============================
 VEREDITO DA REVISÃO: APROVAÇÃO CONDICIONAL
==============================

Conteúdo: Backlog de Bruno Brainstorm — Interface disfarçada/camuflada (implementação e extensão do RF-CORE-02): 12 ideias
Revisão: 1 de 3

------------------------------
 TABELA DE AVALIAÇÃO POR IDEIA
------------------------------
| Ideia | Alinhamento (bloqueante) | Risco Segurança (bloqueante) | Diferenciação | Esforço/Impacto | Veredito |
|---|---|---|---|---|---|
| 1. Biblioteca de disfarces totalmente funcionais | OK | OK | Alta | Alto/Alto | APROVAR |
| 2. Destrave por código numérico disfarçado de operação matemática | OK | OK | Alta | Médio/Alto | APROVAR |
| 3. Destrave por palavra-chave em nota/campo de busca | OK | OK | Alta | Baixo/Médio | APROVAR |
| 4. Gesto de destrave sem digitação | OK | OK | Média | Médio/Baixo | APROVAR |
| 5. Falha silenciosa no destrave (sem mensagem de erro) | OK | OK | Alta | Baixo/Alto | APROVAR |
| 6. Notificações sempre disfarçadas, nunca com conteúdo real | OK | OK | Alta | Médio/Alto | APROVAR |
| 7. Limpeza do snapshot na lista de apps recentes/multitarefa | OK | OK | Alta | Médio/Alto | APROVAR |
| 8. Criptografia real dos dados, independente do disfarce visual | OK | OK | Alta | Alto/Alto | APROVAR |
| 9. Nome e ficha da loja desvinculados de "Amparo" | OK | OK | Média | Médio/Médio | APROVAÇÃO CONDICIONAL — viabilidade depende de política da Apple App Store (ver Mudança Obrigatória) |
| 10. Orientação no onboarding contra reconhecimento do padrão | OK | OK | Alta | Baixo/Médio | APROVAR |
| 11. Sugestão adaptativa de disfarce com base no uso real do aparelho | OK | FALHA — a leitura automática da lista de apps instalados exige permissão de sistema (ex.: consulta de pacotes instalados no Android) que aparece no rótulo de privacidade da loja e nas configurações de permissões do app; uma "calculadora" solicitando esse acesso é, em si, um vestígio técnico que denuncia o disfarce — a própria funcionalidade recria exatamente o Gap 9 que o restante do backlog tenta fechar | - | - | REJEITAR |
| 12. Saída de emergência generalizada para qualquer disfarce | OK | OK | Alta | Médio/Alto | APROVAR |

------------------------------
 RANKING RICE (IDEIAS APROVADAS)
------------------------------
| Ideia | Reach | Impact | Confidence | Effort | Score RICE |
|---|---|---|---|---|---|
| 5. Falha silenciosa no destrave | 10 | 3 | 100% | 1 | 30,00 |
| 6. Notificações sempre disfarçadas | 10 | 3 | 100% | 2 | 15,00 |
| 7. Limpeza do snapshot multitarefa | 10 | 2 | 80% | 1,5 | 10,67 |
| 12. Saída de emergência generalizada | 10 | 2 | 80% | 1,5 | 10,67 |
| 9. Nome/ficha da loja desvinculados (condicional) | 10 | 2 | 50% | 1 | 10,00 |
| 10. Orientação no onboarding | 10 | 1 | 80% | 1 | 8,00 |
| 8. Criptografia real dos dados | 10 | 3 | 100% | 4 | 7,50 |
| 2. Código numérico disfarçado de calculadora | 8 | 3 | 50% | 2 | 6,00 |
| 3. Palavra-chave em nota/campo de busca | 6 | 2 | 50% | 1 | 6,00 |
| 1. Biblioteca de disfarces totalmente funcionais | 10 | 3 | 100% | 6 | 5,00 |
| 4. Gesto de destrave sem digitação | 4 | 1 | 50% | 2 | 1,00 |

FEEDBACK DETALHADO:

Ponto forte: as ideias 5, 6, 7 e 8 fecham diretamente o Gap 9 do brief de Sofia Sabedoria (vestígios técnicos e ausência de criptografia real nos vault apps revisados) com medidas concretas e tecnicamente fundamentadas em literatura peer-reviewed (Ruffin et al., WPES 2022; EFF, 2026) — raro nível de rigor técnico para uma rodada de brainstorm em estágio de TCC, e nenhuma delas é commodity de mercado: o próprio benchmarking mostra que a maioria das implementações comerciais de vault apps falha exatamente nesses pontos.

Mudança obrigatória (ideia 11): a ideia "Sugestão adaptativa de disfarce com base no uso real do aparelho" falha no critério bloqueante de risco de segurança porque a forma proposta de implementação (ler automaticamente a lista de apps instalados no aparelho) introduz, ela mesma, um vestígio técnico — a permissão de consulta de pacotes instalados aparece no rótulo de privacidade da loja de apps e nas configurações do sistema, o que é incoerente com um app disfarçado de calculadora ou bloco de notas. Reformulação sugerida: manter a intenção original (evitar duplicidade visual de disfarces, ex. "duas calculadoras" na tela) sem depender de leitura automática de pacotes instalados — por exemplo, oferecer a personalização por meio de uma lista estática de sugestões que a própria usuária descarta manualmente durante a configuração, sem qualquer permissão de leitura de apps de terceiros.

Mudança obrigatória (ideia 9): a viabilidade desta ideia depende de uma validação de política de loja não confirmada nesta rodada — a fonte que a fundamenta (NNEDV/Safety Net Project) documenta que a Apple App Store pode exigir que a descrição pública do app revele sua função real, o que anularia o efeito pretendido no iOS. Antes de comprometer esforço de implementação, validar diretamente nas diretrizes vigentes da App Store (e, se necessário, tratar como estratégia Android-only nesta fase do projeto).

Nota de sequenciamento (não altera o ranking RICE, mas é relevante para o roadmap): apesar de aparecerem em posições mais baixas do ranking RICE, as ideias 1 (biblioteca de disfarces) e 2 (código numérico de destrave) são pré-requisitos estruturais de quase todas as demais ideias aprovadas — RICE prioriza valor relativo de cada ideia isoladamente, não ordem de dependência técnica. Recomenda-se que o roadmap trate 1 e 2 como base de implementação inicial, independentemente de sua posição no ranking.

CAMINHO PARA APROVAÇÃO:
1. Reformular a ideia 11 removendo a dependência de leitura automática de apps instalados, preservando a intenção de evitar duplicidade visual de disfarces.
2. Devolver a ideia 11 a Bruno Brainstorm para reformulação — não descartar do backlog nem aceitar com ressalva registrada, conforme preferência já confirmada pelo usuário em rodada anterior desta squad para casos de falha em critério bloqueante de uma ideia específica.
3. Validar a viabilidade de política de loja da ideia 9 (Apple App Store) antes de avançar a implementação; manter sua Aprovação Condicional até essa validação.
4. Reenviar como Revisão 2, caso o usuário opte por essa reformulação no checkpoint final.

VEREDITO GERAL: APROVAÇÃO CONDICIONAL — 10 das 12 ideias aprovadas sem ressalva, 1 em Aprovação Condicional por dependência de validação externa (política de loja), e apenas 1 rejeitada por falha em critério bloqueante de segurança, com caminho de reformulação claro. O backlog está pronto para o checkpoint final de aprovação do usuário, com a recomendação explícita de devolver a ideia 11 a Bruno Brainstorm antes de considerar este ciclo encerrado.
