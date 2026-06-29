---
execution: inline
agent: vitoria-visual
inputFile: squads/landing-page-amparo/output/estrutura-conteudo.md
outputFile: squads/landing-page-amparo/output/especificacao-visual.md
---

# Step 4: Especificar Visual

## Context Loading

Load these files before executing:
- `squads/landing-page-amparo/output/estrutura-conteudo.md` (Camila) —
  arquitetura de seções e copy aprovados no Step 3.
- `squads/landing-page-amparo/output/inputs-e-referencias.md` (Step 1) —
  fonte de identidade visual confirmada (ou pendência) e referências de
  sites, se fornecidas.
- Design system mais recente publicado por `squads/marca-design-amparo/output/`
  (Claude Design e/ou markdown), se existir.
- `_opensquad/_memory/company.md` — tom de voz e público.
- `pipeline/data/research-brief.md` (seção 1, framework de UX de conversão).

## Instructions

### Process

1. Carregar as skills `design-taste-frontend`, `high-end-visual-design` e
   `frontend-design` antes de definir qualquer valor visual.
2. Verificar se o design system de `marca-design-amparo` existe. Se existir,
   usar seus tokens (cores, tipografia) fielmente, sem reinterpretação. Se
   não existir, definir uma paleta/tipografia provisória e marcá-la
   explicitamente como "PENDENTE — substituir quando marca-design-amparo
   publicar".
3. Documentar o design system completo: paleta (máximo 5 cores), tipografia
   (família, escala hero/heading/body/caption, pesos), espaçamento (unidade
   base, padding de seção), grid, border radius e estilo de sombra.
4. Verificar contraste WCAG AA (≥4.5:1 texto normal, ≥3:1 texto grande) para
   cada par texto/fundo do sistema antes de prosseguir.
5. Especificar cada uma das 7 seções definidas por Camila: layout/grid
   específico, imagery (nunca foto realista de violência/vítima), e
   variações responsivas (mobile/tablet/desktop).
6. Compilar `especificacao-visual.md` com o design system documentado, a
   especificação seção por seção, e a lista de pendências.

## Output Format

```
DESIGN SYSTEM
Fonte: {marca-design-amparo vX, ou "PENDENTE — paleta provisória"}
Cores: {lista com hex e uso}
Tipografia: {família, escala, pesos}
Espaçamento: {unidade base, padding de seção}
Grid: {colunas, max-width, gutter}
Contraste verificado: {pares texto/fundo com ratio}

SEÇÃO: {NOME}
Layout: {grid específico}
Imagery: {direção, simbólica/abstrata}
Responsivo: {comportamento mobile/tablet/desktop}
```

## Output Example

Ver `pipeline/data/output-examples.md`, Exemplos 5 e 6 (design system completo
e especificação de seção Hero) — o output real cobre as 7 seções com o mesmo
nível de especificidade (valores exatos, nunca aproximados).

## Veto Conditions

Reject and redo if ANY of these are true:
1. Algum valor de cor/tamanho/espaçamento está aproximado ("tom claro",
   "fonte grande") em vez de exato (hex, px).
2. O design system de `marca-design-amparo` existe e foi ignorado/reinterpretado em vez de usado fielmente.
3. Alguma direção de imagery usa foto realista de violência/vítima.

## Quality Criteria

- [ ] Design system documentado antes de qualquer seção individual
- [ ] Todo par texto/fundo com contraste verificado ≥4.5:1 (ou ≥3:1 para texto grande)
- [ ] Paleta provisória (se aplicável) marcada explicitamente como pendência
- [ ] Cada seção tem especificação responsiva explícita
