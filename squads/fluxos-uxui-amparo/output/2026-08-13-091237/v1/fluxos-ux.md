FLUXOS DE UX — AMPARO
Fontes: `arquitetura-informacao.md` (Iara, Step 3) + `padroes-seguranca-discricao.md`
(Daniela, Step 4) + backlog `brainstorm-amparo` + `company.md` (RF-CORE-06).
Quatro fluxos críticos mapeados (emergência, documentação, modo disfarçado,
rede de apoio) — todos com caminho feliz e ao menos um caminho de erro.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FLUXO 1: ACIONAMENTO DE EMERGÊNCIA (BOTÃO DO PÂNICO/SOS)
Ancoragem: RF-CORE-01 (Ação Global 1, arquitetura-informacao.md).
Classificação: Fluxo crítico — exige caminho de erro mapeado.

CAMINHO FELIZ

1. Usuária aciona o Botão SOS (ação global, componente Figma "Botão SOS" de
   Caio Componentes) — disponível com 1 toque mesmo com a tela bloqueada,
   conforme RF-CORE-01.
   Heurística de Nielsen 1 — Visibilidade do status do sistema: o app exibe
   feedback visual e/ou tátil imediato confirmando o acionamento, para que a
   usuária saiba que o alerta foi recebido sem precisar esperar confirmação
   de terceiros.
2. App envia localização em tempo real para a rede de guardiões (RF-CORE-05)
   — a notificação enviada aos guardiões é neutra, conforme Padrão 3 de
   Daniela Discrição.
