BRIEF DE CONHECIMENTO — AMPARO
Foco desta rodada: Tipos de disfarce do aplicativo — expansão para além das ideias já validadas
Preparado em: 2026-06-29

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

REAFIRMAÇÃO DO RECORTE RECEBIDO NO CHECKPOINT

O FOCO desta rodada é a expansão da biblioteca de tipos de disfarce do RF-CORE-02 para além do conjunto já gerado e validado nas rodadas anteriores. O recorte de benchmarking aprovado no checkpoint é INTERNO: pular pesquisa externa nova e reutilizar apenas o que a squad tcc-documentacao e as rodadas anteriores desta squad já levantaram.

O que ESTÁ dentro do escopo de ideação:
- Novos tipos de disfarce (aliases visuais) ainda não gerados por Bruno nas rodadas anteriores (ver lista de ideias já validadas abaixo — Bruno deve evitá-las)
- Estratégias de implementação de UX/fluxo para hardening de notificações push (Gap 9) — não apenas diagnóstico do problema, mas ideias concretas de como resolver
- Mecanismos extras de "camuflagem de segundo nível" contra reconhecimento do padrão pelo agressor (Gap 10) — além do que já foi gerado
- Variantes de gatilho/destrave ainda não exploradas nas rodadas anteriores (Gap 11)

O que NÃO ESTÁ dentro do escopo desta rodada:
- Propor "criar" um modo disfarçado (RF-CORE-02 já está decidido como requisito central)
- Repetir qualquer um dos 11 tipos de disfarce já validados na rodada informal de 29/06 (listados abaixo em IDEIAS JÁ VALIDADAS)
- Repetir os tipos originais do RF-CORE-02 (calculadora, diário/bloco de notas, app de previsão do tempo)
- Repetir os 12 mecanismos de implementação/hardening aprovados na Rodada 2 (28/06) — esses já estão no backlog validado
- Trabalhar os Gaps 1-8 herdados de rodadas anteriores (fora do recorte de disfarce/stealth)
- Realizar pesquisa web ou benchmarking externo novo

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CONHECIMENTO INTERNO DO PROJETO

Funcionalidades já existentes/planejadas — pilares de alto nível (origem: company.md):
1. Proteção imediata (emergência)
2. Documentação segura
3. Rede de apoio pessoal
4. Acesso a profissionais

Requisitos centrais já definidos — NÃO são ideias de brainstorm, são decisões de produto tomadas:

| ID | Nome | Descrição resumida | Frente |
|---|---|---|---|
| RF-CORE-01 | Botão do pânico / SOS | Acionamento rápido de emergência com localização em tempo real; funciona com tela bloqueada | Proteção imediata + Rede de apoio |
| RF-CORE-02 | Modo disfarçado | App se camufla com ícone e tela inicial falsos escolhidos pela usuária; troca de aparência sem desinstalar | Camada transversal de segurança/discrição |
| RF-CORE-03 | Chat com profissional de apoio | Canal sigiloso com psicólogos, assistentes sociais ou voluntários; apagar histórico com um toque | Acesso a profissionais |
| RF-CORE-04 | Registro de ocorrências com evidências | Documentação com texto, foto, áudio e vídeo; arquivos criptografados com metadados para uso como prova legal | Documentação segura |
| RF-CORE-05 | Rede de guardiões | Cadastro de pessoas de confiança com comunicação bidirecional segura e alertas em situações de risco | Rede de apoio pessoal |

ATENÇÃO ESPECIAL — RF-CORE-02: "O app se camufla com ícone e tela inicial falsos escolhidos pela usuária (aliases sugeridos: calculadora, diário, app de tempo). Troca de aparência sem desinstalar." Esta é uma decisão de produto já tomada. O espaço de ideação desta rodada é exclusivamente sobre (a) quais novos tipos de disfarce concretos oferecer além dos já validados, (b) estratégias de UX de hardening de notificações, (c) mecanismos extras de camuflagem de segundo nível e (d) variantes de gatilho/destrave ainda não exploradas.

