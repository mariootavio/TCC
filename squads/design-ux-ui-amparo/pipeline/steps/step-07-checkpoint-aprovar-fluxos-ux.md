---
type: checkpoint
---

# Step 7: Checkpoint — Aprovar Fluxos de UX

## Contexto

Joana Jornada mapeou a arquitetura de informação, os fluxos das 4 jornadas
críticas e os padrões de segurança/discrição no Step 6. Este checkpoint é o
mais sensível do pipeline: ele bloqueia o Step 8 (Telma Tela cria telas de
alta fidelidade no Figma — mutação irreversível de conteúdo visual). Nenhuma
tela pode ser desenhada sobre um fluxo de segurança não revisado e aprovado
explicitamente pelo usuário.

## Instruções

1. Carregar e mostrar ao usuário o conteúdo completo do arquivo indicado pelo
   `input_file` desta etapa no design original: `squads/design-ux-ui-amparo/output/fluxos-ux.md`
   — apresentar a arquitetura de informação, os fluxos das 4 jornadas
   críticas e, com destaque especial, a seção de padrões de segurança e
   discrição (nível de discrição adotado, especificação da saída rápida,
   política de notificações).
2. Perguntar explicitamente ao usuário, com atenção redobrada à seção de
   segurança/discrição:
   - O nível de discrição adotado (3 camadas, sem disfarce completo de UI) é
     aceitável, ou o usuário exige um nível mais alto de disfarce?
   - A especificação da saída rápida (1 toque, posição fixa, transição
     instantânea) atende à expectativa de segurança?
   - Os fluxos das 4 jornadas críticas cobrem os cenários que o usuário
     considera essenciais?
3. Se aprovado: liberar o pipeline para o Step 8, onde Telma traduz esses
   fluxos em telas visuais.
4. Se rejeitado ou com pedido de ajuste: retornar ao Step 6 para Joana
   ajustar os fluxos antes de seguir — especialmente se o ajuste envolver o
   nível de discrição ou a especificação de saída rápida.

## Output Format

Não há `outputFile` formal para este checkpoint. Registrar a decisão do
usuário de forma clara na conversa, com destaque para qualquer decisão
específica sobre o nível de discrição adotado (porque essa decisão tem
consequência direta de segurança para a usuária final do app).

## Output Example

```
CHECKPOINT — Aprovar Fluxos de UX

Fluxos apresentados: arquitetura de informação (4 itens de bottom nav + 2
ações globais), as 4 jornadas críticas completas com caminho de erro, e os
padrões de segurança/discrição (discrição em 3 camadas, saída rápida em 1
toque com transição instantânea, notificações neutras).

Decisão do usuário: Aprovado. Usuário confirmou explicitamente que o nível de
discrição em 3 camadas é suficiente para o escopo do TCC (não exige disfarce
completo de UI como o Aspire News App).

Pipeline segue para Step 8: Telma Tela traduz estes fluxos aprovados em telas
de alta fidelidade e protótipo navegável no Figma.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O conteúdo de `fluxos-ux.md` não foi mostrado ao usuário, com destaque
   para a seção de segurança/discrição, antes de solicitar a aprovação.
2. O pipeline avança para o Step 8 sem uma decisão explícita de aprovação
   registrada — especialmente sem confirmação explícita sobre o nível de
   discrição adotado.

## Quality Criteria

- [ ] O usuário viu as 4 jornadas críticas completas e a seção de
      segurança/discrição antes de decidir.
- [ ] A decisão final sobre o nível de discrição está registrada de forma
      inequívoca.
- [ ] Qualquer ajuste solicitado está documentado para a próxima etapa
      incorporar antes da liberação do pipeline.
