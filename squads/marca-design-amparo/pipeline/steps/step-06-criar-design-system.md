---
execution: inline
agent: tomas-tokens
inputFile: squads/marca-design-amparo/output/identidade-visual.md
outputFile: squads/marca-design-amparo/output/design-system.md
---

# Step 6: Criar Design System

## Context Loading

Load these files before executing:
- `squads/marca-design-amparo/output/identidade-visual.md` — identidade
  visual aprovada no checkpoint Step 5 (paleta hex, tipografia, lógica de
  símbolo, justificativas)
- `squads/marca-design-amparo/pipeline/data/research-brief.md` — seção 4
  (Design Systems — Atomic Design e Tokens)
- `squads/marca-design-amparo/pipeline/data/anti-patterns.md` —
  anti-padrões de design system a evitar (hardcoding, nomenclatura
  genérica)

Nota: este step usa `DesignSync` para publicar no MESMO projeto Claude
Design já criado por Flávia no Step 4 — nunca criar um segundo projeto.

## Instructions

### Process

1. Carregar a identidade visual aprovada. Usar `DesignSync`
   `list_projects` (e `get_project` se necessário) para localizar o
   projeto "Amparo — Marca & Design System" já existente — nunca chamar
   `create_project` nesta etapa.
2. Definir tokens primitivos (escalas de cor a partir das cores-base
   aprovadas, escala tipográfica, escala de espaçamento) ANTES de
   qualquer componente. Em seguida, definir tokens semânticos
   referenciando exclusivamente os primitivos (nunca um valor bruto
   direto em um componente).
3. Verificar contraste WCAG AA (4.5:1 texto normal, 3:1 texto grande) em
   cada par semântico relevante de texto/fundo — ajustar o token
   primitivo referenciado antes de seguir, se algum par falhar.
4. Construir componentes na hierarquia atômica: átomos (Button, Input,
   Icon, Tag) → moléculas (Form-Field, List-Item, Alert-Banner) →
   organismos (App-Header, Bottom-Nav, Card) — cada um especificado com os
   tokens semânticos que usa, com nomenclatura consistente (ex.
   `Atoms/Button/Primary`), nunca um nome genérico.
5. Usar `DesignSync` para publicar: escrever localmente os arquivos HTML
   em `squads/marca-design-amparo/_claude-design/design-system/` (tokens e
   componentes), cada um com `<!-- @dsCard group="Design System" -->` (ou
   subgrupo, ex. "Design System / Tokens", "Design System / Componentes")
   na primeira linha; `finalize_plan` com esses paths; `write_files`.
6. Compilar a especificação completa em `output/design-system.md`, e
   parar — o checkpoint Step 7 decide se a squad avança para a revisão de
   Marina.

## Output Format

The output MUST follow this exact structure:
```markdown
# Design System — Amparo

Base: [identidade visual aprovada]
Projeto Claude Design: [nome, localizado via list_projects]
Metodologia: Atomic Design (Brad Frost) + tokens primitivos/semânticos

## Tokens Primitivos
| Token | Valor | Origem |
|---|---|---|
[linhas]

## Tokens Semânticos
| Token | Referencia | Uso |
|---|---|---|
[linhas]

## Contraste Verificado
| Par | Razão | Mínimo aplicável | Resultado |
|---|---|---|---|
[linhas]

## Componentes — Hierarquia Atômica
### Átomos
[lista com tokens usados]
### Moléculas
[lista com tokens usados]
### Organismos
[lista com tokens usados]

## Publicação no Claude Design
[arquivos publicados e grupo/categoria]

## Próximo Passo
Aguardando aprovação no checkpoint Step 7 antes da revisão de Marina Marca.
```

## Output Example

```markdown
# Design System — Amparo

Base: Identidade Visual "Porto Seguro" (aprovada em checkpoint Step 5)
Projeto Claude Design: "Amparo — Marca & Design System" (localizado via
list_projects, já existente)
Metodologia: Atomic Design (Brad Frost) + tokens primitivos/semânticos

## Tokens Primitivos
| Token | Valor | Origem |
|---|---|---|
| slate-50 | #F4F2F7 | Neutro claro da identidade aprovada |
| slate-600 | #5B6B8C | Azul-ardósia primário da identidade aprovada |
| slate-900 | #2B2D3A | Neutro escuro da identidade aprovada |
| terracotta-500 | #B97A56 | Acento da identidade aprovada |

## Tokens Semânticos
| Token | Referencia | Uso |
|---|---|---|
| color-bg-default | slate-50 | Fundo padrão de tela |
| color-action-primary | slate-600 | Botões e links de ação primária |
| color-action-emergency | terracotta-500 | Ação de emergência (nunca vermelho) |
| color-text-primary | slate-900 | Texto principal |

## Contraste Verificado
| Par | Razão | Mínimo aplicável | Resultado |
|---|---|---|---|
| color-text-primary sobre color-bg-default | 12.6:1 | 4.5:1 | Aprovado |
| Branco sobre color-action-primary | 4.6:1 | 4.5:1 | Aprovado |
| Branco sobre color-action-emergency | 3.9:1 | 4.5:1 (texto normal) | REPROVADO — ajustar para terracotta-600 |

## Componentes — Hierarquia Atômica
### Átomos
Atoms/Button/Primary (color-action-primary), Atoms/Button/Emergency
(color-action-emergency), Atoms/Input/Text, Atoms/Icon (24x24), Atoms/Tag.
### Moléculas
Molecules/Form-Field, Molecules/List-Item, Molecules/Alert-Banner.
### Organismos
Organisms/App-Header, Organisms/Bottom-Nav, Organisms/Card.

## Publicação no Claude Design
design-system/tokens-cor.html, design-system/tokens-tipografia-espacamento.html,
design-system/atomos-button-input-icon.html,
design-system/moleculas-form-list-alert.html,
design-system/organismos-header-nav-card.html (grupo "Design System").

## Próximo Passo
Aguardando aprovação no checkpoint Step 7 antes da revisão de Marina Marca.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Algum componente especificado usa um valor de cor/tipografia/
   espaçamento direto (hardcoded) em vez de um token nomeado.
2. Um segundo projeto Claude Design foi criado em vez de localizar o
   projeto já existente criado por Flávia.

## Quality Criteria

- [ ] Todo token semântico referencia exatamente um token primitivo
      nomeado.
- [ ] Cada par semântico relevante de cor texto/fundo tem contraste
      verificado e documentado contra o mínimo WCAG AA aplicável.
- [ ] Componentes estão organizados na hierarquia atômica com nomenclatura
      consistente, sem nome genérico.
- [ ] A paleta final usa no máximo 5-6 cores-base, com escalas derivadas
      via tokens.
