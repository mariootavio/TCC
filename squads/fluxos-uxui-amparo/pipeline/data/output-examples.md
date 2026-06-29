# Output Examples — Fluxos & UI/Protótipo Amparo

Sete exemplos completos de outputs finais da squad, um por agente. Servem
como referência de qualidade e profundidade — não como templates rígidos a
copiar literalmente.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Exemplo 1: Design System Reconstruído no Figma (Caio Componentes)

```
DESIGN SYSTEM RECONSTRUÍDO NO FIGMA — AMPARO
Projeto Claude Design de origem: "Amparo — Identidade Visual" (squad
marca-design-amparo, projeto confirmado no checkpoint Step 1)
Arquivo Figma criado: "Amparo — Design System" (link: figma.com/file/XXXX)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

TOKENS PRIMITIVOS (Figma Variables — coleção "primitives")

| Token | Valor | Fonte |
|---|---|---|
| color/violet/600 | #6D28D9 | design-system.md, seção "Paleta — Cor Primária" |
| color/violet/700 | #5B21B6 | design-system.md, seção "Paleta — Cor Primária" |
| color/neutral/50 | #FAFAFA | design-system.md, seção "Paleta — Neutros" |
| font/family/base | "Inter" | identidade-visual.md, seção "Tipografia" |
| space/4 | 4px | design-system.md, seção "Espaçamento — Escala Base" |

TOKENS SEMÂNTICOS (Figma Variables — coleção "semantic", modo "light")

| Token | Aponta para | Fonte |
|---|---|---|
| color/action/primary | color/violet/600 | design-system.md, seção "Tokens Semânticos — Ação" |
| color/text/on-primary | color/neutral/50 | design-system.md, seção "Tokens Semânticos — Texto sobre Cor" |

VERIFICAÇÃO DE CONTRASTE WCAG AA

- color/text/on-primary (#FAFAFA) sobre color/action/primary (#6D28D9):
  contraste calculado 7.1:1 — ATENDE (mínimo 4.5:1 texto normal). Conforme
  documentado em design-system.md, seção "Acessibilidade".

COMPONENTES RECONSTRUÍDOS (hierarquia atômica)

- Átomo "Botão" — Variant Properties: Tipo (Primário/Secundário/Texto),
  Estado (Padrão/Pressionado/Desabilitado), Tamanho (Grande/Padrão).
  Fonte: design-system.md, seção "Componentes — Botões".
- Átomo "Campo de Texto" — Variant Properties: Estado (Padrão/Foco/Erro),
  Com ícone (Sim/Não). Fonte: design-system.md, seção "Componentes — Inputs".

PENDÊNCIAS (informação ausente na fonte — decisão do usuário necessária)

1. Cor do estado "Erro" do Campo de Texto não está documentada em
   design-system.md nem em identidade-visual.md. Nenhum valor foi inferido —
   aguardando definição da squad marca-design-amparo ou decisão do usuário.
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Exemplo 2: Arquitetura de Informação (Iara Informação)

```
ARQUITETURA DE INFORMAÇÃO — AMPARO
Fonte: backlog ideias-brainstorm.md (run 2026-06-27-145210, v1) +
research-brief.md (RF-CORE-01 a RF-CORE-05), squad brainstorm-amparo.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

AÇÕES GLOBAIS (acesso instantâneo, de qualquer tela)

1. Botão do pânico/SOS — RF-CORE-01. Justificativa: pesquisa de UX de
   segurança (Safety Net Project) exige acionamento de emergência em no
   máximo 1-2 toques, de qualquer ponto do app — incompatível com
   navegação hierárquica comum.
2. Modo disfarçado / saída rápida — RF-CORE-02. Justificativa: mesma
   exigência de acesso instantâneo; operacionalização detalhada cabe a
   Daniela Discrição no Step 4.

NAVEGAÇÃO PRINCIPAL (bottom nav)

1. Início — painel resumo (status da rede de guardiões, acesso rápido a
   chat e documentação). Fonte: consolidação das frentes RF-CORE-03,
   RF-CORE-04, RF-CORE-05.
