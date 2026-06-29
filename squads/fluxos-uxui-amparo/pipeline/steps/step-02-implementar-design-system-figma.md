---
execution: inline
agent: caio-componentes
inputFile: squads/fluxos-uxui-amparo/output/inputs-selecionados.md
outputFile: squads/fluxos-uxui-amparo/output/design-system-figma.md
---

# Step 2: Implementar Design System no Figma

## Context Loading

Load these files before executing:
- `squads/fluxos-uxui-amparo/output/inputs-selecionados.md` — rodada/projeto
  Claude Design da squad `marca-design-amparo` confirmado no checkpoint
  Step 1, e rodada do backlog de `brainstorm-amparo` (referência cruzada,
  ainda não usada nesta etapa).
- `squads/fluxos-uxui-amparo/pipeline/data/research-brief.md` — seção de
  Acessibilidade Mobile (WCAG 2.2 AA), usada na verificação de contraste.
- `squads/fluxos-uxui-amparo/pipeline/data/domain-framework.md` — visão geral
  do fluxo da squad e papel específico de Caio na cadeia de agentes.

## Instructions

### Process

1. Usar `DesignSync` (`list_projects`, `get_project`, `list_files`,
   `get_file`) para localizar e ler o conteúdo do projeto Claude Design
   confirmado no Step 1, e ler os arquivos `identidade-visual.md` e
   `design-system.md` publicados pela squad `marca-design-amparo` no caminho
   confirmado.
2. Carregar a skill `figma:figma-use` e, se o arquivo Figma do projeto não
   existir ainda, carregar `figma:figma-create-new-file` para criá-lo.
3. Carregar `figma:figma-generate-library` para construir, nesta ordem:
   Figma Variables (tokens primitivos → semânticos), fundações de cor/
   tipografia/espaçamento, e componentes atômicos com Variant Properties —
   seguindo exatamente a hierarquia documentada pela squad de marca, sem
   reinterpretação visual própria.
4. Carregar `figma:figma-create-design-system-rules` para gerar as regras de
   uso do design system, artefato que Telma vai consumir no Step 7.
5. Verificar cada par de cor texto/fundo do sistema reconstruído contra os
   critérios de contraste WCAG AA (4.5:1 texto normal, 3:1 texto
   grande/componentes UI) já documentados pela squad de marca — reportar
   qualquer discrepância encontrada, nunca corrigir silenciosamente.
6. Registrar qualquer informação genuinamente ausente na especificação (ex.:
   hex code não documentado) como pendência explícita — nunca inventar um
   valor para preencher a lacuna.
7. Compilar `output/design-system-figma.md` com: nome/link do arquivo Figma,
   tabela de tokens reconstruídos com fonte rastreável, componentes
   reconstruídos com Variant Properties, verificação de contraste, e lista de
   pendências.

## Output Format

The output MUST follow this exact structure:
```
DESIGN SYSTEM RECONSTRUÍDO NO FIGMA — AMPARO
Projeto Claude Design de origem: {nome do projeto, squad marca-design-amparo}
Arquivo Figma criado: {nome do arquivo} (link: {link})

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

TOKENS PRIMITIVOS (Figma Variables — coleção "primitives")
| Token | Valor | Fonte |
|---|---|---|

TOKENS SEMÂNTICOS (Figma Variables — coleção "semantic")
| Token | Aponta para | Fonte |
|---|---|---|

VERIFICAÇÃO DE CONTRASTE WCAG AA
- {par texto/fundo}: contraste calculado {X}:1 — {ATENDE/NÃO ATENDE}

COMPONENTES RECONSTRUÍDOS (hierarquia atômica)
- {Átomo/Molécula/Organismo} "{nome}" — Variant Properties: {lista}. Fonte: {arquivo, seção}.

PENDÊNCIAS (informação ausente na fonte)
{lista, ou "Nenhuma pendência identificada nesta rodada."}
```

## Output Example

```
DESIGN SYSTEM RECONSTRUÍDO NO FIGMA — AMPARO
Projeto Claude Design de origem: "Amparo — Identidade Visual" (squad
marca-design-amparo, confirmado no checkpoint Step 1)
Arquivo Figma criado: "Amparo — Design System" (link: figma.com/file/XXXX)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

TOKENS PRIMITIVOS (Figma Variables — coleção "primitives")
| Token | Valor | Fonte |
|---|---|---|
| color/violet/600 | #6D28D9 | design-system.md, seção "Paleta — Cor Primária" |
| font/family/base | "Inter" | identidade-visual.md, seção "Tipografia" |

TOKENS SEMÂNTICOS (Figma Variables — coleção "semantic")
| Token | Aponta para | Fonte |
|---|---|---|
| color/action/primary | color/violet/600 | design-system.md, seção "Tokens Semânticos — Ação" |

VERIFICAÇÃO DE CONTRASTE WCAG AA
- color/text/on-primary (#FAFAFA) sobre color/action/primary (#6D28D9):
  7.1:1 — ATENDE (mínimo 4.5:1).

COMPONENTES RECONSTRUÍDOS (hierarquia atômica)
- Átomo "Botão" — Variant Properties: Tipo (Primário/Secundário/Texto),
  Estado (Padrão/Pressionado/Desabilitado). Fonte: design-system.md,
  seção "Componentes — Botões".

PENDÊNCIAS (informação ausente na fonte)
1. Cor do estado "Erro" do Campo de Texto não documentada em nenhuma
   fonte — aguardando definição da squad marca-design-amparo.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Algum token de cor, tipografia ou espaçamento foi criado como Figma Style
   solto ou valor hardcoded, em vez de Figma Variable.
2. Algum token ou componente foi reconstruído sem citar a fonte exata
   (arquivo + seção) de onde veio, ou com um valor inventado para preencher
   uma lacuna de informação.

## Quality Criteria

- [ ] Todo token existe como Figma Variable, com fonte rastreável.
- [ ] Toda pendência por ausência de informação está registrada
      explicitamente, sem valores inventados.
- [ ] Verificação de contraste WCAG AA foi feita para cada par texto/fundo do
      sistema reconstruído.
- [ ] As regras de design system foram geradas via
      `figma:figma-create-design-system-rules`.