3. Guardiões confirmam recebimento (RF-CORE-05, ação secundária "Confirmar
   recebimento de alerta") — confirmação aparece na tela de status da
   usuária.
   Heurística de Nielsen 1 — reforça visibilidade de status em tempo real
   durante todo o acionamento.

CAMINHO DE ERRO: SEM CONEXÃO DE DADOS NO MOMENTO DO ACIONAMENTO

1. App detecta ausência de conexão de dados ao tentar enviar localização.
2. Fallback: acionamento via SMS/USSD com dados mínimos (Ideia 8 do backlog
   priorizado, "SOS sem conexão de dados, com acionamento sem rastro
   visível") — SMS é auto-excluído da conversa nativa após confirmação de
   entrega; em aparelhos onde a exclusão não for tecnicamente possível, usa
   canal USSD/dados mínimos que não grava mensagem na interface padrão.
   Heurística de Nielsen 9 — Ajudar o usuário a reconhecer, diagnosticar e
   corrigir erros: o app informa silenciosamente (sem alarme visual exposto)
   que o envio ocorreu por canal alternativo.
3. Ponto de verificação de segurança: a saída rápida (Padrão 1 de Daniela)
   permanece acessível durante toda a tentativa de envio, caso a usuária
   precise interromper a ação abruptamente.

CAMINHO DE ERRO: INTERRUPÇÃO ABRUPTA DURANTE O ACIONAMENTO

1. Usuária aciona a saída rápida no meio do fluxo de emergência.
2. Transição instantânea para a tela do disfarce ativo (Padrão 1 de Daniela)
   — o acionamento de emergência já disparado continua em segundo plano sem
   exigir retorno da usuária à tela do Amparo.

VARIAÇÃO POR NÍVEL DE RISCO (RF-CORE-06, camada transversal sinalizada por
Iara na tela "Início")

- BAIXO / MÉDIO: nenhuma alteração no acionamento em si — o SOS manual
  funciona de forma idêntica em qualquer nível de risco. O nível MÉDIO se
  manifesta apenas na tela "Início" (alerta discreto pré-configurado), não
  neste fluxo.
- ALTO: passo 2 do Caminho Feliz prioriza o envio à rede de guardiões (menor
  timeout de retry) e dispara proteção reforçada das evidências mais
  recentes (ver Fluxo 2), conforme a ação de sistema "mecanismos de
  emergência priorizados, acesso rápido a recursos de ajuda e proteção
  reforçada das evidências" documentada em company.md. O acionamento em si
  NUNCA é bloqueado, atrasado ou condicionado pelo nível de risco — a
  classificação é mecanismo de apoio, não portão de acesso ao SOS.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FLUXO 2: REGISTRO DE OCORRÊNCIA COM EVIDÊNCIAS
Ancoragem: RF-CORE-04 (Navegação Principal 2, "Documentação") + Ideia 3
"Backup criptografado automático em nuvem" (Must have) + Ideia 4 "Indicador
de integridade da prova" (Should have).
Classificação: Fluxo crítico — exige caminho de erro mapeado.

CAMINHO FELIZ

1. Usuária acessa "Documentação" na navegação principal e inicia novo
   registro.
   Heurística de Nielsen 4 — Consistência e padrões: o destino de
   Documentação é sempre o mesmo item da bottom nav, nunca reposicionado.
2. Usuária anexa evidência (texto/foto/áudio/vídeo) — ação secundária
   contextual dentro do fluxo, conforme arquitetura de Iara.
   Heurística de Nielsen 7 — Flexibilidade e eficiência de uso: múltiplos
   formatos de evidência no mesmo fluxo, sem exigir telas separadas por tipo
   de mídia.
3. Arquivo é criptografado localmente e replicado automaticamente para
   backup em nuvem, ainda criptografado (Ideia 3) — a cópia local mais
   antiga só é removida após confirmação de sincronização, para que a
   apreensão física do celular pelo agressor não elimine a prova.
4. Evidência recebe hash criptográfico e selo de tempo verificável (Ideia
   4), exibidos à usuária e exportáveis junto com a prova.
   Heurística de Nielsen 1 — Visibilidade do status do sistema: indicador
   simples de "Backup concluído" e "Prova verificada" na tela de detalhe.

CAMINHO DE ERRO: FALHA NO BACKUP EM NUVEM

1. App detecta falha de envio do backup (sem conexão ou erro de servidor).
2. Evidência permanece criptografada localmente, com indicador de "Backup
   pendente" — nunca um alerta visual alarmante, mantendo o tom acolhedor do
   projeto (padroes-seguranca-discricao.md, Padrão 3, mesmo espírito de
   neutralidade).
   Heurística de Nielsen 1 — a usuária sabe que o backup não foi concluído,
   sem ser exposta a linguagem técnica ou alarmista.
3. App tenta novamente o backup automaticamente quando a conexão for
   restabelecida (compatível com a Camada Transversal "Modo Offline",
   Ideia 7), sem exigir ação manual da usuária.
4. Ponto de verificação de segurança: a saída rápida permanece acessível em
   toda a tela de Documentação, inclusive durante o upload.

VARIAÇÃO POR NÍVEL DE RISCO (RF-CORE-06)

- BAIXO / MÉDIO: comportamento idêntico ao Caminho Feliz — ciclo de backup
  padrão.
- ALTO: passo 3 do Caminho Feliz é priorizado — backup imediato, sem esperar
  o ciclo padrão de sincronização — conforme a ação de sistema "proteção
  reforçada das evidências" de company.md.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FLUXO 3: ATIVAÇÃO DO MODO DISFARÇADO E SAÍDA RÁPIDA
Ancoragem: RF-CORE-02 (Ação Global 2, arquitetura-informacao.md) +
padroes-seguranca-discricao.md (Padrões 1, 2 e 4 de Daniela Discrição).
Classificação: Fluxo crítico — exige caminho de erro mapeado.

CAMINHO FELIZ — CONFIGURAÇÃO NO ONBOARDING

1. Durante o onboarding, a usuária escolhe um disfarce da biblioteca de 14
   tipos validados (Padrão 2 de Daniela) — o app recomenda um disfarce
   coerente com seu padrão real de uso do celular, sem ler a lista de apps
   instalados (mecanismo de hardening 5).
   Heurística de Nielsen 6 — Reconhecimento em vez de memorização: a lista
   de disfarces é apresentada com ícones e nomes familiares, nunca exigindo
   que a usuária memorize um código antes de configurar.
2. Usuária define o gatilho de destrave específico do disfarce escolhido
   (ex.: código numérico na calculadora) — o app orienta que o gatilho deve
   ser simples/memorável sob estresse, evitando PINs longos.
3. App confirma a configuração silenciosamente (sem alarde visual) e ativa
   o disfarce imediatamente.

CAMINHO FELIZ — USO DIÁRIO (SAÍDA RÁPIDA)

1. Usuária toca o ícone de saída rápida, fixo no canto superior direito em
   qualquer tela (Padrão 1 de Daniela).
2. Transição INSTANTÂNEA (sem animação) para a interface do disfarce
   ativo.
   Heurística de Nielsen 1 — a mudança é imediata o suficiente para não
   haver percepção de "troca de tela" por um observador.

CAMINHO DE ERRO: TENTATIVA DE DESTRAVE INCORRETA (PELO AGRESSOR)

1. Uma pessoa não autorizada (ex.: o agressor testando o disfarce) insere um
   código/gesto incorreto no disfarce ativo.
2. Falha silenciosa — nenhuma mensagem de erro visível é exibida (mecanismo
   de hardening 2); o disfarce continua funcional normalmente (ex.: a
   calculadora apenas mostra o resultado do cálculo digitado).
   Heurística de Nielsen 9 (aplicada de forma invertida por design de
   segurança): o app deliberadamente NÃO ajuda a "corrigir o erro" de quem
   está tentando destravar sem autorização — este é o único ponto do
   sistema onde a heurística de recuperação de erro é intencionalmente
   suspensa, por exigência de segurança documentada por Daniela Discrição.
3. Nenhum log visível ou alerta é gerado no dispositivo do agressor; a
   tentativa não é sinalizada de volta para ele de forma alguma.

CAMINHO DE ERRO: MINIMIZAÇÃO/APP SWITCHER DURANTE FLUXO SENSÍVEL

1. Usuária minimiza o app (ou é interrompida) enquanto está em um fluxo
   sensível (ex.: Documentação, Fluxo 2).
2. Conforme Padrão 4 de Daniela: a captura exibida no app switcher mostra o
   disfarce ativo, nunca o conteúdo real do fluxo em andamento.

VARIAÇÃO POR NÍVEL DE RISCO (RF-CORE-06)

- Não aplicável. Iara não sinalizou este fluxo como afetado pela camada
  transversal RF-CORE-06 — modo disfarçado e saída rápida são padrões de
  segurança universais, com o mesmo comportamento em qualquer nível de risco
  (variar esse comportamento por risco contrariaria o Padrão 1 de Daniela,
  "posição fixa e estável").

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FLUXO 4: REDE DE GUARDIÕES — CADASTRO E CONFIRMAÇÃO DE ALERTA
Ancoragem: RF-CORE-05 (Navegação Principal 3, "Rede de Apoio") + Ideia 6
"Perfis de dependentes" (Should have) + Ideia 5 "Encaminhamento institucional
automático pós-confirmação" (Should have).
Classificação: Fluxo crítico — exige caminho de erro mapeado.

CAMINHO FELIZ — CADASTRO DE GUARDIÃO

1. Usuária acessa "Rede de Apoio" na navegação principal e cadastra uma
   pessoa de confiança (nome, contato) — comunicação bidirecional segura
   estabelecida conforme RF-CORE-05.
   Heurística de Nielsen 6 — campos de cadastro simples, sem jargão técnico
   (tom de voz do projeto).
2. Usuária pode também cadastrar dependentes sob sua guarda (Ideia 6) como
   perfis protegidos dentro da mesma tela, recebendo orientações específicas
   de segurança para eles — alinhado à Lei 15.384/2026 (violência vicária).

CAMINHO FELIZ — CONFIRMAÇÃO DE ALERTA

1. Um guardião recebe um alerta de emergência (originado no Fluxo 1, passo
   2) e confirma o recebimento — a notificação recebida pelo guardião já é
   neutra (Padrão 3 de Daniela).
2. App oferece à usuária, com 1 toque, encaminhamento institucional para o
   canal mais próximo (Delegacia da Mulher, Ligue 180, CRAS) com dados
   básicos da ocorrência pré-preenchidos (Ideia 5).
   Heurística de Nielsen 7 — Flexibilidade e eficiência de uso: o
   encaminhamento é oferecido, nunca obrigatório — a usuária decide se
   aciona o canal institucional.

CAMINHO DE ERRO: GUARDIÃO NÃO RESPONDE (CHECK-IN SEM RESPOSTA)

1. Se a usuária tiver ativado a Ideia 1 (Verificação de bem-estar periódica,
   configurável em Configurações de Segurança) e não responder dentro da
   janela curta configurada, o app escala automaticamente um alerta discreto
   para a rede de guardiões, sem exigir acionamento manual do Botão SOS.
   Heurística de Nielsen 1 — mesmo em escalonamento automático, o status é
   sempre visível para a usuária quando ela reabrir o app.
2. Se NENHUM guardião confirmar recebimento dentro de um intervalo razoável,
   o app mantém o alerta ativo e continua tentando notificar — nunca marca
   silenciosamente como "resolvido" sem confirmação humana.
3. Ponto de verificação de segurança: a saída rápida permanece acessível
   durante toda a espera por confirmação.

VARIAÇÃO POR NÍVEL DE RISCO (RF-CORE-06)

- BAIXO: nenhuma alteração — cadastro e confirmação seguem o Caminho Feliz.
- MÉDIO: ao confirmar um alerta, o guardião recebe também um recurso de
  apoio contextual (ex.: link para a Biblioteca de Direitos, Navegação
  Principal item "Mais") — conforme a ação de sistema "alerta discreto
  pré-configurado e apresentação de recursos de apoio" de company.md.
- ALTO: o encaminhamento institucional (passo 2 do Caminho Feliz de
  Confirmação) é priorizado visualmente e sugerido proativamente à usuária
  logo após a confirmação do guardião, em vez de aparecer apenas como opção
  secundária — conforme "acesso rápido a recursos de ajuda" de company.md.
  O encaminhamento continua sendo oferecido, nunca obrigatório.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FLUXO 5: PIPELINE DE CLASSIFICAÇÃO DE RISCO (RF-CORE-06)
Ancoragem: RF-CORE-06 (`_opensquad/_memory/company.md`, seção "Classificação
de Risco (IA/ML)"). Adicionado nesta rodada por decisão do usuário no
checkpoint Step 6 (2026-08-13) — documenta o pipeline interno da camada
transversal, complementando (não substituindo) as variações por nível de
risco já descritas nos Fluxos 1, 2 e 4.
Classificação: Fluxo crítico — a classificação alimenta a priorização de
emergência (Fluxo 1) e de evidências (Fluxo 2); uma falha aqui não pode
degradar a segurança da usuária.

CAMINHO FELIZ

1. App (React Native) registra eventos relevantes durante o uso normal:
   agressões verbais, agressões físicas, ameaças, emergências acionadas
   (Fluxo 1) e frequência das ocorrências (Fluxo 2) — nenhum evento novo é
   coletado além do que já é gerado pelas funcionalidades RF-CORE existentes.
   Heurística de Nielsen 1 — Visibilidade do status do sistema: a coleta é
   silenciosa (não é um formulário que a usuária precisa preencher), mas o
   resultado da classificação é sempre visível de alguma forma na tela
   "Início" (BAIXO/MÉDIO/ALTO), nunca uma decisão invisível.
2. Backend (NestJS) envia os dados agregados para a API de IA (Python).
3. API de IA aplica o modelo Decision Tree (Scikit-learn, treinado com dados
   sintéticos) e retorna uma classe de risco: BAIXO, MÉDIO ou ALTO.
4. Backend propaga o nível de risco para o app, que ajusta o comportamento
   das telas afetadas (Fluxos 1, 2 e 4) conforme já documentado.
   Heurística de Nielsen 1 — a transição de nível de risco na tela "Início"
   é sempre comunicada de forma discreta e não alarmista (mesmo tom
   acolhedor do restante do app), nunca como um alerta abrupto.

CAMINHO DE ERRO: API DE IA INDISPONÍVEL OU SEM RESPOSTA

1. Backend detecta timeout ou erro ao chamar a API de IA.
2. App mantém o último nível de risco conhecido (cache local) em vez de
   reverter silenciosamente para BAIXO — reverter para BAIXO sem base real
   poderia reduzir indevidamente a priorização de emergência de uma usuária
   em risco ALTO.
   Heurística de Nielsen 9 — o app não expõe erro técnico à usuária; a
   ausência de atualização é tratada internamente, sem linguagem alarmista.
3. Ponto de verificação de segurança: independentemente do estado da API de
   IA, o acionamento manual do Botão SOS (Fluxo 1) nunca é bloqueado,
   atrasado ou condicionado — esta é a mesma regra já estabelecida no
   Fluxo 1, reforçada aqui na origem do dado de risco.

NOTA DE ESCOPO: a classificação é mecanismo de apoio, não diagnóstico
determinístico (company.md) — este fluxo nunca aciona uma ação de emergência
sozinho; ele apenas prioriza/adapta a apresentação de funcionalidades que a
usuária já controla.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FLUXO 6: DELEGACIAS PRÓXIMAS
Ancoragem: NOVO — trazido de "Trabalhos Futuros" (`AMPARO_TCC_Apresentacao.pdf`)
para o escopo atual por decisão explícita do usuário no checkpoint Step 6
(2026-08-13). Não é um item do backlog RICE da squad `brainstorm-amparo` —
pendência registrada em `arquitetura-informacao.md` para rastreabilidade
futura. Navegação: item "Delegacias Próximas" dentro de "Mais".
Classificação: Fluxo padrão (não crítico pela definição desta squad —
emergência, documentação, modo disfarçado, rede de apoio — mas com caminho
de erro mapeado por exigência explícita do usuário).

CAMINHO FELIZ

1. Usuária acessa "Delegacias Próximas" a partir de "Mais".
2. App solicita permissão de localização (se ainda não concedida), com
   explicação clara do motivo do pedido.
   Heurística de Nielsen 1 — Visibilidade do status do sistema: o app
   explica por que precisa da localização antes de pedir a permissão do SO.
3. App exibe lista (e/ou mapa) das delegacias mais próximas, com distância
   aproximada, endereço e telefone.
   Heurística de Nielsen 6 — Reconhecimento em vez de memorização: lista
   ordenada por proximidade, sem exigir que a usuária saiba o nome da
   delegacia previamente.
4. Usuária pode tocar em uma delegacia para ver rota (abre app de mapas
   externo) ou ligar diretamente.

CAMINHO DE ERRO: PERMISSÃO DE LOCALIZAÇÃO NEGADA

1. Usuária nega a permissão de localização.
2. App oferece busca manual por cidade/CEP como alternativa, sem bloquear o
   acesso à funcionalidade.
   Heurística de Nielsen 9 — a ausência de permissão não gera erro
   bloqueante, apenas um caminho alternativo de busca.

CAMINHO DE ERRO: NENHUMA DELEGACIA ENCONTRADA NA REGIÃO

1. App não encontra delegacias cadastradas próximas à localização/busca da
   usuária.
2. App exibe, no lugar de uma lista vazia, o número do Ligue 180 e o
   telefone de emergência 190 como alternativa imediata — nunca uma tela
   vazia sem próximo passo.

PONTO DE VERIFICAÇÃO DE SEGURANÇA: a saída rápida permanece acessível em
toda a tela, e a busca por localização não fica registrada em histórico de
mapas do sistema operacional de forma que denuncie o uso do Amparo (mesma
lógica de minimização de rastro do Padrão 4 de Daniela, aplicada aqui à
navegação externa).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FLUXOS NÃO MAPEADOS NESTA RODADA (fora do escopo dos fluxos críticos/padrão já cobertos)

Chat de Apoio (RF-CORE-03), Biblioteca de Direitos (Ideia 11), Assistente de
Triagem (Ideia 9) e Relatos Anônimos (Ideia 15) são navegáveis conforme
arquitetura-informacao.md, mas não foram classificados como fluxo crítico
por Iara/Joana nesta rodada (não envolvem emergência, documentação sensível
ou comunicação com rede de apoio direta). Podem ser detalhados em uma rodada
futura desta squad, se priorizado pelo usuário.