Tom de voz (origem: company.md): Acolhedor, empático, seguro e claro — sem jargão técnico. Relevante para esta rodada: nomes de disfarces e fluxos de destrave devem ser triviais/cotidianos para a usuária sob estresse. Evitar PINs longos ou gestos complexos que ela possa esquecer em situação de pânico. Telas de disfarce devem ser absolutamente banais, nunca alarmistas.

Público-alvo (origem: company.md): mulheres em situação de risco (público crítico desta rodada); órgãos e autoridades; banca acadêmica (avaliará o rigor técnico do hardening proposto — relevante para o TCC).

IDEIAS JÁ VALIDADAS NAS RODADAS ANTERIORES — Bruno NÃO deve repetir nenhum destes itens:

Tipos de disfarce originais do RF-CORE-02 (já citados antes de qualquer rodada de brainstorm):
- Calculadora (com destrave por código numérico disfarçado de operação matemática — ideia 2 da Rodada 2)
- Diário / Bloco de notas (com destrave por palavra-chave — ideia 3 da Rodada 2)
- App de previsão do tempo / Clima (com destrave por cidade-código — ideia 6 da Rodada Informal)

11 tipos de disfarce gerados e validados na Rodada Informal (29/06, extensão direta da Rodada 2):
1. Conversor de moedas/unidades — destrave: converter valor numérico específico (ex.: "1207")
2. Lista de tarefas (to-do) — destrave: criar tarefa com título-chave específico
3. Lista de compras/mercado — destrave: adicionar item com nome-chave específico
4. Despertador/alarme — destrave: configurar alarme para horário específico (ex.: 03:33) [condicional: tentativa incorreta nunca agenda alarme real]
5. Rádio/sintonizador de estações — destrave: digitar "frequência" específica (ex.: 98.7)
6. Calendário/Agenda — destrave: criar evento com título-chave em data específica
7. Contatos (agenda telefônica) — destrave: criar contato com nome-chave (ex.: "Manutenção Ar Condicionado")
8. Tradutor — destrave: traduzir frase/palavra-chave específica [condicional: frase-código não persiste no histórico]
9. Mapas/Navegação — destrave: buscar endereço com nome de local específico [condicional: histórico de busca deve ser limpo]
10. Cronômetro/Timer — destrave: configurar duração específica (ex.: 7 min 43 s) [condicional: tentativa incorreta nunca agenda timer real]
11. (Clima/Previsão do tempo detalhado) — já listado acima como original do RF-CORE-02

Mecanismos de implementação/hardening validados na Rodada 2 (28/06) — também fora do escopo de ideação desta rodada (já estão no backlog):
- Biblioteca de disfarces totalmente funcionais (não apenas fachada visual)
- Destrave por código numérico disfarçado de operação matemática
- Destrave por palavra-chave em nota ou campo de busca
- Gesto de destrave como alternativa sem digitação
- Falha silenciosa no destrave (sem mensagem de erro visível)
- Notificações sempre disfarçadas, nunca com conteúdo real
- Limpeza do snapshot na lista de apps recentes/multitarefa
- Criptografia real dos dados, independente do disfarce visual
- Nome e ficha da loja de apps desvinculados da marca "Amparo" [condicional: política Apple]
- Orientação no onboarding para reduzir risco de reconhecimento do padrão
- Sugestão de disfarces alternativos por escolha manual, sem leitura de apps instalados (reformulada)
- Saída de emergência generalizada para qualquer disfarce escolhido

