# Quality Criteria — Design UX/UI Amparo

> Compilação dos `quality_criteria` de cada agente em `design.yaml`. Usado por
> Wagner WCAG como rubrica de revisão e por todos os agentes como critério de
> autoavaliação antes de apresentar qualquer artefato a um checkpoint.

## Flávia Fonte — Identidade Visual e Design System

- O logo e o ícone do app não contêm nenhum símbolo literal de violência, socorro
  óbvio ("SOS", escudo vermelho, cruz) ou imagem que exponha o propósito do app a
  quem vê a tela de relance.
- Toda combinação de cor de texto/fundo na paleta atinge no mínimo 4.5:1 de
  contraste (texto normal) ou 3:1 (texto grande/componentes), verificado e
  documentado.
- Todo valor de cor, tipografia e espaçamento usado em qualquer componente está
  vinculado a um token (Figma Variable) — nenhum valor hardcoded.
- A paleta final usa no máximo 5-6 cores-base (incluindo neutros), com escalas
  derivadas via tokens — sem inflação de cores ad-hoc.
- Componentes seguem nomenclatura atômica consistente (ex.: `Atoms/Button/Primary`,
  `Molecules/Form-Field`) — nenhuma camada com nome genérico tipo "Rectangle 24".
- Cada direção de identidade visual apresentada para aprovação tem justificativa
  escrita amarrada ao brief de personalidade de marca.

## Joana Jornada — Arquitetura de Informação e Fluxos de UX

- Todas as 4 jornadas críticas mínimas (denúncia/evidência, emergência, modo
  discreto, rede de apoio) têm fluxo ponta a ponta documentado, incluindo caminho
  de erro.
- O botão/mecanismo de saída rápida está presente e na mesma posição relativa em
  100% das telas mapeadas (WCAG 3.2.6).
- Nenhuma ação irreversível (enviar denúncia, excluir registro, desativar modo
  discreto) ocorre sem uma etapa de confirmação explícita.
- Cada fluxo cita ao menos uma heurística de Nielsen nomeada e, quando aplicável,
  um critério WCAG 2.2 AA nomeado.
- Nenhuma notificação ou elemento de UI especificado expõe o nome "Amparo" ou o
  propósito do app em contexto de tela bloqueada/preview.

## Telma Tela — Telas de Alta Fidelidade e Protótipo Navegável

- 100% dos elementos visuais (cor, tipografia, espaçamento, componente) em cada
  tela correspondem a um token ou componente do design system aprovado — zero
  estilo ad-hoc.
- O botão/mecanismo de saída rápida aparece na posição idêntica em 100% das telas
  do protótipo.
- Todo elemento interativo tem touch target de no mínimo 24x24px (WCAG 2.5.8).
- O protótipo navegável permite percorrer as 4 jornadas críticas ponta a ponta
  sem nenhuma tela morta ou link quebrado.
- Toda ação irreversível mapeada por Joana tem sua etapa de confirmação
  visualmente presente e funcional no protótipo.
- Modais, alertas e confirmações são implementados como overlays, nunca como
  telas duplicadas.

## Wagner WCAG — Revisão Estruturada

- Toda nota atribuída tem justificativa escrita de ao menos uma frase com
  "porque".
- Toda correção obrigatória aponta o frame/página exato do Figma e descreve a
  correção específica a aplicar.
- O veredito final (APROVAR/REJEITAR/APROVAR COM RESSALVAS) é consistente com as
  regras de decisão: média ≥7 sem critério abaixo de 4 e sem gatilho de segurança
  violado = APROVAR; qualquer um desses violado = REJEITAR.
- Toda violação de padrão de segurança/discrição (saída rápida ausente,
  notificação que expõe conteúdo, ação irreversível sem confirmação) é tratada
  como gatilho de rejeição automática, independente da média geral.
- A revisão contém ao menos um "Ponto forte:" com exemplo concreto, mesmo em
  veredito de rejeição.
- O número da revisão atual (X de 3) está registrado, com escalonamento
  sinalizado caso ultrapasse 3 ciclos com o mesmo problema recorrente.

## Tabela de Decisão de Veredito (Wagner WCAG)

| Condição | Veredito |
|---|---|
| Média geral ≥ 7/10 e nenhum critério < 4/10 e nenhum gatilho de segurança violado | APROVAR |
| Média geral ≥ 7/10 e algum critério não-crítico entre 4-6/10 | APROVAR COM RESSALVAS |
| Média geral < 7/10 | REJEITAR |
| Qualquer critério < 4/10 | REJEITAR (gatilho automático) |
| Qualquer gatilho de segurança/discrição violado | REJEITAR (gatilho automático, independente da média) |
| 3+ ciclos de revisão com o mesmo problema recorrente | ESCALONAR para decisão do usuário |

## Critérios Transversais (aplicam-se a toda a squad)

- Toda escolha visual ou de fluxo é justificada e rastreável ao brief de marca,
  ao requisito de segurança/discrição, a uma heurística de Nielsen ou a um
  critério WCAG nomeado — nunca apresentada como preferência estética sem critério.
- Nenhum artefato é apresentado a um checkpoint de aprovação sem que o agente
  responsável tenha verificado seus próprios quality_criteria primeiro.