2. Documentação — RF-CORE-04 (registro de ocorrências com evidências).
3. Rede de Apoio — RF-CORE-05 (rede de guardiões) + Ideia 6 priorizada
   "Perfis de dependentes na rede de apoio" (backlog brainstorm-amparo,
   ranking RICE).
4. Chat de Apoio — RF-CORE-03 (chat com profissional de apoio).
5. Mais — agrupa Ideia 11 "Biblioteca de direitos e legislação
   simplificada" e Ideia 10 "Avaliação de risco estruturada adaptada ao
   Brasil" (ambas do backlog priorizado), evitando exceder 5 itens na
   bottom nav.

AÇÕES SECUNDÁRIAS/CONTEXTUAIS

1. Anexar evidência (foto/áudio/vídeo) — contextual dentro do fluxo de
   Documentação (RF-CORE-04), nunca um destino de navegação independente.
2. Confirmar recebimento de alerta — contextual dentro do fluxo de Rede de
   Apoio, acionado a partir de uma notificação (RF-CORE-05).

LACUNAS IDENTIFICADAS (sem funcionalidade correspondente no backlog)

1. Onboarding inicial pós-instalação: o backlog prioriza "Onboarding via
   QR code em pontos de acolhimento" (Ideia 17) como canal de aquisição,
   mas não há funcionalidade documentada cobrindo o onboarding padrão
   (sem QR code) para quem instala o app por conta própria. Sinalizado
   para decisão do usuário — não preenchido nesta arquitetura.
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Exemplo 3: Padrões de Segurança e Discrição (Daniela Discrição)

```
PADRÕES DE SEGURANÇA E DISCRIÇÃO — AMPARO
Base: RF-CORE-02 (modo disfarçado, backlog brainstorm-amparo) + pesquisa
Safety Net Project (research-brief.md desta squad, seção UX de Segurança
e Discrição).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PADRÃO 1: SAÍDA RÁPIDA (QUICK EXIT)

Regra: ícone de saída rápida fixo no canto superior direito, idêntico em
posição e aparência em 100% das telas do app, exceto quando o modo
disfarçado já estiver ativo. Acionamento em 1 toque. Transição para a
tela de destino deve ser INSTANTÂNEA — sem animação, sem easing, sem
Smart Animate (Pietro deve implementar como troca de frame direta, não
como transição animada).

Racional de risco: se o agressor observar a tela por cima do ombro da
usuária, qualquer atraso perceptível (mesmo 300-500ms de uma transição
animada padrão) cria uma janela de exposição. A posição fixa elimina o
tempo de busca visual pelo controle de saída em um momento de pânico.

Destino da saída rápida: tela neutra configurável pela usuária no
onboarding (ex.: tela de busca genérica, app de previsão do tempo) —
nunca a tela de login do próprio Amparo, que já denuncia o uso do app.

PADRÃO 2: NOTIFICAÇÕES NEUTRAS

Regra: nenhuma notificação push ou de lock screen exibe conteúdo
sensível em texto visível — usar sempre um texto genérico fixo (ex.:
"Você tem uma atualização" em vez de "Sua guardiã Marina confirmou o
recebimento do seu alerta"). Aplica-se a RF-CORE-03 (chat), RF-CORE-05
(rede de guardiões) e qualquer alerta de risco.

Racional de risco: o conteúdo de uma notificação fica visível mesmo com
a tela bloqueada, em qualquer celular que o agressor consiga visualizar
de relance — neutralidade de conteúdo é a única defesa nesse cenário,
já que a usuária não controla quando o agressor vê a tela de bloqueio.
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Exemplo 4: Fluxo de UX (Joana Jornada)

```
FLUXO: ACIONAMENTO DE EMERGÊNCIA (BOTÃO DO PÂNICO/SOS)
Ancoragem: RF-CORE-01 (backlog brainstorm-amparo, research-brief.md).
Classificação: Fluxo crítico — exige caminho de erro mapeado.

CAMINHO FELIZ

