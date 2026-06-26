---
type: checkpoint
---

# Step 3: Checkpoint — Aprovar Identidade Visual

## Contexto

Flávia Fonte gerou 2-3 direções de identidade visual de marca no Step 2. Este
checkpoint existe porque nenhuma tela de UI ou design system pode ser
construído sobre uma identidade não aprovada — é o primeiro dos gates de
aprovação obrigatórios do pipeline (Gate 2b: este step bloqueia o Step 4, que
faz mutações no Figma).

## Instruções

1. Carregar e mostrar ao usuário o conteúdo completo do arquivo indicado pelo
   `input_file` desta etapa no design original: `squads/design-ux-ui-amparo/output/identidade-visual.md`
   — apresentar as 2-3 direções de identidade, paletas, tipografia e a
   recomendação de Flávia, na íntegra, antes de pedir qualquer decisão.
2. Perguntar explicitamente ao usuário:
   - Ele aprova a direção recomendada por Flávia? Ou prefere outra das
     direções apresentadas?
   - Há algum ajuste pontual necessário (ex.: trocar uma cor específica,
     ajustar a tipografia) antes de seguir para o design system completo?
3. Se o usuário aprovar (com ou sem ajustes menores): registrar a decisão e
   liberar o pipeline para o Step 4 (criação do design system, que usa a
   identidade aprovada como base).
4. Se o usuário rejeitar ou pedir uma nova rodada de direções: retornar ao
   Step 2 para Flávia gerar novas direções, incorporando o feedback recebido.

## Output Format

Não há `outputFile` formal para este checkpoint (ele é um gate de
aprovação, não uma captura de novo conteúdo). Registrar a decisão do usuário
de forma clara na conversa, e quando aplicável, anotar qualquer ajuste pontual
solicitado para Flávia incorporar na próxima etapa.

## Output Example

```
CHECKPOINT — Aprovar Identidade Visual

Identidade apresentada: Direção 1 "Porto Seguro" (recomendada por Flávia),
mais Direções 2 "Abrigo" e 3 "Constância" como alternativas.

Decisão do usuário: Aprovada a Direção 1 ("Porto Seguro"), com um ajuste
pontual — usar #4F5E80 em vez de #5B6B8C como azul primário (tom levemente
mais escuro, preferência do usuário).

Pipeline segue para Step 4: Flávia constrói o design system completo sobre a
identidade "Porto Seguro" aprovada, já incorporando o ajuste de cor solicitado.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O conteúdo de `identidade-visual.md` não foi mostrado ao usuário antes de
   solicitar a aprovação.
2. O pipeline avança para o Step 4 sem uma decisão explícita de aprovação
   registrada.

## Quality Criteria

- [ ] O usuário viu as 2-3 direções completas (não um resumo reduzido) antes
      de decidir.
- [ ] A decisão final (aprovado / aprovado com ajuste / rejeitado) está
      registrada de forma inequívoca.
- [ ] Qualquer ajuste solicitado pelo usuário está documentado para a próxima
      etapa incorporar.
