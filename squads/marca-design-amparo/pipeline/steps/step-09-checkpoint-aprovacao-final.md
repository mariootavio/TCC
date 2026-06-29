---
type: checkpoint
inputFile: squads/marca-design-amparo/output/revisao-marca.md
---

# Step 9: Checkpoint — Aprovação Final

## Contexto

Este é o checkpoint final do pipeline. Marina Marca já produziu um
veredito estruturado (Step 8) sobre a identidade visual e o design system
juntos. Este checkpoint apresenta esse veredito ao usuário para a decisão
final, e formaliza a entrega: o nome e o link do projeto Claude Design
que serve de fonte de verdade da marca e do design system do Amparo, que
será o insumo direto da squad `fluxos-uxui-amparo` para reconstruir tudo
dentro do Figma.

## Instruções

1. Carregar e apresentar ao usuário o veredito completo de
   `squads/marca-design-amparo/output/revisao-marca.md` — tabela de
   pontuação, gatilhos de rejeição (se houver), feedback detalhado e o
   veredito final de Marina, na íntegra.
2. Informar explicitamente ao usuário o nome do projeto Claude Design
   ("Amparo — Marca & Design System") e orientar que ele pode abrir
   diretamente em claude.ai/design para revisar visualmente a identidade e
   o design system publicados.
3. Explicar que este trabalho — identidade visual + design system
   publicados no Claude Design — é o insumo direto que a squad
   `fluxos-uxui-amparo` vai usar para reconstruir tudo dentro do Figma.
4. Perguntar ao usuário se ele aprova a entrega final como concluída, ou
   se deseja alguma correção adicional antes de considerar este pipeline
   encerrado.
5. Se aprovado: registrar a aprovação final e encerrar o pipeline,
   recomendando o próximo passo (acionar a squad `fluxos-uxui-amparo`).
   Se não aprovado: registrar o feedback e direcionar de volta ao step
   relevante (Step 4 para identidade, Step 6 para design system).

## Output Format

Não há `outputFile` formal de novo conteúdo neste checkpoint — ele
consolida e encerra o pipeline. Registrar a decisão final do usuário de
forma clara na conversa.

## Output Example

```
CHECKPOINT — Aprovação Final

Veredito de Marina Marca: APROVAR COM RESSALVAS (média 7.8/10). Correção
obrigatória já aplicada por Tomás antes deste checkpoint: ajuste do token
color-action-emergency para terracotta-600 (contraste WCAG AA corrigido
para 4.6:1).

Projeto Claude Design: "Amparo — Marca & Design System"
(https://claude.ai/design/... — projeto contém identidade visual completa
e design system com tokens e componentes documentados).

Próximo passo recomendado: acionar a squad `fluxos-uxui-amparo`, que vai
ler este projeto Claude Design e reconstruir fielmente a identidade e o
design system dentro do Figma, antes de desenhar fluxos de UX e telas de
alta fidelidade.

Decisão do usuário: Aprovado. Pipeline marca-design-amparo encerrado com
sucesso.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O veredito completo de Marina não foi apresentado ao usuário antes da
   pergunta de aprovação final.
2. O nome/link do projeto Claude Design não foi informado explicitamente
   ao usuário como parte da entrega.

## Quality Criteria

- [ ] O usuário viu o veredito completo de Marina (tabela de pontuação e
      feedback detalhado), não um resumo reduzido.
- [ ] O nome do projeto Claude Design está registrado como parte da
      entrega final, com indicação de que é o insumo da squad
      `fluxos-uxui-amparo`.
- [ ] A decisão final do usuário (aprovado / correção adicional
      solicitada) está registrada de forma inequívoca.
