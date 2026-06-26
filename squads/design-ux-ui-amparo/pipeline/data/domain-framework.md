# Domain Framework — Design UX/UI Amparo

> Compilação dos `operational_framework` de cada agente definidos em
> `squads/design-ux-ui-amparo/_build/design.yaml`. Este documento consolida a
> metodologia operacional completa do domínio de design de produto desta squad:
> identidade de marca → design system → arquitetura de UX → UI de alta fidelidade →
> revisão. Cada agente também mantém sua própria cópia do framework relevante nos
> arquivos de task correspondentes.

## Visão Geral do Fluxo Metodológico

```
Brief de Design (checkpoint)
        ↓
Flávia Fonte  → Identidade Visual (logo, paleta, simbolismo, tipografia de marca)
        ↓ (checkpoint de aprovação)
Flávia Fonte  → Design System (tokens, componentes atômicos, variantes)
        ↓ (checkpoint de aprovação)
Joana Jornada → Arquitetura de Informação + Fluxos de UX + Padrões de Segurança/Discrição
        ↓ (checkpoint de aprovação)
Telma Tela    → Telas de Alta Fidelidade + Protótipo Navegável
        ↓
Wagner WCAG   → Revisão estruturada (design system, WCAG 2.2 AA, Nielsen, marca, protótipo)
        ↓ (on_reject volta para Telma Tela)
Checkpoint de Aprovação Final do Usuário
```

A regra estrutural do domínio: **fundação antes de construção** em cada camada —
tokens antes de componentes, fluxos em texto antes de telas visuais, design system
aprovado antes de qualquer tela de UI.

## 1. Framework de Flávia Fonte (Designer de Marca e Design System)

1. Carregar o brief de design aprovado (adjetivos de personalidade de marca,
   restrições de cor, referências visuais) e o contexto do Amparo — nunca iniciar
   sem esse brief.
2. Antes de qualquer chamada a `use_figma`, carregar a skill `figma:figma-use`. Se
   o arquivo Figma do projeto não existir, carregar primeiro `figma:figma-create-new-file`.
3. Identidade visual: aplicar design trauma-informado (tons frios/calmantes em vez
   de vermelho/amarelo de alarme) e simbolismo de proteção/acolhimento (nunca
   imagética literal de violência). Nome/ícone não podem expor o propósito do app.
4. Gerar 2-3 variações de direção de logo/identidade — nunca uma única opção
   fechada — com justificativa de cada escolha amarrada ao brief de marca.
5. Antes do design system, carregar também `figma:figma-generate-library` junto
   com `figma-use` (ensina O QUE construir e em que ordem).
6. Definir tokens primitivos (ex.: `purple-500`) separados de tokens semânticos
   (ex.: `color-action-primary`) ANTES de qualquer componente. Registrar como
   Figma Variables.
7. Construir componentes via atomic design: átomos → moléculas → organismos. Usar
   Variant Properties para variações visuais e boolean/instance-swap para estados.
8. Verificar cada par cor de texto/fundo contra WCAG AA (4.5:1 normal, 3:1 grande)
   antes de fixar a paleta final.
9. Documentar paleta, escala tipográfica, espaçamento, raio de borda e nomenclatura
   de componentes em resumo legível fora do Figma (para Joana e Telma).
10. Apresentar o design system completo ao checkpoint de aprovação antes de
    qualquer tela de UI ser construída sobre ele.

## 2. Framework de Joana Jornada (Estrategista de UX)

1. Carregar o brief aprovado, o design system aprovado por Flávia e o contexto do
   Amparo — fluxos desenhados sabendo quais componentes existem, nunca no vácuo.
2. Mapear TODAS as funcionalidades centrais (emergência, documentação segura, rede
   de apoio, acesso a profissionais, onboarding) em arquitetura de informação
   hierárquica antes de desenhar qualquer fluxo individual.
3. Para cada jornada crítica, mapear o fluxo ponta a ponta em texto/diagrama ANTES
   de qualquer wireframe visual. Jornadas mínimas obrigatórias: (a) registrar
   denúncia/evidência, (b) acionar emergência, (c) ativar/desativar modo discreto,
   (d) contatar rede de apoio pessoal.
4. Para fluxos complexos com múltiplos ramos, usar o FigJam (carregando
   `figma:figma-use-figjam` junto com `figma:figma-use`) para diagramar.
5. Tratar segurança/discrição como requisito de primeira classe: (a) saída rápida
   em no máximo 1 toque de qualquer tela; (b) notificações neutras por padrão;
   (c) avaliação de rastro no histórico/app-switcher/capturas de tela.
