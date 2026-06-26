---
task: "Criar Design System"
order: 2
input: |
  - identidade_visual: Identidade visual já aprovada no checkpoint anterior — squads/design-ux-ui-amparo/output/identidade-visual.md
  - company_context: Contexto do projeto Amparo — _opensquad/_memory/company.md
output: |
  - design_system: Documento com tokens primitivos/semânticos, escala tipográfica e componentes atômicos documentados — squads/design-ux-ui-amparo/output/design-system.md
---

# Criar Design System

Constrói o design system completo no Figma (variáveis/tokens de cor, tipografia,
espaçamento, componentes atômicos e suas variantes) a partir da identidade
visual já aprovada, usando atomic design como metodologia organizadora.

## Process

1. Carregar a identidade visual aprovada (paleta, tipografia, simbolismo) — não
   iniciar o design system sem essa aprovação confirmada.
2. Antes de qualquer chamada à ferramenta `use_figma`, invocar a skill
   `figma:figma-use`; para este trabalho de design system, invocar também
   `figma:figma-generate-library` (ensina o que construir — variáveis,
   fundações, componentes, variantes — e em que ordem).
3. Definir tokens primitivos (ex.: `slate-500`) antes de tokens semânticos (ex.:
   `color-action-primary`), registrando-os como Figma Variables em coleções
   separadas ("primitives" e "semantic").
4. Construir os componentes seguindo a hierarquia de atomic design: átomos
   (botão, campo, ícone, tag) → moléculas (campo de busca, alerta, item de
   lista) → organismos (cabeçalho, card, barra de navegação). Usar Variant
   Properties para variações visuais e boolean/instance-swap para estados.
5. Verificar cada cor de texto/fundo contra o mínimo de contraste WCAG AA
   (4.5:1 texto normal, 3:1 texto grande) antes de fixar a paleta final.
6. Documentar a paleta, escala tipográfica, espaçamento, raio de borda e
   nomenclatura de componentes em `output/design-system.md`, legível sem
   precisar abrir o Figma, e apresentar ao checkpoint de aprovação.

## Output Format

```yaml
design_system:
  base: "string — identidade visual de origem (aprovada)"
  arquivo_figma: "string — nome do arquivo e página"
  tokens_primitivos:
    - colecao: "string"
      escalas: ["string"]
  tokens_semanticos:
    - nome: "string — ex. color-action-primary"
      referencia: "string — ex. slate-600"
  tipografia:
    - nivel: "string — ex. heading"
      tamanho_peso: "string"
  componentes:
    atomos: ["string"]
    moleculas: ["string"]
    organismos: ["string"]
  touch_targets: "string — confirmação do mínimo WCAG 2.5.8"
  proximo_passo: "string"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
DESIGN SYSTEM — AMPARO
Base: Identidade Visual "Porto Seguro" (aprovada)
Arquivo Figma: Amparo — Marca & Design System (página "02. Design System")
Metodologia: Atomic Design + Figma Variables

TOKENS PRIMITIVOS (coleção "primitives")
  slate-50 a slate-900, lilac-50 a lilac-900, jade-50 a jade-900
  spacing-1 a spacing-8 (4px a 64px), radius-sm/md/lg (8/16/24px)

TOKENS SEMÂNTICOS (coleção "semantic")
  color-action-primary → slate-600
  color-action-emergency → jade-700 (verde, não vermelho)
  color-text-primary → slate-900

TIPOGRAFIA (family: 'Source Sans 3')
  heading: 24/32, weight 700 | body: 16/24, weight 400
  Contraste mínimo testado: 7.2:1 (acima do mínimo WCAG AA de 4.5:1)

COMPONENTES
  Átomos: Button (primary/secondary/ghost/emergency × sm/md/lg), Input/Text, Icon
  Moléculas: Form-Field, List-Item, Alert-Banner
  Organismos: App-Header, Bottom-Nav, Report-Card

Touch targets: mínimo 24x24px (WCAG 2.5.8); Button "sm" com 44x44px via padding.

Próximo passo: aguardando aprovação antes de Joana iniciar os fluxos de UX.
```

## Quality Criteria

- [ ] Tokens primitivos e semânticos estão claramente separados e nenhum
      componente usa valor hardcoded.
- [ ] Todos os pares de cor de texto/fundo documentados atingem o contraste
      mínimo WCAG AA, com o valor numérico registrado.
- [ ] Componentes seguem nomenclatura atômica consistente (ex.:
      `Atoms/Button/Primary`).
- [ ] Touch targets mínimos (24x24px) estão confirmados para todo componente
      interativo.

## Veto Conditions

Reject and redo if ANY are true:
1. Algum componente usa valor de cor/espaçamento/tipografia hardcoded em vez de
   referenciar um token.
2. Qualquer combinação de cor de texto/fundo na paleta final não atinge o
   contraste mínimo WCAG AA documentado.
3. O design system foi iniciado sem a identidade visual ter sido aprovada no
   checkpoint anterior.
