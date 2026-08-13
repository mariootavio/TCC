TELAS DE ALTA FIDELIDADE — AMPARO
Arquivo Figma: "App" (fileKey `uq8ZErrErmrt2lCfLPq6j3`) — mesmo arquivo de Caio,
6 novas páginas adicionadas, uma por fluxo de `fluxos-ux.md` (Joana, aprovado
no checkpoint Step 6).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PÁGINA: "📱 Fluxo 1 — Emergência"
Fonte: fluxos-ux.md, Fluxo 1 "Acionamento de Emergência", RF-CORE-01.

- Frame "Emergência / Acionamento — Padrão": Botão SOS (componente de Caio) sempre visível. Corresponde ao passo 1 do Caminho Feliz.
- Frame "Emergência / Confirmação — Padrão": card de status "Alerta enviado" (cor feedback/confirm). Corresponde aos passos 2-3 do Caminho Feliz.
- Frame "Emergência / Confirmação — Erro Sem Conexão": mesma estrutura do frame anterior, cor neutra. Corresponde ao Caminho de Erro "Sem Conexão de Dados".

PÁGINA: "📱 Fluxo 2 — Documentação"
Fonte: fluxos-ux.md, Fluxo 2 "Registro de Ocorrência com Evidências", RF-CORE-04.

- Frame "Documentação / Início — Padrão": lista de ocorrências + Botão Primário "Nova ocorrência" (componente de Caio). Passo 1 do Caminho Feliz.
- Frame "Documentação / Detalhe — Prova Verificada": cards de status "Backup concluído" e "Prova verificada" (hash + timestamp). Passos 3-4 do Caminho Feliz.
- Frame "Documentação / Detalhe — Erro Backup Pendente": card neutro "Backup pendente". Caminho de Erro "Falha no Backup em Nuvem".

PÁGINA: "📱 Fluxo 3 — Modo Disfarçado"
Fonte: fluxos-ux.md, Fluxo 3 "Ativação do Modo Disfarçado e Saída Rápida", RF-CORE-02.

- Frame "Disfarce / Onboarding — Escolher": biblioteca de disfarces (calculadora, bloco de notas, previsão do tempo, lista de tarefas), conforme padroes-seguranca-discricao.md Padrão 2.
- Frame "Disfarce / Calculadora — Ativa": calculadora funcional com destrave por código numérico ("1207"), falha silenciosa documentada em nota de tela.
- Frame "Disfarce / App Switcher — Rastro Minimizado": representação da lista de apps recentes do SO mostrando o disfarce, nunca o Amparo real — Padrão 4 de Daniela.

PÁGINA: "📱 Fluxo 4 — Rede de Guardiões"
Fonte: fluxos-ux.md, Fluxo 4 "Rede de Guardiões — Cadastro e Confirmação de Alerta", RF-CORE-05.

- Frame "Rede de Apoio / Lista — Padrão": guardiã + dependente cadastrados, Botão Secundário "Adicionar guardião".
- Frame "Rede de Apoio / Confirmação de Alerta — Padrão": título de notificação neutro ("Você tem uma atualização", Padrão 3 de Daniela), Botão de Confirmação, card de encaminhamento institucional (Ideia 5).
- Frame "Rede de Apoio / Check-in — Sem Resposta": escalonamento automático (Ideia 1), cor de alerta (feedback/sos) no card principal.

PÁGINA: "📱 Fluxo 5 — Classificação de Risco (RF-CORE-06)"
Fonte: fluxos-ux.md, Fluxo 5 "Pipeline de Classificação de Risco", RF-CORE-06.
Como RF-CORE-06 é uma camada transversal (não um destino de navegação), as
telas traduzem a tela "Início" em suas 3 variações de nível de risco.

- Frame "Início / Nível BAIXO": card verde (feedback/confirm), monitoramento discreto + conteúdo educativo.
- Frame "Início / Nível MÉDIO": card neutro, alerta discreto pré-configurado.
- Frame "Início / Nível ALTO": card vermelho (feedback/sos), Botão SOS priorizado visualmente, Rede de Apoio com notificação priorizada.
- Frame "Pipeline / Nota Técnica" (fora do fluxo de telas, documentação lateral): descreve o pipeline App → Backend → API de IA → resultado, e o comportamento de fallback (mantém último nível conhecido, nunca bloqueia o SOS).

PÁGINA: "📱 Fluxo 6 — Delegacias Próximas"
Fonte: fluxos-ux.md, Fluxo 6 "Delegacias Próximas" (trazido de Trabalhos
Futuros por decisão do usuário no checkpoint Step 6).

- Frame "Delegacias / Lista — Padrão": 2 delegacias com distância/telefone.
- Frame "Delegacias / Erro — Permissão Negada": busca manual por cidade/CEP como alternativa.
- Frame "Delegacias / Erro — Nenhuma Encontrada": Ligue 180 e 190 como alternativa imediata, nunca tela vazia.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PONTO DE VERIFICAÇÃO DE SEGURANÇA (transversal)

O placeholder "✕ sair" (saída rápida) está posicionado de forma absoluta no
canto superior direito, com padding idêntico (16px), em 100% dos 18 frames
de tela criados nesta rodada — nenhuma variação de posição entre telas,
conforme Padrão 1 de Daniela Discrição.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

EXPANSÃO DE ESCOPO (a pedido do usuário, checkpoint Step 10, 2026-08-13)

Após o veredito de Wagner, o usuário pediu o "app completo": navegação
inferior real, jornada de entrada e o conteúdo do menu "Mais". Adicionado
nesta mesma rodada, sem retorno formal ao Step 7:

