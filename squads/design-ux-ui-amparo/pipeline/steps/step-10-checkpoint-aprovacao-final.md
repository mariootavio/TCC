---
type: checkpoint
---

# Step 10: Checkpoint — Aprovação Final

## Contexto

Wagner WCAG entregou o veredito estruturado de revisão no Step 9. Se o
veredito foi REJEITAR, o pipeline já retornou automaticamente ao Step 8
(`on_reject: 8`) antes de chegar aqui — este checkpoint só é alcançado quando
a revisão resultou em APROVAR ou APROVAR COM RESSALVAS. Este é o checkpoint
final do pipeline: a decisão do usuário aqui encerra (ou reabre) o ciclo de
produção de design da squad.

## Instruções

1. Carregar e mostrar ao usuário o conteúdo completo do arquivo indicado pelo
   `input_file` desta etapa no design original: `squads/design-ux-ui-amparo/output/revisao-design.md`
   — apresentar a tabela de pontuação completa, os pontos fortes, qualquer
   sugestão não-bloqueante registrada, e o veredito final de Wagner.
2. Perguntar explicitamente ao usuário:
   - Ele concorda com o veredito de Wagner (APROVAR ou APROVAR COM
     RESSALVAS)?
   - Se houver sugestões não-bloqueantes registradas, ele quer que sejam
     aplicadas antes de considerar o trabalho encerrado, ou aceita o estado
     atual como entrega final?
   - Há algo que Wagner não cobriu e que o usuário quer avaliar pessoalmente
     no arquivo Figma antes de aprovar definitivamente?
3. Se o usuário aprovar definitivamente: registrar a aprovação final, marcar o
   ciclo de design como concluído e atualizar `squads/design-ux-ui-amparo/_memory/runs.md`
   com o resultado deste run.
4. Se o usuário pedir ajustes adicionais (mesmo após um veredito de Wagner
   favorável): retornar ao Step 8 (Telma Tela) para incorporar o feedback
   antes de re-rodar a revisão.

## Output Format

Não há `outputFile` formal para este checkpoint. Registrar a decisão final do
usuário de forma clara na conversa, e refletir o resultado do run em
`_memory/runs.md` (data, tema, output, resultado).

## Output Example

```
CHECKPOINT — Aprovação Final

Revisão apresentada: Wagner WCAG — Revisão 1 de 3, veredito APROVAR (média
8.8/10), com 2 sugestões não-bloqueantes registradas (ajuste de z-index em
"Lista de Registros" e renomeação de camadas internas em "Modal-Captura").

Decisão do usuário: Aprovado definitivamente. Usuário optou por aceitar as 2
sugestões não-bloqueantes como pendência de polimento futuro, não bloqueante
para a entrega atual.

Resultado: ciclo de design do Amparo concluído nesta rodada. Entregáveis:
identidade visual aprovada, design system completo, fluxos de UX
documentados, telas de alta fidelidade e protótipo navegável no Figma,
revisão estruturada de Wagner.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O conteúdo de `revisao-design.md` não foi mostrado ao usuário (scoring
   table completa) antes de solicitar a aprovação final.
2. O run é encerrado como concluído sem uma decisão explícita de aprovação
   final do usuário registrada.

## Quality Criteria

- [ ] O usuário viu a tabela de pontuação completa e o veredito de Wagner
      antes de decidir.
- [ ] A decisão final de aprovação (ou pedido de novo ciclo) está registrada
      de forma inequívoca.
- [ ] `_memory/runs.md` é atualizado refletindo o resultado deste run.
