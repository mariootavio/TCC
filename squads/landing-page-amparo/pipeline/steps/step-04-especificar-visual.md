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
- `brand/design-system.md` e `brand/LogoAmparo.svg` — fonte única, travada
  e sempre disponível de cores, tipografia, espaçamento e logotipo do
  Amparo. Carregar sempre, sem exceção — não existe cenário de identidade
  "pendente" nesta squad.
- `squads/landing-page-amparo/output/inputs-e-referencias.md` (Step 1) —
  referências de sites, se fornecidas, e o modo de execução (nova
  construção ou ajuste).
- `_opensquad/_memory/company.md` — tom de voz e público.
- `pipeline/data/research-brief.md` (seção 1, framework de UX de conversão).
- `pipeline/data/direcao-imagens-ia.md` — direção de imagery/fotografia
  editorial para o público real do Amparo.

## Instructions

### Process

1. Carregar as skills `design-taste-frontend`, `high-end-visual-design` e
   `frontend-design` antes de definir qualquer valor visual.
2. Carregar `brand/design-system.md` e `brand/LogoAmparo.svg` e usar seus
   tokens (cores, tipografia, espaçamento, raios) fielmente, sem
   reinterpretação. Este é o design system finalizado do projeto — nunca
   um valor provisório ou inventado.
3. Documentar o design system traduzido para telas: paleta (máximo 5
   cores, de `brand/design-system.md`), tipografia (família, escala
   hero/heading/body/caption, pesos), espaçamento (unidade base, padding
   de seção), grid, border radius e estilo de sombra.
4. Verificar contraste WCAG AA (≥4.5:1 texto normal, ≥3:1 texto grande)
   para cada par texto/fundo do sistema antes de prosseguir.
5. Especificar cada uma das 7 seções definidas por Camila: layout/grid
   específico, direção de imagery (fotografia editorial ou ilustração
   simbólica, ver `direcao-imagens-ia.md` — nunca foto realista de
   violência/vítima), direção de motion/dinamismo (o que se move, quando,
   e por quê — para Diego Assets aplicar no protótipo Figma), e variações
   responsivas (frames mobile/tablet/desktop).
6. Compilar `especificacao-visual.md` com o design system documentado, a
   especificação seção por seção (incluindo imagery e motion), e a lista
   de pendências.

## Output Format

```text
DESIGN SYSTEM
Fonte: brand/design-system.md
Cores: {lista com hex e uso}
Tipografia: {família, escala, pesos}
Espaçamento: {unidade base, padding de seção}
Grid: {colunas, max-width, gutter}
Contraste verificado: {pares texto/fundo com ratio}

SEÇÃO: {NOME}
Layout: {grid específico}
Imagery: {direção, fotografia editorial ou simbólica/abstrata}
Motion: {o que se move, trigger, propósito}
Responsivo: {comportamento mobile/tablet/desktop}
```

## Output Example

Ver `pipeline/data/output-examples.md`, Exemplos 4 e 5 (design system
completo e especificação de seção Hero com imagery e motion) — o output
real cobre as 7 seções com o mesmo nível de especificidade (valores
exatos, nunca aproximados).

## Veto Conditions

Reject and redo if ANY of these are true:
1. Algum valor de cor/tamanho/espaçamento está aproximado ("tom claro",
   "fonte grande") em vez de exato (hex, px).
2. Algum valor de `brand/design-system.md` foi ignorado ou reinterpretado
   em vez de usado fielmente.
3. Alguma direção de imagery usa foto realista de violência/vítima.
4. Alguma direção de motion não tem propósito declarado (guiar atenção ou
   dar feedback).

## Quality Criteria

- [ ] Design system documentado antes de qualquer seção individual
- [ ] Todo par texto/fundo com contraste verificado ≥4.5:1 (ou ≥3:1 para texto grande)
- [ ] Cada seção tem especificação responsiva explícita e direção de motion com propósito
- [ ] Direção de imagery segue `direcao-imagens-ia.md`, nunca imagem realista de violência
