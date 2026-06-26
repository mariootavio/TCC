---
execution: inline
agent: flavia-fonte
inputFile: squads/design-ux-ui-amparo/output/brief-design.md
outputFile: squads/design-ux-ui-amparo/output/identidade-visual.md
---

# Step 2: Criar Identidade Visual

## Context Loading

Load these files before executing:
- `squads/design-ux-ui-amparo/output/brief-design.md` — brief de design aprovado no checkpoint anterior (adjetivos de marca, restrições de cor, referências)
- `_opensquad/_memory/company.md` — contexto do projeto Amparo (público-alvo, tom de voz, problema central)
- `squads/design-ux-ui-amparo/pipeline/data/research-brief.md` — pesquisa sobre design trauma-informado e UX de segurança (seções 1 e 2)
- `squads/design-ux-ui-amparo/pipeline/data/anti-patterns.md` — anti-padrões de identidade visual a evitar
- `squads/design-ux-ui-amparo/agents/flavia-fonte/tasks/criar-identidade-visual.md` — task completa com processo e formato de output

## Instructions

### Process

1. Carregar o brief de design e o contexto do Amparo. Antes de qualquer
   chamada a `use_figma`, invocar a skill `figma:figma-use`. Se o arquivo
   Figma do projeto ainda não existir, invocar `figma:figma-create-new-file`
   antes de `create_new_file`.
2. Aplicar o framework de design trauma-informado (tons frios/calmantes,
   nunca vermelho/amarelo de alarme) e o requisito de discrição (nome/ícone
   não podem expor o propósito do app) para gerar 2-3 direções de
   logo/identidade no Figma (página "01. Identidade Visual").
3. Para cada direção, definir paleta (com hex), tipografia de marca e
   justificativa amarrada ao brief — nunca uma escolha sem razão explícita.
4. Recomendar uma direção, explicando por que ela atende melhor aos adjetivos
   do brief e ao requisito de segurança/discrição.
5. Compilar tudo em `output/identidade-visual.md` seguindo o formato da task
   `criar-identidade-visual.md`, e parar aqui — o checkpoint seguinte (Step 3)
   decide se a squad avança.

## Output Format

The output MUST follow this exact structure:
```markdown
# Identidade Visual — Amparo

Brief de origem: [adjetivos do brief]
Preparado em: [data]
Arquivo Figma: [nome do arquivo + página]

## Direção 1 — "[Nome]" [(recomendada) se aplicável]
Logo: [descrição]
Paleta: Primária [#HEX], Secundária [#HEX], Acento [#HEX]
Tipografia: [família tipográfica]
Justificativa: [conectada ao brief e/ou segurança]

## Direção 2 — "[Nome]"
[mesma estrutura, com trade-offs explícitos]

## Direção 3 — "[Nome]" (opcional)
[mesma estrutura]

## Recomendação
[qual direção e por quê]

## Próximo Passo
Aguardando aprovação no checkpoint antes do design system completo.
```

## Output Example

```markdown
# Identidade Visual — Amparo

Brief de origem: acolhedor, seguro, discreto
Preparado em: 2026-06-26
Arquivo Figma: Amparo — Marca & Design System (página "01. Identidade Visual")

## Direção 1 — "Porto Seguro" (recomendada)
Logo: monograma circular com a letra "A" estilizada formando duas mãos curvas
abstratas que se encontram — sem realismo, apenas forma geométrica suave. Não
remete a "ajuda" de forma óbvia para quem olha de relance a tela do celular.

Paleta: Primária #5B6B8C (azul-ardósia), Secundária #8B7FB8 (lilás suave),
Acento #2D9D8F (verde-jade), Neutro escuro #2B2D3A, Neutro claro #F4F2F7.

Tipografia: 'Source Sans 3' (humanista, alta legibilidade, sem serifa
decorativa).

Justificativa: tons frios seguem o princípio de design trauma-informado de
reduzir ansiedade visual, em contraste com o vermelho/laranja que o
benchmarking associa a apps de "alarme" institucionais. O monograma não
contém símbolo óbvio de violência ou socorro.

## Direção 2 — "Abrigo"
Paleta em tons terrosos + verde-oliva, logo com forma de folha abstrata. Mais
"natural/orgânico", porém risco de parecer app de bem-estar genérico.

## Direção 3 — "Constância"
Paleta azul-petróleo + dourado discreto, logo com padrão de ondas. Transmite
estabilidade, porém o dourado pode ler como "premium/financeiro".

## Recomendação
Direção 1 ("Porto Seguro"), por atender simultaneamente aos 3 adjetivos do
brief e ao requisito de segurança de não expor o propósito do app.

## Próximo Passo
Aguardando aprovação no checkpoint antes do design system completo.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Apenas uma direção de identidade é apresentada, sem alternativas reais.
2. Alguma direção usa imagética literal de violência/socorro óbvio, ou
   vermelho/laranja saturado como cor dominante.

## Quality Criteria

- [ ] No mínimo 2 direções de identidade apresentadas, cada uma com paleta,
      tipografia e justificativa.
- [ ] Nenhuma direção expõe o propósito do app de forma literal/óbvia.
- [ ] A recomendação final é explícita e justificada.
- [ ] A skill `figma:figma-use` (e `figma-create-new-file` se aplicável) foi
      carregada antes de qualquer chamada a ferramenta Figma de escrita.
