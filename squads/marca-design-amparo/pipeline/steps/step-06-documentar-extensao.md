---
execution: inline
agent: helena-manual
inputFile: squads/marca-design-amparo/output/auditoria.md
outputFile: squads/marca-design-amparo/output/manual-extensoes.md
---

# Step 6: Documentar Extensão

## Context Loading

Load these files before executing:
- `squads/marca-design-amparo/output/especificacao.md` — Flávia Fonte.
- `squads/marca-design-amparo/output/implementacao-figma.md` — Tomás
  Tokens (ou "não aplicável").
- `squads/marca-design-amparo/output/auditoria.md` — veredito de Marina
  Marca (Step 5). Se o veredito foi REJEITAR, este step não roda — o
  pipeline já retornou ao Step 2.
- `.agents/skills/manual-identidade-visual-premium/references/
  vocabulario-design.md` (seção "Palavras a evitar") — lido diretamente.

## Instructions

### Process

1. Confirmar que o veredito de Marina foi APROVAR, ou APROVAR COM
   RESSALVAS com a correção já confirmada como aplicada — nunca documentar
   algo pendente como definitivo.
2. Redigir uma entrada nova para o apêndice: data, pedido original, o que
   foi criado, tokens/valores usados com origem exata em
   `brand/design-system.md`, localização final (arquivo de output e/ou
   frame do Figma), veredito de Marina.
3. Escrever sem nenhuma frase genérica, seguindo a régua anti-genérico do
   skill `manual-identidade-visual-premium`.
4. Anexar a entrada ao final de
   `squads/marca-design-amparo/output/manual-extensoes.md` (criar o
   arquivo se ainda não existir) — nunca reescrever entradas anteriores,
   nunca editar `brand/manual-amparo.pdf` ou `brand/design-system.md`.

## Output Format

Ver `pipeline/data/output-examples.md` (Exemplos 1 e 2 de Helena Manual) —
formato de entrada de apêndice, para componente e para prompt de imagem.

## Output Example

Ver `pipeline/data/output-examples.md` (Exemplos 1 e 2 de Helena Manual).

## Veto Conditions

Reject and redo if ANY of these are true:
1. Uma entrada documenta como definitivo algo que Marina reprovou ou
   marcou como pendente de correção sem confirmação.
2. `brand/manual-amparo.pdf` ou `brand/design-system.md` foram editados
   diretamente em vez de `output/manual-extensoes.md`.
3. Uma entrada anterior do apêndice foi reescrita ou removida em vez de
   preservada.

## Quality Criteria

- [ ] A entrada é executável sem interpretação (hex, fonte, valor
      numérico, localização exata).
- [ ] A entrada é datada e cita o pedido original e o veredito de Marina.
- [ ] `brand/manual-amparo.pdf` e `brand/design-system.md` permanecem
      inalterados.
- [ ] A entrada foi anexada ao final do apêndice, sem remover ou
      reescrever entradas anteriores.
