ARQUITETURA DE INFORMAÇÃO — AMPARO
Fontes: `squads/brainstorm-amparo/output/2026-06-27-145210/v1/ideias-brainstorm.md` (17 ideias, RICE) +
`squads/brainstorm-amparo/pipeline/data/research-brief.md` (RF-CORE-01 a RF-CORE-05) +
`_opensquad/_memory/company.md` (RF-CORE-06 — classificação de risco) +
`squads/fluxos-uxui-amparo/output/2026-08-13-091237/v1/design-system-figma.md` (Caio Componentes, Step 2).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

AÇÕES GLOBAIS (acesso instantâneo, de qualquer tela)

1. Botão do pânico/SOS — RF-CORE-01. Justificativa: pesquisa de UX de segurança exige acionamento de emergência em no máximo 1-2 toques, de qualquer ponto do app, mesmo com tela bloqueada. Componente Figma: "Botão SOS" (Caio, Step 2).
2. Modo disfarçado / saída rápida — RF-CORE-02. Justificativa: mesma exigência de acesso instantâneo; operacionalização detalhada cabe a Daniela Discrição no Step 4.

NAVEGAÇÃO PRINCIPAL (bottom nav — 5 itens, no limite)

1. **Início** — painel resumo. Consolida RF-CORE-03 (acesso rápido a chat), RF-CORE-04 (acesso rápido a documentação), RF-CORE-05 (status da rede de guardiões). É também a tela onde a Camada Transversal RF-CORE-06 (classificação de risco) se manifesta visualmente — ver seção própria abaixo.
2. **Documentação** — RF-CORE-04 (registro de ocorrências com evidências). Contextualiza Ideia 3 (backup criptografado automático) e Ideia 4 (indicador de integridade da prova) como comportamentos internos deste fluxo — ver Ações Secundárias.
3. **Rede de Apoio** — RF-CORE-05 (rede de guardiões). Inclui como sub-seção a Ideia 6 priorizada "Perfis de dependentes na rede de apoio" (RICE alto, alinhada à Lei 15.384/2026) — não é destino de nav separado, vive dentro deste item.
4. **Chat de Apoio** — RF-CORE-03 (chat com profissional de apoio). O conteúdo de apoio aqui exibido deve seguir a Ideia 14 "Conteúdo culturalmente adaptado ao perfil brasileiro de vítimas" (característica de conteúdo, não uma tela nova).
5. **Mais** — agrupa 4 itens de uso pouco frequente/RICE menor, evitando exceder 5 itens na bottom nav:
   - "Central de Conteúdo e Direitos" — Ideia 11 "Biblioteca de direitos e legislação simplificada" (Should have) + Ideia 14 "Conteúdo de apoio culturalmente adaptado ao perfil brasileiro de vítimas" (Should have), unificadas em um único destino de conteúdos explicativos (legislação + apoio psicológico/educativo), conforme decisão do usuário no checkpoint Step 6 (2026-08-13).
   - Ideia 9 "Assistente conversacional de triagem de risco (IA leve, on-device)" (Could have) — distinto de RF-CORE-06: este é um chat orientador que a usuária aciona manualmente; RF-CORE-06 é uma classificação automática de risco em segundo plano. Não confundir os dois no Step 5.
   - Ideia 15 "Relatos anônimos filtrados por contexto" (Could have)
   - **"Delegacias Próximas"** (NOVO — decisão do usuário no checkpoint Step 6, 2026-08-13): localizador de delegacias mais próximas da usuária. Fonte: `AMPARO_TCC_Apresentacao.pdf`, seção "Trabalhos Futuros" — originalmente fora do escopo do TCC II, promovido para o escopo atual por decisão explícita do product owner. Não é um item do backlog RICE da squad `brainstorm-amparo`; deve ser registrado como pendência nessa squad para rastreabilidade em rodadas futuras de ideação, mas já é uma decisão de produto vinculante para esta squad a partir de agora.

AÇÕES SECUNDÁRIAS/CONTEXTUAIS

