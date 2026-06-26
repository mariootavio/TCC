---
type: checkpoint
---

# Step 5: Checkpoint — Aprovar Design System

## Contexto

Flávia Fonte construiu o design system completo (tokens, tipografia,
componentes atômicos) no Step 4. Este checkpoint bloqueia a entrada de Joana
Jornada no pipeline (Step 6) — nenhum fluxo de UX deve ser desenhado sabendo
"mais ou menos" quais componentes existem; o design system precisa estar
formalmente aprovado primeiro.

## Instruções

1. Carregar e mostrar ao usuário o conteúdo completo do arquivo indicado pelo
   `input_file` desta etapa no design original: `squads/design-ux-ui-amparo/output/design-system.md`
   — apresentar tokens primitivos, tokens semânticos, escala tipográfica e a
   lista de componentes (átomos/moléculas/organismos) na íntegra.
2. Perguntar explicitamente ao usuário:
   - O conjunto de tokens e componentes cobre o que ele imagina para o app
     (ou falta algo evidente, como um componente de funcionalidade já
     conhecida do projeto)?
   - A paleta e a tipografia estão de acordo com a identidade visual aprovada
     no Step 3?
   - Há algum ajuste necessário antes de Joana iniciar os fluxos de UX?
3. Se aprovado: liberar o pipeline para o Step 6, onde Joana usa este design
   system como insumo fixo para desenhar os fluxos.
4. Se rejeitado ou com pedido de ajuste: retornar ao Step 4 para Flávia
   ajustar o design system antes de seguir.

## Output Format

Não há `outputFile` formal para este checkpoint. Registrar a decisão do
usuário de forma clara na conversa, e quando aplicável, anotar qualquer
ajuste solicitado para Flávia incorporar antes de liberar o pipeline.

## Output Example

```
CHECKPOINT — Aprovar Design System

Design system apresentado: tokens primitivos (slate/lilac/jade), tokens
semânticos (color-action-primary, color-action-emergency em jade-700),
tipografia 'Source Sans 3' em 4 níveis, componentes organizados em
átomos/moléculas/organismos.

Decisão do usuário: Aprovado sem ajustes. Usuário destacou positivamente o
uso de jade-700 (verde) em vez de vermelho para ações de emergência.

Pipeline segue para Step 6: Joana Jornada inicia o mapeamento da arquitetura
de informação e dos fluxos de UX usando este design system como base fixa.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O conteúdo de `design-system.md` não foi mostrado ao usuário antes de
   solicitar a aprovação.
2. O pipeline avança para o Step 6 sem uma decisão explícita de aprovação
   registrada.

## Quality Criteria

- [ ] O usuário viu a lista completa de tokens e componentes antes de decidir.
- [ ] A decisão final está registrada de forma inequívoca.
- [ ] Qualquer ajuste solicitado está documentado para a próxima etapa
      incorporar antes da liberação do pipeline.
