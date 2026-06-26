---
execution: inline
agent: flavia-fonte
inputFile: squads/design-ux-ui-amparo/output/identidade-visual.md
outputFile: squads/design-ux-ui-amparo/output/design-system.md
---

# Step 4: Criar Design System

## Context Loading

Load these files before executing:
- `squads/design-ux-ui-amparo/output/identidade-visual.md` — identidade visual aprovada no checkpoint anterior (Step 3)
- `_opensquad/_memory/company.md` — contexto do projeto Amparo
- `squads/design-ux-ui-amparo/pipeline/data/research-brief.md` — pesquisa sobre atomic design e tokens (seção 4)
- `squads/design-ux-ui-amparo/pipeline/data/quality-criteria.md` — critérios de qualidade de Flávia Fonte para design system
- `squads/design-ux-ui-amparo/agents/flavia-fonte/tasks/criar-design-system.md` — task completa com processo e formato de output

## Instructions

### Process

1. Carregar a identidade visual aprovada — não iniciar sem essa aprovação
   confirmada. Antes de qualquer chamada a `use_figma`, invocar a skill
   `figma:figma-use` junto com `figma:figma-generate-library` (ensina o que
   construir — variáveis, fundações, componentes, variantes — e em que ordem).
2. Definir tokens primitivos (ex.: `slate-500`) antes de tokens semânticos
   (ex.: `color-action-primary`), registrando-os como Figma Variables em
   coleções separadas.
3. Construir os componentes via atomic design (átomos → moléculas →
   organismos), usando Variant Properties para variações visuais e
   boolean/instance-swap para estados.
4. Verificar cada cor de texto/fundo contra o contraste mínimo WCAG AA antes
   de fixar a paleta final.
5. Documentar paleta, tipografia, espaçamento, raio de borda e nomenclatura de
   componentes em `output/design-system.md`, legível sem precisar abrir o
   Figma, e parar aqui — o checkpoint seguinte (Step 5) decide se a squad avança.

## Output Format

The output MUST follow this exact structure:
```markdown
# Design System — Amparo

Base: [identidade visual de origem, aprovada]
Arquivo Figma: [nome + página]
Metodologia: Atomic Design + Figma Variables

## Tokens Primitivos
[coleções e escalas]

## Tokens Semânticos
[nome → referência ao primitivo, com racional quando relevante]

## Tipografia
[escala: nível, tamanho/altura de linha, peso]

## Componentes
### Átomos
[lista]
### Moléculas
[lista]
### Organismos
[lista]

## Touch Targets
[confirmação do mínimo WCAG 2.5.8]

## Próximo Passo
Aguardando aprovação no checkpoint antes de Joana iniciar os fluxos de UX.
```

## Output Example

```markdown
# Design System — Amparo

Base: Identidade Visual "Porto Seguro" (aprovada)
Arquivo Figma: Amparo — Marca & Design System (página "02. Design System")
Metodologia: Atomic Design + Figma Variables

## Tokens Primitivos
slate-50 a slate-900, lilac-50 a lilac-900, jade-50 a jade-900
spacing-1 a spacing-8 (4px a 64px), radius-sm/md/lg (8/16/24px)

## Tokens Semânticos
color-bg-default → slate-50 | color-action-primary → slate-600
color-action-emergency → jade-700 (verde, não vermelho — evita leitura de
"alarme" caso a tela seja vista de relance)
color-text-primary → slate-900 | color-border → slate-200

## Tipografia
display: 32/40, weight 700 | heading: 24/32, weight 700
body: 16/24, weight 400 | caption: 13/18, weight 500
Contraste mínimo testado contra slate-50/lilac-50: 7.2:1 (acima do mínimo
WCAG AA de 4.5:1).

## Componentes
### Átomos
Button (primary/secondary/ghost/emergency × sm/md/lg), Input/Text, Icon
(24x24), Tag, Avatar
### Moléculas
Form-Field, List-Item, Alert-Banner, Search-Bar
### Organismos
App-Header, Bottom-Nav, Report-Card, Contact-Card, Emergency-Action-Sheet

## Touch Targets
Mínimo 24x24px (WCAG 2.5.8); Button "sm" com área de toque mínima de 44x44px
via padding invisível.

## Próximo Passo
Aguardando aprovação no checkpoint antes de Joana iniciar os fluxos de UX.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Algum componente documentado usa valor hardcoded em vez de referenciar um
   token primitivo ou semântico.
2. Alguma combinação de cor de texto/fundo na paleta final não atinge o
   contraste mínimo WCAG AA documentado.

## Quality Criteria

- [ ] Tokens primitivos e semânticos claramente separados, todos registrados
      como Figma Variables.
- [ ] Componentes seguem nomenclatura atômica consistente.
- [ ] Touch targets mínimos confirmados para todo componente interativo.
- [ ] A skill `figma:figma-generate-library` foi carregada junto com
      `figma-use` antes da criação dos componentes.