1. Anexar evidência (foto/áudio/vídeo) — contextual dentro do fluxo de Documentação (RF-CORE-04).
2. Backup criptografado automático em nuvem (Ideia 3, Must have) — comportamento automático disparado ao salvar uma evidência em Documentação; não é uma tela própria.
3. Indicador de integridade da prova — hash + selo de tempo (Ideia 4) — exibido na tela de detalhe de uma evidência já registrada, dentro de Documentação.
4. Confirmar recebimento de alerta — contextual dentro do fluxo de Rede de Apoio, acionado a partir de uma notificação (RF-CORE-05).
5. Encaminhamento institucional automático pós-confirmação dos guardiões (Ideia 5) — ação de 1 toque exibida após um guardião confirmar uma emergência real, dentro de Rede de Apoio.
6. Verificação de bem-estar periódica / check-in ativo (Ideia 1, Should have) — configurável dentro de "Configurações de Segurança" (a criar por Telma sob Mais ou Início); o status do check-in aparece como indicador contextual em Início.
7. Detecção de padrão de risco em segundo plano (Ideia 2, Could have) — opt-in dentro de Configurações de Segurança; sugestão de revisão do plano de segurança aparece contextualmente em Início, nunca como notificação de terceiros.
8. SOS sem conexão de dados, com acionamento sem rastro visível (Ideia 8, Must have) — não é destino de navegação; é o caminho de erro/fallback da Ação Global 1 (RF-CORE-01) quando não há conectividade. Detalhamento de fluxo cabe a Joana Jornada (Step 5).
9. Pesquisa de acompanhamento pós-uso (Ideia 12, Could have) — prompt opcional e anônimo exibido contextualmente após o uso de Ação Global 1 (SOS) ou do assistente de triagem (Ideia 9); nunca um destino de navegação persistente.
10. Convite discreto entre usuárias (Ideia 16, Could have) — ação contextual dentro de Configurações/Compartilhar, camuflada como conteúdo neutro (RF-CORE-02 como inspiração de discrição).
11. Onboarding via QR code em pontos de acolhimento (Ideia 17, Could have) — fluxo de pré-navegação (antes da bottom nav existir), acionado fora do app pelos pontos físicos de acolhimento.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CAMADAS TRANSVERSAIS (modulam outras funcionalidades — nunca destinos de navegação)

1. **RF-CORE-06 — Classificação de Risco (IA/ML)**. Fonte: company.md. Telas/fluxos afetados:
   - Início: BAIXO exibe monitoramento discreto + conteúdo educativo; MÉDIO adiciona alerta discreto pré-configurado + recursos de apoio; ALTO prioriza a Ação Global 1 (SOS) na hierarquia visual da tela.
   - Documentação (RF-CORE-04): nível ALTO aciona proteção reforçada das evidências (prioriza a Ideia 3, backup imediato).
   - Confirmar recebimento de alerta (ação secundária 4): o texto da notificação gerada em nível MÉDIO/ALTO segue a política de notificações neutras de Daniela Discrição (Step 4) — Iara só sinaliza o gatilho, não o texto.
   Desenho detalhado de cada variação por nível de risco é responsabilidade de Joana Jornada (Step 5). Adicionalmente, por decisão do usuário no checkpoint Step 6, Joana também documenta o **fluxo interno do próprio RF-CORE-06** (pipeline de classificação App → Backend → API de IA → resultado), não apenas seus efeitos nas telas — ver Fluxo 5 em `fluxos-ux.md`.

2. **Modo Offline Completo (Ideia 7, Must have)**. Fonte: backlog brainstorm-amparo, Gap 3. Telas/fluxos afetados: plano de segurança, lista de guardiões (Rede de Apoio), registro de evidências (Documentação) e rota de fuga continuam acessíveis sem internet; sincronização criptografada ocorre quando a conectividade retorna. Afeta todos os itens de Navegação Principal exceto Chat de Apoio (que depende de conexão em tempo real com o profissional). Joana Jornada deve mapear o estado "offline" como uma variação transversal adicional, à parte de RF-CORE-06.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FORA DO ESCOPO DESTA ARQUITETURA

- **Ideia 13 "Painel de indicadores de segurança agregados"** (Could have) — o próprio backlog define como "painel interno, não voltado à usuária final". Não é uma tela do app mobile Amparo; pertence a uma superfície administrativa/de pesquisa separada. Não classificado em nenhuma das categorias acima nem mapeado por Telma/Pietro nesta squad.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

LACUNAS IDENTIFICADAS (sem funcionalidade correspondente no backlog)

1. **Onboarding padrão pós-instalação (sem QR code):** o backlog prioriza "Onboarding via QR code em pontos de acolhimento" (Ideia 17) como canal de aquisição, mas não há funcionalidade documentada cobrindo o onboarding padrão (sem QR code) para quem instala o app por conta própria. Sinalizado para decisão do usuário — não preenchido nesta arquitetura.
2. **Componente de navegação "bottom nav" ausente no design system Figma:** `design-system-figma.md` (Caio, Step 2) só reconstruiu Botão, Botão SOS, Input e Card — nenhum componente de barra de navegação inferior existe ainda no Figma, embora esta arquitetura defina 5 itens de bottom nav. Pendência para Telma Tela (Step 7): sinalizar para Caio a necessidade de um componente novo, nunca criar um ad-hoc sem token.
