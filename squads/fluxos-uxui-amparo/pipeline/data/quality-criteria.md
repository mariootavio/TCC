# Quality Criteria — Fluxos & UI/Protótipo Amparo

Critérios de qualidade consolidados dos 7 agentes da squad. Cada agente tem
sua própria seção.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Caio Componentes — Design System no Figma

- [ ] Todo token de cor, tipografia e espaçamento existe como Figma Variable (nunca como estilo solto ou valor hardcoded na camada).
- [ ] Todo token e componente reconstruído cita a fonte exata (arquivo + seção) de onde veio.
- [ ] Toda pendência por ausência de informação está registrada explicitamente em `output/design-system-figma.md` — nenhum valor foi inventado para preencher uma lacuna.
- [ ] Todo par de cor texto/fundo do sistema reconstruído foi verificado contra os critérios de contraste WCAG AA documentados pela squad de marca.
- [ ] As regras de design system foram geradas via `figma:figma-create-design-system-rules` e estão disponíveis para os agentes seguintes.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Iara Informação — Arquitetura de Informação

- [ ] Toda funcionalidade do backlog do brainstorm (RF-CORE + ideias priorizadas) aparece classificada em exatamente uma categoria estrutural (Navegação Principal, Ação Global, Ação Secundária/Contextual ou Camada Transversal).
- [ ] Nenhuma funcionalidade mapeada está ausente do backlog real da squad `brainstorm-amparo`.
- [ ] A navegação principal (bottom nav) não excede 5 itens, com agrupamentos justificados quando necessário.
- [ ] Toda lacuna identificada está documentada em seção separada, sem preenchimento por funcionalidade inventada.
- [ ] RF-CORE-06 (classificação de risco) está documentada como Camada Transversal — nunca como item de bottom nav, ação global ou ação secundária isolada — com a lista explícita de telas/fluxos afetados e as 3 ações de sistema (BAIXO/MÉDIO/ALTO) citadas exatamente como em `company.md`.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Daniela Discrição — Segurança e Discrição UX

- [ ] Todo padrão de segurança/discrição documentado tem um racional de risco explícito associado.
- [ ] A regra de saída rápida especifica posição fixa, 1 toque, e transição instantânea sem nenhuma ambiguidade.
- [ ] A política de notificações neutras cobre todas as funcionalidades do backlog que geram notificação (RF-CORE-03, RF-CORE-05, alertas de risco).
- [ ] O RF-CORE-02 foi operacionalizado fielmente, sem reinterpretação do conceito original definido pelo product owner.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Joana Jornada — Fluxos de UX

- [ ] Todo fluxo documentado cita explicitamente o RF-CORE ou ideia do backlog priorizado que implementa.
- [ ] Todo fluxo crítico (emergência, documentação, modo disfarçado, rede de apoio) tem ao menos um caminho de erro/interrupção mapeado com destino definido.
- [ ] Toda decisão de design de fluxo cita a heurística de Nielsen aplicada.
- [ ] Nenhum fluxo contradiz um padrão de segurança/discrição já definido por Daniela Discrição.
- [ ] Todo fluxo/tela sinalizado por Iara como afetado por RF-CORE-06 tem as três variações (BAIXO/MÉDIO/ALTO) desenhadas, citando a ação de sistema exata de `company.md`, sem que o nível de risco bloqueie, atrase ou condicione o acionamento manual de emergência (RF-CORE-01).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Telma Tela — Telas de Alta Fidelidade

- [ ] Toda tela criada usa exclusivamente componentes e tokens já existentes no design system reconstruído por Caio.
- [ ] Toda tela cita o fluxo e o passo exato de `fluxos-ux.md` que ela traduz visualmente.
- [ ] Toda pendência de componente ausente está registrada nomeada para Caio, com o placeholder temporário usado explicitado.
- [ ] Nenhuma conexão de protótipo (overlay, link, Interactive Component) foi criada por Telma — essas conexões pertencem exclusivamente a Pietro.
- [ ] Frames de estados visuais equivalentes entre telas seguem nomenclatura consistente.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Pietro Prototipagem — Protótipo Navegável

- [ ] Todo modal, alerta ou confirmação temporária foi implementado como overlay, nunca como tela duplicada.
- [ ] A ação de saída rápida tem transição instantânea (sem Smart Animate, sem easing) em 100% das ocorrências no protótipo, testada a partir de múltiplos pontos.
- [ ] Todo fluxo crítico de `fluxos-ux.md` (caminho feliz e caminhos de erro) foi testado manualmente, com resultado registrado na tabela de verificação de navegação.
- [ ] Nenhuma tela morta ou link quebrado permanece sem resolução ou sinalização explícita no relatório final.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Wagner WCAG — Revisão de Design

- [ ] 100% das telas e 100% das conexões do protótipo foram percorridas antes de qualquer pontuação — nenhuma avaliação por amostragem.
- [ ] Toda violação de segurança/discrição encontrada está destacada no topo do veredito e foi tratada como gatilho de rejeição automática.
- [ ] O skill `wcag-audit-patterns` foi carregado e aplicado, cobrindo os quatro princípios POUR, além dos critérios WCAG 2.2 já conhecidos pela squad.
- [ ] Toda correção específica cita o frame ou página exata onde o problema foi encontrado.
- [ ] O veredito geral é inequivocamente APROVAR, REJEITAR ou APROVAR COM RESSALVAS — nunca uma formulação ambígua.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Critério de Decisão Transversal (regra herdada por Wagner)

Qualquer violação de um padrão de segurança/discrição definido por Daniela
Discrição é gatilho de rejeição automática do veredito geral de Wagner WCAG,
independentemente da pontuação nos demais critérios — este é o único critério
verdadeiramente bloqueante de toda a squad, refletindo a inegociabilidade do
risco de exposição da usuária no domínio do Amparo.