1. Usuária aciona o botão de emergência (ação global, definida por Iara
   em arquitetura-informacao.md) — disponível com 1 toque mesmo com tela
   bloqueada, conforme RF-CORE-01.
   Heurística de Nielsen 1 — Visibilidade do status do sistema: o app
   exibe feedback visual e/ou tátil imediato confirmando o acionamento,
   para que a usuária saiba que o alerta foi recebido sem precisar
   esperar confirmação de terceiros.
2. App envia localização em tempo real para a rede de guardiões
   (RF-CORE-05) — notificação enviada é neutra, conforme padrão 2 de
   Daniela Discrição (padroes-seguranca-discricao.md).
3. Guardiões confirmam recebimento (RF-CORE-05) — confirmação aparece na
   tela de status da usuária.

CAMINHO DE ERRO: SEM CONEXÃO DE DADOS NO MOMENTO DO ACIONAMENTO

1. App detecta ausência de conexão de dados ao tentar enviar localização.
2. Fallback: acionamento via SMS/USSD com dados mínimos (ancorado na
   Ideia 8 do backlog priorizado, "SOS sem conexão de dados, com
   acionamento sem rastro visível", RICE 3,75) — SMS é auto-excluído da
   conversa nativa após confirmação de entrega.
   Heurística de Nielsen 9 — Ajudar o usuário a reconhecer, diagnosticar
   e corrigir erros: o app informa silenciosamente (sem alarme visual
   exposto) que o envio ocorreu por canal alternativo.
3. Ponto de verificação de segurança: a saída rápida (padrão 1 de
   Daniela) permanece acessível durante toda a tentativa de envio, caso
   a usuária precise interromper a ação abruptamente.
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Exemplo 5: Telas de Alta Fidelidade (Telma Tela)

```
TELAS DE ALTA FIDELIDADE — AMPARO
Arquivo Figma: "Amparo — Design System" (mesmo arquivo de Caio, novas
páginas adicionadas por fluxo).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PÁGINA: "Fluxo — Acionamento de Emergência"
Fonte: fluxos-ux.md, fluxo "Acionamento de Emergência (Botão do
Pânico/SOS)", RF-CORE-01.

Frame "Emergência / Acionamento — Padrão": tela inicial com o botão de
emergência (ação global, componente "Botão Primário — Tamanho Grande" do
design system de Caio) sempre visível. Corresponde ao passo 1 do Caminho
Feliz.

Frame "Emergência / Confirmação — Padrão": exibe feedback visual
imediato de acionamento confirmado, usando o componente "Indicador de
Status — Sucesso" do design system. Corresponde ao passo 1-2 do Caminho
Feliz (Heurística 1, visibilidade do status do sistema).

Frame "Emergência / Confirmação — Erro Sem Conexão": variação do frame
anterior usando o componente "Indicador de Status — Atenção" (mesma
posição e estrutura do frame "Padrão", apenas o estado do indicador
muda) — nomenclatura consistente preparada para Smart Animate por
Pietro. Corresponde ao Caminho de Erro "Sem Conexão de Dados" de
fluxos-ux.md.

Posição da saída rápida: ícone fixo no canto superior direito, idêntico
em todos os três frames desta página, conforme padrão 1 de Daniela
Discrição (padroes-seguranca-discricao.md).
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Exemplo 6: Protótipo Navegável (Pietro Prototipagem)

```
PROTÓTIPO NAVEGÁVEL — AMPARO
Arquivo Figma: "Amparo — Design System" (mesmo arquivo de Caio e Telma).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FLUXO: ACIONAMENTO DE EMERGÊNCIA (RF-CORE-01)

Conexões criadas:
1. "Emergência / Acionamento — Padrão" → "Emergência / Confirmação —
   Padrão": Smart Animate (300ms, ease-out) — nomenclatura de camadas
   idêntica entre os dois frames, conforme preparado por Telma.
2. "Emergência / Confirmação — Padrão" → "Emergência / Confirmação —
   Erro Sem Conexão": Smart Animate, acionado pela condição de falha de
   rede simulada no protótipo.
3. Ícone de saída rápida (presente nos 3 frames desta página) →
   "Disfarce / Tela Neutra": TRANSIÇÃO INSTANTÂNEA (sem Smart Animate,
   sem easing), conforme padrão 1 de Daniela Discrição — regra aplicada
   sem exceção.

TABELA DE VERIFICAÇÃO DE NAVEGAÇÃO

| Fluxo | Caminho Feliz | Caminho(s) de Erro | Saída Rápida testada | Status |
|---|---|---|---|---|
| Acionamento de Emergência | OK — 2 cliques até confirmação | OK — fallback sem conexão testado | OK — testada nos 3 frames | OK |
| Registro de Ocorrência com Evidências | OK | OK — falha de backup testada | OK — testada em 2 frames | OK |

Nenhuma tela morta ou link quebrado identificado nesta rodada de teste.
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Exemplo 7: Veredito de Revisão de Design (Wagner WCAG)

```
==============================
 VEREDITO DA REVISÃO DE DESIGN: REJEITAR
==============================

Escopo revisado: 100% das páginas/frames do arquivo Figma "Amparo —
Design System" + 100% das conexões do protótipo navegável.

------------------------------
 GATILHO DE REJEIÇÃO AUTOMÁTICA — VIOLAÇÃO DE SEGURANÇA/DISCRIÇÃO
------------------------------
Frame "Rede de Apoio / Notificação de Confirmação — Padrão": o texto da
notificação exibido no protótipo mostra "Sua guardiã Marina confirmou
seu alerta" — viola diretamente o Padrão 2 (Notificações Neutras) de
padroes-seguranca-discricao.md, que exige texto genérico sem nome de
contato nem conteúdo do alerta. Esta única violação aciona rejeição
automática do veredito geral, independentemente da pontuação dos demais
critérios.

------------------------------
 TABELA DE PONTUAÇÃO POR CRITÉRIO (para referência, mesmo com rejeição)
------------------------------
| Critério | Cobertura avaliada | Status |
|---|---|---|
| Consistência com design system (Caio) | 100% das telas | OK — nenhum placeholder não resolvido encontrado |
| WCAG 2.2 AA — Contraste (1.4.3) | 100% dos pares texto/fundo | OK |
| WCAG 2.2 AA — Touch target (2.5.8) | 100% dos elementos interativos | FALHA — botão "Cancelar" no frame "Emergência / Confirmação — Erro Sem Conexão" mede 20x20px, abaixo do mínimo de 24x24px |
| Auditoria POUR completa (wcag-audit-patterns) | 100% das telas | FALHA — ver correção específica abaixo |
| Heurísticas de Nielsen (Joana) | 100% dos fluxos | OK |
| Integridade do protótipo (Pietro) | 100% das conexões | OK — nenhuma tela morta ou link quebrado |

CORREÇÕES ESPECÍFICAS OBRIGATÓRIAS:

1. Frame "Rede de Apoio / Notificação de Confirmação — Padrão": substituir
   o texto da notificação por uma versão genérica (ex.: "Você tem uma
   atualização"), conforme Padrão 2 de Daniela Discrição. CORREÇÃO
   BLOQUEANTE.
2. Frame "Emergência / Confirmação — Erro Sem Conexão": aumentar o botão
   "Cancelar" para no mínimo 24x24px, conforme WCAG 2.2 critério 2.5.8.
3. Frame "Documentação / Anexar Evidência": princípio POUR "Perceivable"
   (via wcag-audit-patterns) identificou ausência de texto alternativo
   nos ícones de tipo de mídia (foto/áudio/vídeo) — adicionar rótulos
   acessíveis.

VEREDITO GERAL: REJEITAR — uma violação de segurança/discrição foi
encontrada (notificação com preview de conteúdo real), o que anula a
média geral independentemente das demais pontuações. Retorna ao Step 7
(Telma Tela) para correção das telas afetadas; o protótipo de Pietro
precisará ser refeito sobre as telas corrigidas.
```