Descartados explicitamente (Won't Have — Bruno não deve retomar):
- Navegador/browser com URL falsa como gatilho (histórico difícil de limpar)
- App de álbum/galeria protegida por senha (padrão reconhecível por agressor familiarizado com vault apps)
- Gravador de áudio/notas de voz (vestígio de arquivos de áudio reais)
- Upload livre de ícone personalizado pela usuária (iOS não suporta ícone arbitrário em tempo real)
- Leitura automática da lista de apps instalados para personalização (vestígio técnico que denuncia o disfarce)

Dados-chave tcc-documentacao reutilizados (mesma fonte/confiança — sem repesquisa):
1. Brasil (2024): 1.492 feminicídios — maior número da série histórica desde 2015. Confiança: ALTA. Fonte: FBSP/19º Anuário Brasileiro de Segurança Pública.
2. Perfil das vítimas (2024): 63,6%-64% mulheres negras; 70,5%-71% entre 18-44 anos; 8 em 10 mortas por companheiro/ex; 64,3% dos crimes dentro da própria residência. Confiança: ALTA. Fonte: FBSP. Nota de relevância direta para RF-CORE-02: 64,3% dos crimes ocorrem dentro do domicílio — o agressor tem acesso físico prolongado ao celular da vítima, tornando a "revisão manual/forense doméstica" o vetor de risco mais crítico, não apenas um cenário teórico.
3. Subnotificação: fenômeno confirmado (Atlas da Violência), sem percentual nacional oficial. Confiança: ALTA para existência, BAIXA para qualquer número.
4. Ligue 180 (2024): 750.687 atendimentos, 132.084 denúncias (+15,2%). Confiança: ALTA. Fonte: dados oficiais Ligue 180.
5. Lei 15.125/2025: permite cumular MPU com monitoração eletrônica do agressor e botão do pânico em app. Confiança: ALTA.
6. Lei 15.384/2026: tipifica violência vicária e amplia rede de apoio para incluir dependentes. Confiança: ALTA.
7. Lei 14.022/2020: precedente legal para canais digitais/remotos de MPU — sustenta viabilidade jurídica de fluxos 100% via app. Confiança: ALTA.

CONHECIMENTO EXTERNO — BENCHMARKING

NOTA: benchmarking externo PULADO nesta rodada por recorte aprovado no checkpoint Step 1 (decisão do usuário em 2026-06-29). Nenhuma pesquisa web nova foi realizada.

Referências externas levantadas nas rodadas anteriores (preservadas para rastreabilidade — não expandidas nesta rodada):
- Aspire News App (When Georgia Smiled / Robin McGraw, EUA): único app de violência doméstica com disfarce documentado robusto; ícone e interface de app de notícias; 3 toques na barra superior aciona alerta; botão "X" leva instantaneamente a trecho aleatório do app de notícias. Falha documentada: em 2020, gravações de voz das usuárias ficaram expostas em servidor desprotegido (TechCrunch/Bitdefender). Confiança: ALTA.
- PenhaS, SP Mulher, Juntas (PLP 2.0), Circle of 6, bSafe, myPlan: nenhuma evidência de disfarce de ícone/tela documentada nesta nem na pesquisa anterior. Confiança: MÉDIA (ausência de evidência, não prova definitiva).
- Vault apps / Calculator vault apps (Ruffin, Lopez-Toledo, Levchenko, Wang — WPES 2022, ACM): 20 apps analisados; apenas 5 ativam disfarce automaticamente na instalação; a maioria não criptografa os dados por trás da UI. Confiança: ALTA.
- Stalkerware e Intimate Partner Surveillance: Freed et al. (CHI 2018), Chatterjee et al. (USENIX): agressores já familiarizados com lógica de apps disfarçados pelo lado ofensivo. Refuge (UK, 2019): 72% das mulheres atendidas relataram abuso tecnológico. Confiança: ALTA.
- NNEDV/Safety Net Project ("So You Wanna Build an App? Safety First"): Apple App Store pode exigir descrição que revele função real do app; nome real pode aparecer na busca da loja; atualizações podem alterar ícone sem aviso. Confiança: ALTA.
- EFF (abril/2026): notificações push expõem conteúdo sensível na tela de bloqueio; mitigação padrão é configurar preview para "Nunca" ou "Somente quando desbloqueado". Confiança: ALTA.
- VIDE (Vault app IDentification and Extraction system, ScienceDirect): sistema automatizado para identificar e extrair dados de vault apps em iOS. Confiança: ALTA.

GAPS DE MERCADO (ESPAÇO EM BRANCO)

Gaps 1-8 — preservados para rastreabilidade histórica, fora do foco de ideação desta rodada:
- Gap 1: dependência de acionamento manual (alerta proativo ausente)
- Gap 2: vulnerabilidade de armazenamento de provas
- Gap 3: ausência de IA/modo offline
- Gap 4: falta de evidência de eficácia
- Gap 5: sub-representação racial/demográfica
- Gap 6: baixa adoção/divulgação no Brasil
- Gap 7: fragmentação de rede de apoio pessoal/institucional
- Gap 8: ausência de decision aid validado no Brasil
Esses gaps foram trabalhados na Rodada 1 (2026-06-27) e permanecem no backlog para rodadas futuras.

Gaps 9-11 — FOCO DESTA RODADA — disfarce/stealth:

Gap 9 — Ausência de hardening contra vestígios técnicos no padrão de disfarce de apps de violência doméstica
Descrição: nenhum app de violência doméstica revisado (incluindo Aspire News App) trata publicamente dos vetores de vazamento identificados na literatura de vault/stalkerware apps. Confiança: ALTA quanto a cada vetor; MÉDIA quanto à ausência total de tratamento público por qualquer app do benchmarking.
Vetores documentados: (1) notificações push na tela de bloqueio (EFF, 2026); (2) vestígios em lista de apps recentes/multitarefa (Ruffin et al., WPES 2022); (3) nome real persistente na busca da loja de apps (NNEDV/Safety Net Project); (4) dados sem criptografia real por trás do disfarce visual (Ruffin et al.; VIDE/ScienceDirect; Paraben Corporation).

Sub-espaços do Gap 9 com aspectos AINDA NÃO ideados por Bruno (foco de novas ideias desta rodada):
- Notificações push: a ideia 6 da Rodada 2 ("Notificações sempre disfarçadas, nunca com conteúdo real") está aprovada, mas trata o problema pela perspectiva do conteúdo da notificação. NÃO foram ainda geradas ideias sobre: (a) como o app deve se comportar quando o usuário bloqueia completamente as notificações (descoberta torna o app inútil para alertas de guardião); (b) qual o fluxo de UX de configuração de privacidade de notificações guiado pelo próprio app durante o onboarding; (c) se notificações silenciosas/invisíveis (silent push) são uma alternativa viável no iOS/Android e como o fluxo de UX se adapta a isso.
- Multitarefa/snapshot: a ideia 7 da Rodada 2 ("Limpeza do snapshot na lista de apps recentes") está aprovada. NÃO foram geradas ideias sobre: (a) o que mostrar como thumbnail substituto na lista de recentes — tela em branco, última tela do disfarce, algo diferente?; (b) comportamento do app quando é acessado por assistentes de voz (Siri, Google Assistant) que podem exibir o nome real do app nas sugestões de recentes.
- Loja de apps: a ideia 9 da Rodada 2 ("Nome e ficha da loja desvinculados de 'Amparo'") está em aprovação condicional por dependência de validação de política da Apple. NÃO foram geradas ideias sobre: (a) como orientar a usuária, dentro do próprio app, a renomear o ícone manualmente na tela inicial para um nome neutro (funcionalidade disponível no iOS 14+ e Android); (b) se o app deve sugerir um nome de atalho neutro para o ícone na tela inicial durante o onboarding.

Gap 10 — Risco de reconhecimento do padrão pelo agressor familiarizado com stalkerware
Descrição: agressores já familiarizados com a lógica de apps disfarçados (pelo lado ofensivo, via stalkerware) têm maior probabilidade de reconhecer um ícone "estranho" ou "fora do padrão de uso" da vítima. Nenhuma fonte consultada propõe mitigação específica para esse risco de reconhecimento cruzado. Confiança: MÉDIA (inferência de literaturas sobrepostas; sem teste direto documentado).
Ideias já geradas para este gap (Rodada 2): ideia 10 (orientação no onboarding para escolha de disfarce coerente com padrão real de uso), ideia 11 reformulada (sugestão de disfarces alternativos por escolha manual, sem leitura de apps instalados).

Aspectos de camuflagem de segundo nível AINDA NÃO ideados:
- Estratégias de "aging" do disfarce: como fazer o disfarce parecer um app antigo e familiar no aparelho (ex.: data de instalação, padrão de uso, dados de "histórico" plantados no disfarce funcional) versus um app recém-instalado e suspeito
- Estratégias de coerência de comportamento do disfarce na perspectiva do agressor: se o agressor abrir o app de disfarce sem destrave, o que ele vê — apenas a UI funcional, ou algo mais convincente como dados "reais" de uso (uma nota salva de verdade, uma tarefa real, um contato genuíno)?
- Estratégias de reação ao "teste de funcionalidade" pelo agressor: o que acontece se o agressor tentar usar ativamente o disfarce (calcular algo na calculadora, adicionar uma tarefa na lista)? O app registra esse uso? A usuária deve ser alertada discretamente?

Gap 11 — Ausência de gatilho/destrave padronizado e testado para apps de proteção disfarçados
Descrição: nenhuma fonte acadêmica ou de tech safety apresenta comparação estruturada entre tipos de gatilho quanto a usabilidade sob estresse, resistência a destrave acidental e resistência a shoulder surfing. Confiança: MÉDIA (ausência de estudo comparativo direto).
Ideias já geradas para este gap (Rodadas 2 e Informal): código numérico em calculadora, palavra-chave em nota/campo de busca, gesto de destrave, e as variantes de gatilho intrínsecas a cada um dos 11 tipos de disfarce validados (horário-código em despertador, frequência em rádio, título de evento em agenda, etc.).

Variantes de gatilho/destrave AINDA NÃO exploradas:
- Gatilho por sequência de interação física com o hardware: pressionar botão de volume em sequência específica (ex.: volume+ 3x + power) ainda dentro do disfarce ativo — sem digitar nada na tela, imperceptível a shoulder surfing
- Gatilho por biometria oculta: tocar o sensor de digital enquanto o disfarce está aberto, sem que a usuária precise navegar para nenhum campo de PIN — o gesto parece apenas "usar o celular normalmente"
- Gatilho por orientação do dispositivo: rotacionar o celular em sequência específica (ex.: landscape, portrait, landscape) dentro de um app onde isso seria gestual neutro (ex.: jogo simples, leitor de notícias)
- Gatilho por NFC/QR discreto: aproximar o celular de um objeto físico (ex.: etiqueta NFC discreta em um objeto pessoal da usuária — pulseira, carteira) destrava o app sem qualquer interação visível na tela
- Destrave de emergência "reverso": o disfarce exibe uma tela específica de emergência diretamente (sem mostrar a interface real do Amparo) ao receber uma sequência de destrave de emergência diferente da sequência normal — útil quando a usuária não precisa da interface completa, apenas de acionar SOS de dentro do disfarce sem expor o app real

RECOMENDAÇÃO PARA O BRAINSTORM

Bruno deve focar exclusivamente no ESPAÇO NOVO desta rodada — o que ainda não existe no backlog aprovado das Rodadas 2 e Informal. O espaço de ideação tem três frentes ordenadas por lacuna atual:

1. Novos tipos de disfarce além dos 14 já validados (3 originais do RF-CORE-02 + 11 da Rodada Informal): qualquer categoria de app comum que ainda não conste na lista — ex.: app de meditação/bem-estar, jogo simples/casual, leitor de notícias funcional, app de receitas, fitness/saúde — avaliando trade-off entre "banalidade no perfil de uma mulher adulta" e viabilidade de gatilho de destrave coerente com o uso normal daquele tipo de app.

2. Variantes de gatilho/destrave de Gap 11 ainda não geradas: especialmente os gatilhos de hardware (volume buttons), biometria oculta, NFC/objeto físico e destrave reverso de emergência — esses mecanismos foram identificados como lacuna no Gap 11 e nenhum consta no backlog atual.

3. Sub-espaços de UX do Gap 9 ainda sem ideia concreta: fluxo de configuração de privacidade de notificações guiado no onboarding, comportamento do app com assistentes de voz, conteúdo do thumbnail substituto na lista de recentes, e orientação in-app para renomear o ícone na tela inicial.

Fora do escopo por já estar validado: os 14 tipos de disfarce listados acima; os 12 mecanismos de hardening aprovados na Rodada 2; os 5 itens Won't Have já descartados explicitamente.
