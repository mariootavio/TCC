---
type: checkpoint
inputFile: squads/marca-design-amparo/output/identidade-visual.md
---

# Step 6: Checkpoint — Aprovar Identidade Visual

## Contexto

Flávia Fonte gerou 2-3 direções de identidade visual de marca no Step 5 e
publicou-as no projeto Claude Design via `DesignSync`. Este checkpoint
existe porque nenhum design system pode ser construído sobre uma
identidade não aprovada — é o primeiro gate de aprovação obrigatório do
pipeline depois da criação visual (bloqueia o Step 7, que constrói tokens
e componentes sobre a identidade escolhida).

## Instruções

1. Carregar e mostrar ao usuário o conteúdo completo de
   `squads/marca-design-amparo/output/identidade-visual.md` — apresentar
   as 2-3 direções de identidade, paletas, tipografia, lógica de símbolo e
   a recomendação de Flávia, na íntegra, antes de pedir qualquer decisão.
   Informar também o nome do projeto Claude Design onde as direções foram
   publicadas, para o usuário poder abrir e visualizar diretamente em
   claude.ai/design se desejar.
2. Perguntar explicitamente ao usuário:
   - Ele aprova a direção recomendada por Flávia? Ou prefere outra das
     direções apresentadas?
   - Há algum ajuste pontual necessário (ex.: trocar uma cor específica,
     ajustar a tipografia) antes de seguir para o design system completo?
3. Se o usuário aprovar (com ou sem ajustes menores): registrar a decisão
   e liberar o pipeline para o Step 7 (criação do design system, que usa a
   identidade aprovada como base).
4. Se o usuário rejeitar ou pedir uma nova rodada de direções: retornar ao
   Step 5 para Flávia gerar novas direções, incorporando o feedback
   recebido.

## Output Format

Não há `outputFile` formal para este checkpoint (ele é um gate de
aprovação, não uma captura de novo conteúdo). Registrar a decisão do
usuário de forma clara na conversa, e quando aplicável, anotar qualquer
ajuste pontual solicitado para Flávia incorporar antes da próxima etapa.

## Output Example

```
CHECKPOINT — Aprovar Identidade Visual

Identidade apresentada: Direção 1 "Porto Seguro" (recomendada por Flávia),
mais Direções 2 "Abrigo" e 3 "Constância" como alternativas. Publicado no
projeto Claude Design "Amparo — Marca & Design System"
(identity/logo-direcao-1.html, identity/logo-direcao-2.html,
identity/logo-direcao-3.html).

Decisão do usuário: Aprovada a Direção 1 ("Porto Seguro"), com um ajuste
pontual — usar #4F5E80 em vez de #5B6B8C como azul primário (tom levemente
mais escuro, preferência do usuário).

Pipeline segue para Step 7: Tomás Tokens constrói o design system completo
sobre a identidade "Porto Seguro" aprovada, já incorporando o ajuste de cor
solicitado.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O conteúdo de `identidade-visual.md` não foi mostrado ao usuário antes
   de solicitar a aprovação.
2. O pipeline avança para o Step 7 sem uma decisão explícita de aprovação
   registrada.

## Quality Criteria

- [ ] O usuário viu as 2-3 direções completas (não um resumo reduzido)
      antes de decidir.
- [ ] A decisão final (aprovado / aprovado com ajuste / rejeitado) está
      registrada de forma inequívoca.
- [ ] Qualquer ajuste solicitado pelo usuário está documentado para a
      próxima etapa incorporar.
