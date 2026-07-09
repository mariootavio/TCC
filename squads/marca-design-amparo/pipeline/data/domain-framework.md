# Domain Framework — Marca & Design System Amparo

> Compilação do `Operational Framework` de cada agente desta squad. Este
> documento consolida a metodologia operacional completa: pesquisa de cor e
> público → identidade de marca (brandkit + Claude Design) → design system
> (tokens + componentes, Claude Design) → revisão de marca. Cada agente
> também mantém sua própria cópia detalhada do framework no respectivo
> arquivo `.agent.md`.

## Visão Geral do Fluxo Metodológico

```
Brief de Design (checkpoint)
        ↓
Renata Referência → Pesquisa de Cor e Público (calibrada à demografia
                     real do Amparo, benchmarking de marcas de causas
                     sensíveis)
        ↓ (checkpoint de referências visuais do usuário)
Flávia Fonte      → Identidade Visual (brandkit como framework estratégico
                     + métodos de concepção de logo) — publicada no Claude
                     Design via DesignSync
        ↓ (checkpoint de aprovação)
Tomás Tokens      → Design System (tokens primitivos/semânticos,
                     componentes em hierarquia atômica) — publicado no
                     MESMO projeto Claude Design via DesignSync
        ↓ (checkpoint de aprovação)
Marina Marca      → Revisão estruturada (conformidade trauma-informada,
                     WCAG AA recalculado, consistência de tokens, coerência
                     com o brief)
        ↓ (on_reject volta para Tomás Tokens, Step 7)
Checkpoint de Aprovação Final do Usuário
        ↓
Insumo da squad fluxos-uxui-amparo (reconstrução fiel no Figma)
```

A regra estrutural do domínio é a mesma de qualquer design system maduro:
**fundação antes de construção** — pesquisa calibrada antes de identidade,
identidade aprovada antes de tokens, tokens antes de componentes. A
diferença desta squad para a squad-irmã `design-ux-ui-amparo` é o canal de
publicação: aqui tudo é documentado e publicado no Claude Design via
`DesignSync`, nunca no Figma.

## 1. Framework de Renata Referência (Pesquisadora de Cor e Público)

1. Carregar o brief de design aprovado e o perfil demográfico exato do
   público do Amparo (mulheres negras, 18-44 anos, agressão majoritariamente
   doméstica) — nunca tratar o público como "mulheres" de forma genérica.
2. Pesquisar psicologia de cor e simbolismo calibrada a esse público
   específico via `web_search`/`web_fetch`, buscando ativamente fontes que
   considerem raça/etnia/contexto socioeconômico — não psicologia das
   cores genérica.
3. Fazer benchmarking de identidades visuais REAIS de marcas de causas
   sensíveis (ONGs, apps de proteção), nunca inventar exemplos.
4. Marcar explicitamente todo gap de aplicabilidade da literatura
   internacional ao contexto racial/socioeconômico brasileiro — mesmo gap
   já identificado pela squad tcc-documentacao.
5. Entregar recomendações com fonte e nível de confiança (ALTA/MÉDIA/BAIXA)
   — nunca decidir a identidade final, isso é exclusivo de Flávia.

## 2. Framework de Flávia Fonte (Designer de Identidade Visual)

1. Carregar o brief, a pesquisa de Renata e as referências visuais do
   usuário (checkpoint dedicado) — nunca iniciar sem esses três insumos.
2. Invocar o skill `brandkit` e aplicar seu framework estratégico
   (categoria/audiência/função/promessa emocional/posição cultural/nível
   de confiança/mundo visual/metáfora/o que evitar) ao Amparo
   especificamente — nenhum visual mode pré-definido do brandkit cobre
   proteção trauma-informada sem adaptação.
3. Escolher 1-2 métodos de concepção de logo (Monograma+Significado, Ação
   do Produto, Fusão de Metáfora, Espaço Negativo, Geometria de
   Construção) e gerar 2-3 direções de identidade com paleta, tipografia e
   justificativa ligada ao brief E à pesquisa de Renata.
4. Verificar contraste WCAG AA antes de finalizar qualquer paleta.
5. Publicar via `DesignSync`: `list_projects` → `create_project` (se
   necessário) → `finalize_plan` → `write_files`, com cada HTML carregando
   `<!-- @dsCard group="Identidade Visual" -->`.
6. Tentar gerar a imagem-conceito de brand-kit board do brandkit como apoio
   visual opcional, sem nunca bloquear a entrega por isso.

## 3. Framework de Tomás Tokens (Especialista em Design System)

1. Carregar a identidade visual JÁ APROVADA de Flávia — nunca reinterpretar
   ou alterar decisões de marca já fechadas.
2. Localizar o projeto Claude Design existente via `list_projects`/
   `get_project` — nunca criar um segundo projeto.
3. Definir tokens primitivos (escalas de cor, tipografia, espaçamento)
   ANTES de qualquer componente, depois tokens semânticos referenciando
   exclusivamente os primitivos.
4. Verificar contraste WCAG AA em cada par semântico relevante antes de
   fixar o token.
5. Construir componentes em hierarquia atômica (átomos → moléculas →
   organismos) com nomenclatura consistente, nunca um valor hardcoded.
6. Publicar via `DesignSync` no projeto já existente, com cada HTML
   carregando `<!-- @dsCard group="Design System" -->` (ou subgrupo).

## 4. Framework de Marina Marca (Revisora de Marca e Acessibilidade)

1. Carregar identidade visual, design system, brief e pesquisa de Renata —
   entender o que foi prometido antes de avaliar o que foi entregue.
2. Percorrer 100% das direções de identidade e 100% dos
   tokens/componentes — nunca avaliar por amostragem.
3. Recalcular o contraste WCAG AA de forma independente, nunca aceitar o
   valor de Tomás sem verificação própria.
4. Auditar consistência de tokens e verificar conformidade
   trauma-informada — qualquer violação de discrição/trauma-informado é
   gatilho de rejeição automática, independente da média geral.
5. Pontuar cada critério com justificativa, calcular o veredito conforme a
   tabela de decisão, sempre incluindo ao menos um "Ponto forte:" mesmo em
   rejeição, e apontando localização exata em toda correção obrigatória.

## Princípio Transversal: Ferramentas Nativas do Ambiente como Pré-requisito

Diferente de squads de conteúdo, esta squad depende de ferramentas/skills
nativas do ambiente Claude Code (`DesignSync`, skill `brandkit`) em vez de
skills do catálogo Opensquad. Toda publicação no Claude Design exige
`list_projects` antes de `create_project` (para nunca duplicar o projeto da
squad) e `finalize_plan` antes de `write_files`. Toda criação de identidade
exige a aplicação do framework estratégico do `brandkit`, nunca o uso
direto de um visual mode pré-definido sem adaptação ao contexto trauma-
-informado do Amparo.
