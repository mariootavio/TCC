---
execution: inline
agent: flavia-fonte
inputFile: squads/marca-design-amparo/output/pesquisa-cor-publico.md
outputFile: squads/marca-design-amparo/output/identidade-visual.md
---

# Step 4: Criar Identidade Visual

## Context Loading

Load these files before executing:
- `squads/marca-design-amparo/output/brief-design.md` — brief de design
  aprovado (adjetivos de marca, restrições de cor, nível de discrição)
- `squads/marca-design-amparo/output/pesquisa-cor-publico.md` — pesquisa
  calibrada de Renata sobre cor e público específico do Amparo
- `squads/marca-design-amparo/output/referencias-visuais.md` — referências
  visuais do usuário coletadas no checkpoint Step 3
- `_opensquad/_memory/company.md` — contexto do projeto Amparo
- `squads/marca-design-amparo/pipeline/data/research-brief.md` — framework
  de design trauma-informado (seção 1)
- `squads/marca-design-amparo/pipeline/data/anti-patterns.md` —
  anti-padrões de identidade visual a evitar

Nota: este step depende de duas ferramentas/skills nativas do ambiente,
não do catálogo Opensquad — o skill `brandkit` (via Skill tool) e a
ferramenta `DesignSync` (publicação no Claude Design).

## Instructions

### Process

1. Carregar o brief, a pesquisa de Renata e as referências visuais do
   usuário (se houver). Invocar o skill `brandkit` (via Skill tool) e
   aplicar seu framework estratégico ao Amparo especificamente: categoria,
   audiência (perfil demográfico real trazido por Renata), função do
   produto, promessa emocional, posição cultural, nível de confiança
   exigido, mundo visual, metáfora simbólica candidata e o que a marca
   deve evitar. Nenhum "visual mode" pré-definido do brandkit (Dark
   Security, Light Editorial, etc.) cobre proteção trauma-informada sem
   adaptação — usar a lógica estratégica e os métodos de concepção do
   skill como metodologia, nunca aplicar um modo pronto sem adaptar.
2. Escolher 1-2 métodos de concepção de logo do brandkit (Monograma+
   Significado, Ação do Produto, Fusão de Metáfora, Espaço Negativo, ou
   Geometria de Construção) e gerar 2-3 direções de identidade — paleta
   (hex), tipografia de marca e justificativa ligada ao brief E à
   pesquisa de Renata para cada uma.
3. Verificar contraste WCAG AA (4.5:1 texto normal, 3:1 texto grande) em
   cada par de cor candidato antes de finalizar qualquer paleta — ajustar
   ou descartar combinações que não passem.
4. Usar `DesignSync`: (a) `list_projects` para verificar se já existe um
   projeto "Amparo — Marca & Design System" desta squad; (b) se não
   existir, `create_project`; (c) escrever localmente os arquivos HTML das
   direções em `squads/marca-design-amparo/_claude-design/identity/`
   (cada um com `<!-- @dsCard group="Identidade Visual" -->` na primeira
   linha); (d) `finalize_plan` declarando esses paths; (e) `write_files`
   com `localPath` apontando para os arquivos escritos.
5. Se houver ferramenta de geração de imagem disponível no ambiente,
   tentar gerar a imagem-conceito de brand-kit board (3x3) do brandkit
   como apoio visual opcional — nunca bloquear a entrega se a ferramenta
   não existir.
6. Compilar a especificação completa, incluindo a recomendação final, em
   `output/identidade-visual.md`, e parar — o checkpoint seguinte (Step 5)
   decide se a squad avança.

## Output Format

The output MUST follow this exact structure:
```markdown
# Identidade Visual — Amparo

Brief de origem: [adjetivos do brief]
Pesquisa de base: [síntese da recomendação de Renata usada]
Framework brandkit aplicado: [categoria/audiência/promessa/o que evitar]
Projeto Claude Design: [nome do projeto]

## Direção 1 — "[Nome]" [(recomendada) se aplicável]
Método de concepção: [método(s) do brandkit usado(s)]
Logo: [descrição]
Paleta: Primária [#HEX], Secundária [#HEX], Acento [#HEX]
Tipografia: [família tipográfica]
Contraste verificado: [pares e razões]
Justificativa: [conectada ao brief E à pesquisa de Renata]

## Direção 2 — "[Nome]"
[mesma estrutura, com trade-offs explícitos]

## Direção 3 — "[Nome]" (opcional)
[mesma estrutura]

## Recomendação
[qual direção e por quê]

## Publicação no Claude Design
[arquivos publicados e grupo/categoria]

## Próximo Passo
Aguardando aprovação no checkpoint antes do design system completo.
```

## Output Example

```markdown
# Identidade Visual — Amparo

Brief de origem: acolhedor, seguro, discreto
Pesquisa de base: tons frios calibrados com ressalva de gap racial; tom
terroso/quente não-saturado como hipótese de calibração ao público
específico (pesquisa-cor-publico.md, Renata)
Framework brandkit aplicado: categoria = proteção pessoal
trauma-informada; audiência = mulheres em situação de risco,
majoritariamente negras, 18-44 anos; o que evitar = alarme, clichê de
ONG, imagética de violência
Projeto Claude Design: "Amparo — Marca & Design System"

## Direção 1 — "Porto Seguro" (recomendada)
Método de concepção: Espaço Negativo + Monograma.
Logo: monograma circular com a letra "A" estilizada formando duas curvas
abstratas que se encontram no espaço negativo central — sem realismo,
apenas geometria suave.
Paleta: Primária #5B6B8C, Secundária #8B7FB8, Acento #B97A56 (terracota
suave, calibrado pela hipótese de Renata).
Tipografia: 'Source Sans 3' (humanista, alta legibilidade).
Contraste verificado: #2B2D3A sobre #F4F2F7 = 12.6:1 (AA); branco sobre
#5B6B8C = 4.6:1 (AA texto normal).
Justificativa: tons frios seguem trauma-informed design; acento terracota
responde à hipótese de calibração de Renata; monograma não contém símbolo
óbvio de violência ou socorro.

## Direção 2 — "Abrigo"
Método de concepção: Fusão de Metáfora (folha + mão aberta). Paleta em
tons terrosos + verde-oliva. Mais "natural/orgânico", risco de parecer
genérico.

## Direção 3 — "Constância"
Método de concepção: Geometria de Construção (ondas modulares). Paleta
azul-petróleo + terracota discreto. Estável, porém menos distintiva.

## Recomendação
Direção 1 ("Porto Seguro"), por atender aos 3 adjetivos do brief, à
calibração de Renata e ao requisito de discrição.

## Publicação no Claude Design
identity/logo-direcao-1.html, identity/logo-direcao-2.html,
identity/logo-direcao-3.html, identity/paleta-tipografia.html (grupo
"Identidade Visual").

## Próximo Passo
Aguardando aprovação no checkpoint antes do design system completo.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Apenas uma direção de identidade é apresentada, sem alternativas reais.
2. Alguma direção usa imagética literal de violência/socorro óbvio, ou
   vermelho/laranja saturado como cor dominante.

## Quality Criteria

- [ ] No mínimo 2-3 direções de identidade apresentadas, cada uma com
      paleta, tipografia, lógica de símbolo e justificativa.
- [ ] Nenhuma direção expõe o propósito do app de forma literal/óbvia.
- [ ] A recomendação final é explícita e justificada com base no brief E
      na pesquisa de Renata.
- [ ] O projeto Claude Design foi localizado via `list_projects` antes de
      qualquer `create_project`, e os arquivos publicados têm o comentário
      `<!-- @dsCard group="Identidade Visual" -->`.
