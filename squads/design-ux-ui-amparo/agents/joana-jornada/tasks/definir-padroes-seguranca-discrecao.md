---
task: "Definir Padrões de Segurança e Discrição"
order: 3
input: |
  - fluxos_ux: Fluxos de UX já mapeados na task anterior — incorporados em squads/design-ux-ui-amparo/output/fluxos-ux.md
  - research_brief: Pesquisa de UX de segurança/privacidade — squads/design-ux-ui-amparo/pipeline/data/research-brief.md
output: |
  - padroes_seguranca: Especificação de modo discreto, saída rápida e notificações neutras — squads/design-ux-ui-amparo/output/fluxos-ux.md (seção final, consolidando o documento completo)
---

# Definir Padrões de Segurança e Discrição

Define especificamente os padrões de modo discreto, saída rápida (quick exit)
e notificações neutras que protegem a usuária caso o agressor tenha acesso ao
celular, com base na pesquisa de UX de segurança/privacidade (Safety Net
Project/techsafety.org) compilada em `research-brief.md`.

## Process

1. Carregar o research brief (seção de UX de segurança e discrição) e os
   fluxos de UX já mapeados — os padrões de segurança não são um adendo, são
   definidos com a mesma prioridade que os fluxos de funcionalidade.
2. Decidir e documentar explicitamente o nível de "modo discreto" adotado (ex.:
   disguise mode completo vs. discrição em camadas — ícone neutro + notificação
   sem preview + saída rápida), com base na pesquisa, justificando o trade-off
   de esforço vs. eficácia escolhido.
3. Especificar o mecanismo de saída rápida: deve estar acessível em no máximo 1
   toque/gesto de qualquer tela do app, na MESMA posição relativa em todas as
   telas (WCAG 3.2.6), com transição "Instant" (sem animação perceptível).
4. Especificar a política de notificações: conteúdo genérico/neutro por
   padrão, nunca expor o nome "Amparo" ou o conteúdo da ação na tela de
   bloqueio/preview.
5. Avaliar e documentar a mitigação de rastro no histórico do sistema/app-
   switcher/capturas de tela recentes — especificar o comportamento esperado
   (ex.: remoção do app-switcher ao acionar saída rápida).
6. Consolidar a especificação completa (arquitetura de informação + fluxos +
   padrões de segurança/discrição) em `output/fluxos-ux.md` e apresentar ao
   checkpoint de aprovação final desta etapa.

## Output Format

```yaml
padroes_seguranca:
  nivel_discricao_adotado: "string — com justificativa"
  saida_rapida:
    toques_maximo: 1
    posicao: "string — ex. canto superior direito, consistente em 100% das telas"
    transicao: "Instant"
  notificacoes:
    conteudo_padrao: "string — ex. genérico, sem nome do app"
  mitigacao_rastro:
    app_switcher: "string — comportamento esperado"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
DECISÃO DE ARQUITETURA: nível de discrição adotado

O Amparo NÃO disfarça a interface inteira como outro app (ex.: Aspire News
App) — exigiria manutenção de duas "personas" de UI completas, fora do escopo
deste TCC. Adota-se discrição em 3 camadas (Safety Net Project/techsafety.org):
  1. Ícone do app: nome neutro configurável no onboarding, não "Amparo".
  2. Notificações push: nunca mostram conteúdo no preview.
  3. Saída rápida: botão fixo no canto superior direito, presente em TODAS as
     telas (WCAG 3.2.6), touch target 44x44px. Um toque leva instantaneamente
     (transição "Instant") para uma Tela Neutra (clima fake funcional) e
     remove o app do app-switcher do sistema.

Retorno ao app real: gesto oculto configurável (ex.: toque longo de 1.5s no
ícone do sol) — sem botão visível "Voltar ao Amparo", o que anularia a
discrição.

Próximo passo: aguardando aprovação no checkpoint antes de Telma iniciar o
desenho visual deste fluxo.
```

## Quality Criteria

- [ ] O nível de discrição adotado está documentado com justificativa
      explícita, não apenas descrito.
- [ ] A saída rápida está especificada como acessível em no máximo 1 toque, em
      posição consistente, com transição instantânea.
- [ ] A política de notificações garante que nenhum conteúdo sensível aparece
      em preview/tela de bloqueio.

## Veto Conditions

Reject and redo if ANY are true:
1. O mecanismo de saída rápida exige mais de 1 toque/gesto ou usa transição
   animada perceptível.
2. A especificação de notificações permite que o nome "Amparo" ou o conteúdo
   da ação apareça em preview de tela bloqueada.
