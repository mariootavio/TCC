---
type: checkpoint
---

# Step 3: Checkpoint — Aprovar Especificação/Prompt

Apresente ao usuário a especificação ou prompt gerado por Flávia Fonte
(`squads/marca-design-amparo/output/especificacao.md`), destacando:

- O tipo de entrega (prompt de imagem, especificação de componente, ou
  especificação de tela/página).
- O resultado da verificação de duplicidade (algo assim já existia? foi
  reaproveitado ou é realmente novo?).
- O roteamento decidido: se este ciclo termina aqui (só o
  prompt/especificação) ou se segue para implementação real no Figma
  (Step 4, Tomás Tokens).

Pergunte explicitamente:

- A especificação/prompt está alinhada com o que você pediu no Step 1?
- Cada cor/fonte/componente citado bate com o que você já conhece do
  design system em `brand/design-system.md`? Algo parece deslocado da
  identidade do Amparo?
- O roteamento (só prompt vs. implementação no Figma) ainda é o que você
  quer, ou mudou de ideia depois de ver a especificação?

Se o usuário aprovar, o pipeline segue para o Step 4 (Tomás Tokens —
implementação no Figma, se o roteamento pedir isso; caso contrário Tomás só
registra "não aplicável" e o pipeline segue direto para a auditoria de
Marina). Se o usuário pedir ajustes, volte ao Step 2 (Flávia Fonte) para
reespecificar.

Nunca avance sem confirmação explícita do usuário sobre a especificação —
tanto a implementação de Tomás quanto a auditoria de Marina dependem
inteiramente da qualidade e fidelidade deste documento.
