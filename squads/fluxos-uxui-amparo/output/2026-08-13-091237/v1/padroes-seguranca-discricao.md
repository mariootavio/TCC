PADRÕES DE SEGURANÇA E DISCRIÇÃO — AMPARO
Base: RF-CORE-02 (modo disfarçado, backlog brainstorm-amparo) + pesquisa Safety
Net Project (research-brief.md desta squad, seção "UX de Segurança e
Discrição") + biblioteca de disfarces validada nas rodadas de brainstorm de
2026-06-28 e 2026-06-29 (confirmadas como fonte complementar no checkpoint
Step 1).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PADRÃO 1: SAÍDA RÁPIDA (QUICK EXIT)

Regra: ícone de saída rápida fixo no canto superior direito, idêntico em
posição e aparência em 100% das telas do app (Início, Documentação, Rede de
Apoio, Chat de Apoio, Mais, e todas as ações secundárias mapeadas por Iara),
exceto quando o modo disfarçado já estiver ativo. Acionamento em 1 toque.
Transição para a tela de destino deve ser INSTANTÂNEA — sem animação, sem
easing, sem Smart Animate (Pietro deve implementar como troca de frame
direta, Step 8).

Racional de risco: se o agressor observar a tela por cima do ombro da
usuária, qualquer atraso perceptível (mesmo 300-500ms de uma transição
animada padrão) cria uma janela de exposição. A posição fixa elimina o tempo
de busca visual pelo controle de saída em um momento de pânico.

Destino da saída rápida: tela neutra idêntica ao disfarce ativo escolhido no
onboarding (Padrão 2) — nunca a tela de login do próprio Amparo, que já
denuncia o uso do app.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PADRÃO 2: MODO DISFARÇADO (RF-CORE-02, OPERACIONALIZADO)

Conceito (já decidido pelo product owner, não reinterpretado aqui): o app se
camufla com ícone e tela inicial falsos escolhidos pela usuária no
onboarding, com troca de aparência sem desinstalar.

**Biblioteca de disfarces disponíveis** (14 tipos validados no backlog —
3 originais + 11 da rodada informal de 2026-06-29 — cada um com gatilho de
destrave próprio, coerente com o uso normal daquele tipo de app):

| Disfarce | Gatilho de destrave |
|---|---|
| Calculadora | Código numérico disfarçado de operação matemática |
| Diário / Bloco de notas | Palavra-chave em nota |
| App de previsão do tempo | Cidade-código |
| Conversor de moedas/unidades | Converter valor numérico específico |
| Lista de tarefas | Criar tarefa com título-chave |
| Lista de compras | Adicionar item com nome-chave |
| Despertador/alarme | Configurar horário específico (tentativa incorreta nunca agenda alarme real) |
| Rádio/sintonizador | Digitar frequência específica |
| Calendário/Agenda | Criar evento com título-chave em data específica |
| Contatos (agenda) | Criar contato com nome-chave |
| Tradutor | Traduzir frase-chave (não persiste no histórico) |
| Mapas/Navegação | Buscar endereço-chave (histórico de busca limpo) |
| Cronômetro/Timer | Configurar duração específica (tentativa incorreta nunca agenda timer real) |

Racional de risco (escolha de disfarce): agressores já familiarizados com a
lógica de apps disfarçados (Freed et al., CHI 2018; Refuge UK 2019 — 72% das
mulheres atendidas relataram abuso tecnológico) têm maior chance de
reconhecer um ícone "fora do padrão de uso" da vítima — por isso o
onboarding deve orientar a usuária a escolher um disfarce coerente com seu
padrão real de uso do celular (ex.: se ela já usa calculadora com frequência,
esse disfarce é mais seguro que um app raramente usado).

**Mecanismos de hardening obrigatórios** (validados no backlog, Rodada 2):

1. Biblioteca de disfarces totalmente funcionais — nunca apenas fachada
   visual; cada disfarce realiza sua função real (a calculadora calcula de
   verdade), para resistir a um teste de funcionalidade pelo agressor.
2. Falha silenciosa no destrave — tentativa incorreta de código/gesto nunca
   exibe mensagem de erro visível.
3. Gesto de destrave como alternativa sem digitação, para reduzir shoulder
   surfing.
4. Criptografia real dos dados por trás do disfarce, independente da UI
   visual (Ruffin et al., WPES 2022 — maioria dos vault apps analisados NÃO
   criptografa; Amparo não repete essa falha).
5. Orientação no onboarding para reduzir risco de reconhecimento do padrão
   (ver racional acima).
6. Saída de emergência generalizada — a saída rápida (Padrão 1) funciona a
   partir de qualquer disfarce escolhido, sem exceção.

Racional de risco (hardening): 64,3% dos feminicídios ocorrem dentro da
própria residência da vítima (research-brief.md, squad tcc-documentacao) —
o agressor tem acesso físico prolongado e repetido ao celular, tornando a
"inspeção manual/forense doméstica" o vetor de risco mais crítico do domínio
Amparo, não um cenário teórico.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PADRÃO 3: NOTIFICAÇÕES NEUTRAS

Regra: nenhuma notificação push ou de lock screen exibe conteúdo sensível em
texto visível — usar sempre um texto genérico fixo (ex.: "Você tem uma
atualização" em vez de "Sua guardiã Marina confirmou o recebimento do seu
alerta"). Aplica-se sem exceção a:
- RF-CORE-03 (chat com profissional de apoio)
- RF-CORE-05 (rede de guardiões) e à ação secundária "Confirmar recebimento
  de alerta" (arquitetura-informacao.md, Iara)
- Qualquer notificação gerada pela Camada Transversal RF-CORE-06
  (classificação de risco MÉDIO/ALTO) — o gatilho pode vir do modelo de ML,
  mas o TEXTO da notificação segue esta regra sem exceção
- Ideia 1 "Check-in ativo" e Ideia 2 "Detecção de padrão em segundo plano"
  (ambas ação secundária, Iara) — qualquer alerta escalado por ausência de
  resposta ou sinal indireto é neutro

Configuração de privacidade guiada: no onboarding, o app orienta a usuária a
configurar o preview de notificações do sistema operacional para "Nunca" ou
"Somente quando desbloqueado" (mitigação documentada pela EFF, 2026) — o
próprio Amparo não depende dessa configuração do SO para sua proteção
(o conteúdo já é neutro por padrão), mas reforça a orientação como camada
extra.

Racional de risco: o conteúdo de uma notificação fica visível mesmo com a
tela bloqueada, em qualquer celular que o agressor consiga visualizar de
relance — neutralidade de conteúdo é a única defesa nesse cenário, já que a
usuária não controla quando o agressor vê a tela de bloqueio.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PADRÃO 4: MINIMIZAÇÃO DE RASTRO NO SISTEMA

Regra: quando o app é minimizado ou aparece no app switcher do sistema
operacional, a captura de tela exibida deve mostrar o ícone e a interface do
disfarce configurado (Padrão 2), nunca a tela real do Amparo em uso — mesmo
que a usuária estivesse, no momento de minimizar, dentro de um fluxo sensível
(ex.: registrando uma ocorrência em Documentação, ou vendo o resultado de
RF-CORE-06 em Início).

Implementação esperada (Pietro, Step 8): qualquer frame marcado como
"sensível" na hierarquia de Telma (Step 7) tem, no protótipo, o comportamento
de "tela de fundo" equivalente à interface disfarçada ao perder o foco.

Vetores adicionais cobertos por este padrão (Gap 9 do research-brief da
squad brainstorm-amparo):
- Nome do app na loja/ficha de instalação desvinculado da marca "Amparo"
  (condicional à política da Apple — pendência sinalizada para decisão
  humana, não resolvida aqui).
- Orientação in-app, no onboarding, para a usuária renomear manualmente o
  ícone na tela inicial do celular (disponível nativamente em iOS 14+ e
  Android) para um nome neutro coerente com o disfarce escolhido.

Racional de risco: o histórico de apps recentes é um dos vetores de
descoberta mais comuns documentados pela literatura de tecnologia e segurança
(Malwarebytes Labs; Ruffin et al., WPES 2022) — um agressor que abre o app
switcher do celular da vítima não deve ver nenhuma evidência visual de que o
Amparo estava em uso real.

Esta regra se aplica de forma transversal a qualquer fluxo desenhado por
Joana (Step 5), não apenas ao modo disfarçado isoladamente — incluindo os
fluxos afetados pela Camada Transversal Modo Offline (Ideia 7,
arquitetura-informacao.md).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PENDÊNCIAS

1. Variantes de gatilho/destrave por hardware (sequência de botão de volume,
   biometria oculta, NFC/objeto físico, destrave de emergência "reverso")
   foram identificadas como lacuna de mercado (Gap 11) mas ainda não têm
   prioridade RICE definida no backlog — não incorporadas como regra
   obrigatória nesta rodada, apenas registradas para eventual priorização
   futura pela squad `brainstorm-amparo`.
2. Nome/ficha da loja de apps desvinculada da marca "Amparo" depende de
   validação da política da Apple App Store — decisão humana pendente.