PÁGINA: "🧩 Navegação Inferior" (nova, resolve a Ressalva 3 de Wagner)
ComponentSet "Navegação Inferior" — 5 variantes (Ativo=Início/Documentação/
Rede de Apoio/Chat de Apoio/Mais), ícones vetoriais 24×24 (seção 9),
aplicado nas 7 telas-hub: 3 telas de "Início" (Fluxo 5), "Documentação /
Início" (Fluxo 2), "Rede de Apoio / Lista" (Fluxo 4), "Chat de Apoio /
Conversa" e "Mais / Hub" (Fluxo 7).

PÁGINA: "📱 Onboarding — Entrada" (nova)
- Frame "Onboarding / Cadastro": nome, e-mail/telefone, senha — usa
  componentes Input e Botão de Caio.
- Frame "Onboarding / Login": e-mail/telefone, senha, "Esqueci minha senha".

PÁGINA: "📱 Fluxo 7 — Menu Mais" (nova)
- Frame "Mais / Hub — Padrão": 4 cards de navegação (Central de Conteúdo e
  Direitos, Assistente de Triagem, Relatos Anônimos, Configurações de
  Segurança) + bottom nav.
- Frame "Chat de Apoio / Conversa — Padrão": RF-CORE-03, bolhas de
  mensagem, "Apagar histórico" em destaque (não escondido em submenu).
- Frame "Central de Conteúdo e Direitos / Lista — Padrão": Ideia 11 + 14
  unificadas — 4 artigos educativos/legais.
- Frame "Assistente de Triagem / Conversa — Padrão": Ideia 9, com nota
  explícita distinguindo de RF-CORE-06.
- Frame "Relatos Anônimos / Feed — Padrão": Ideia 15, 2 relatos de exemplo.

PÁGINA: "🗺️ Mapa Completo do App" (nova — visão única solicitada pelo
usuário: "quero tudo em uma única tela também com o fluxo completo do
aplicativo")
Diagrama de blocos e setas mostrando as ~26 telas do app e suas conexões:
entrada (Welcome → Cadastro/Login → Escolher Disfarce → Calculadora →
Início), os 5 tabs de navegação principal com seus sub-fluxos, a ação
global de Emergência, a camada transversal de Saída Rápida, o fluxo de
Delegacias e o pipeline de RF-CORE-06 — com legenda de cores. Este mapa é
uma referência visual (sitemap), não um protótipo clicável adicional; cada
bloco corresponde a uma tela real e navegável em sua página de origem.

BUG CORRIGIDO NESTA RODADA: texto das bolhas de chat ("Chat de Apoio")
estava configurado sem quebra de linha (transbordando a bolha) —
corrigido com `textAutoResize: 'HEIGHT'` e largura explícita.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PENDÊNCIAS PARA CAIO COMPONENTES

1. **Ícone de saída rápida**: nenhum componente existe no design system — usado um placeholder textual "✕ sair" em todas as 18 telas. Recomendação: criar um componente "Ícone/Saída Rápida" com Variant Properties mínimas (só um estado), fixável em qualquer frame.
2. **Indicador de Status**: usado o componente "Card" como placeholder para status de sucesso/atenção/neutro (ex.: "Alerta enviado", "Backup pendente"), variando apenas a cor do título. Recomendação: criar um componente dedicado "Indicador de Status" com Variant Properties (Sucesso/Atenção/Neutro/Crítico), mais leve visualmente que um Card completo.
3. **Componente de Navegação Principal (bottom nav)**: já sinalizado por Iara em `arquitetura-informacao.md` — ainda não existe no design system; nenhuma das 18 telas desta rodada inclui a bottom nav real por esse motivo.
4. **Input de busca**: usado no Fluxo 6 (Delegacias) reaproveitando exatamente o componente "Input" de Caio — sem pendência aqui, apenas registro de uso.
5. **Componente de mapa/lista de resultados** (Fluxo 6): não existe no design system; Cards usados como placeholder temporário, sinalizado na própria tela.

Nenhuma pendência foi resolvida com um componente ad-hoc "definitivo" — todas
usam o componente mais próximo já existente, claramente identificado como
placeholder temporário na tela e neste relatório.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PASSADA DE REFINAMENTO VISUAL (a pedido do usuário, 2026-08-13)

O usuário avaliou a primeira versão como "muito simples" e pediu mais
cuidado visual. Correções aplicadas em 100% das 18 telas, sempre dentro dos
tokens já travados de `brand/design-system.md` — nenhuma cor, fonte ou
espaçamento novo foi inventado:

1. **Sombra dos cards**: o effect style "Sombra/Card" (já existente desde o
   Step 2) nunca havia sido aplicado às telas — corrigido em todos os cards
   de status/conteúdo das 6 páginas.
2. **Anel de pulso do Botão SOS**: especificado em design-system.md seção 8
   ("anel de pulso suave") mas nunca implementado — adicionado no componente-
   fonte de Caio (propaga automaticamente a toda instância já usada nas telas).
3. **Ícone de saída rápida real**: o placeholder de texto "✕ sair" foi
   substituído por um ícone vetorial X (grid 24×24, importado como SVG, nunca
   reconstruído a partir de formas rotacionadas) dentro de um chip circular
   suave — mais alinhado à seção 9 "Sistema de Ícones" do design system.
4. **Ícones de disfarce vetoriais**: os emojis da tela de onboarding (Fluxo 3)
   e do app switcher foram substituídos por ícones lineares 1.5pt na cor
   Vinho Amparo, seguindo a especificação exata da seção 9.
5. **Status bar mock**: adicionado indicador de hora ("9:41") no topo de
   todas as 18 telas, para leitura mais realista como app mobile.

A pendência de "Ícone de Saída Rápida" (item 1 da lista de pendências acima)
permanece registrada para Caio formalizar como componente oficial do design
system — o que foi construído aqui é um placeholder mais fiel, não a
resolução definitiva da pendência.