6. Avaliar e documentar explicitamente o nível de "modo discreto" adotado, com
   base na pesquisa de UX de segurança.
7. Aplicar heurísticas de Nielsen a cada fluxo, com atenção especial à prevenção
   de erros em ações irreversíveis.
8. Verificar cada fluxo contra critérios de acessibilidade aplicáveis (WCAG 3.2.6
   Ajuda Consistente; 2.5.8 tamanho mínimo de toque).
9. Documentar cada fluxo com pontos de decisão, estados de erro e racional de
   segurança/discrição — este documento é o que Telma traduz visualmente.
10. Apresentar os fluxos completos ao checkpoint de aprovação antes de qualquer
    tela de alta fidelidade.

## 3. Framework de Telma Tela (Designer de UI)

1. Carregar o design system aprovado e os fluxos de UX aprovados — nunca iniciar
   uma tela sem ambos os insumos aprovados.
2. Antes de `use_figma` para criar telas, carregar `figma:figma-use` junto com
   `figma:figma-generate-design` (traduz fluxo/página do app em telas usando
   componentes e tokens já existentes).
3. Organizar o arquivo Figma em páginas por fluxo — nunca misturar telas numa
   única página desorganizada.
4. Usar EXCLUSIVAMENTE componentes e tokens já definidos no design system — uma
   necessidade visual nova é sinalizada como lacuna, nunca resolvida ad-hoc.
5. Seguir o fluxo de UX exatamente como documentado, incluindo confirmações,
   estados de erro e posição consistente do botão de saída rápida (WCAG 3.2.6).
6. Verificar em cada tela: touch target mínimo 24x24px, contraste conforme tokens
   semânticos, foco visível não obscurecido (WCAG 2.4.11).
7. Montar o protótipo: overlays para modais/confirmações, Interactive Components
   para estados de botão, Smart Animate para transições com continuidade visual.
8. Planejar interações desde o início de cada fluxo; nomear frames de forma
   consistente entre estados equivalentes.
9. Testar a navegação completa do protótipo antes de entregar — nenhum link
   quebrado, nenhuma tela morta, incluindo o caminho de saída rápida.
10. Apresentar telas e link do protótipo a Wagner para revisão — nunca pular essa
    etapa por considerar o trabalho "visualmente pronto".

## 4. Framework de Wagner WCAG (Revisor de Design)

1. Carregar todos os critérios de referência (design system, fluxos de UX, brief
   de marca, `quality-criteria.md` da squad) antes de revisar qualquer tela.
2. Para inspecionar o Figma diretamente (`get_design_context`, `get_screenshot`),
   lembrar que ferramentas de leitura não exigem a skill `figma-use` (que é só
   para escrita via `use_figma`).
3. Percorrer TODAS as telas e o protótipo completo do início ao fim pelo menos uma
   vez antes de pontuar qualquer critério.
4. Pontuar cada critério individualmente em escala 1-10 com justificativa: (a)
   Consistência com design system; (b) Acessibilidade WCAG 2.2 AA; (c) Heurísticas
   de Nielsen; (d) Aderência à marca e tom acolhedor/discreto; (e) Integridade do
   protótipo navegável.
5. Tratar qualquer violação de padrão de segurança/discrição como gatilho de
   rejeição automática (hard rejection trigger), independentemente da média geral.
6. Calcular o veredito: APROVAR (média ≥7 e nenhum critério <4 e nenhum gatilho de
   segurança violado); REJEITAR (média <7 OU critério <4 OU gatilho violado);
   APROVAR COM RESSALVAS (média ≥7 mas critério não-crítico entre 4-6).
7. Para toda rejeição, identificar a tela/componente exato e fornecer a correção
   específica.
8. Reconhecer pontos fortes explicitamente, mesmo em revisão de rejeição.
9. Registrar o número da revisão atual; escalonar ao usuário após 3 ciclos de
   rejeição pelo mesmo motivo.
10. Entregar o veredito estruturado ao checkpoint final de aprovação do usuário.

## Princípio Transversal: Skills do Claude Code como Pré-requisito de Ferramenta

Diferente de squads de conteúdo, esta squad depende de ferramentas nativas do
ambiente Claude Code (Figma MCP) em vez de skills do catálogo Opensquad. Toda
chamada de escrita no Figma (`use_figma`, `create_new_file`) exige carregar a
skill correspondente do Claude Code antes da chamada — isso está documentado
explicitamente em cada agente que escreve no Figma (Flávia, Telma) e detalhado em
`native_environment_tools_note` do `design.yaml` desta squad.
