---
execution: inline
agent: flavia-fonte
inputFile: squads/marca-design-amparo/output/pesquisa-cor-publico.md
outputFile: squads/marca-design-amparo/output/identidade-visual.md
---

# Step 5: Criar Identidade Visual

## Context Loading

Load these files before executing:
- `squads/marca-design-amparo/output/brief-design.md` — brief de design
  aprovado (adjetivos de marca, restrições de cor, nível de discrição)
- `squads/marca-design-amparo/output/pesquisa-marcas-concorrentes.md` —
  repertório de concorrentes e logos-símbolo levantado por Renata (Step
  2) — usar como precedente concreto para a exigência de símbolo
- `squads/marca-design-amparo/output/pesquisa-cor-publico.md` — pesquisa
  calibrada de Renata sobre cor e público específico do Amparo
- `squads/marca-design-amparo/output/referencias-visuais.md` — referências
  visuais do usuário coletadas no checkpoint Step 4
- `_opensquad/_memory/company.md` — contexto do projeto Amparo
- `squads/marca-design-amparo/pipeline/data/research-brief.md` — framework
  de design trauma-informado (seção 1)
- `squads/marca-design-amparo/pipeline/data/anti-patterns.md` —
  anti-padrões de identidade visual a evitar
- `squads/marca-design-amparo/pipeline/data/direcao-imagens-ia.md` —
  diretriz obrigatória para qualquer imagem gerada por IA no card de
  abertura

Nota: este step depende de duas ferramentas/skills nativas do ambiente,
não do catálogo Opensquad — o skill `brandkit` (via Skill tool) e a
ferramenta `DesignSync` (publicação no Claude Design, no PRIMEIRO dos
dois projetos da squad — "Amparo — Marca & Design System"; o segundo
projeto, de apresentação, é criado por Helena no Step 11, só depois do
checkpoint Step 10). Também usa a skill do catálogo Opensquad
`image-ai-generator` (já em `squad.yaml`), opcionalmente, para o card de
abertura.

## Instructions

### Process

1. Carregar o brief, o repertório de marcas/concorrentes de Renata (Step
   2), a pesquisa de cor calibrada de Renata (Step 3) e as referências
   visuais do usuário (se houver). Invocar o skill `brandkit` (via Skill
   tool) e aplicar seu framework estratégico ao Amparo especificamente:
   categoria, audiência (perfil demográfico real trazido por Renata),
   função do produto, promessa emocional, posição cultural, nível de
   confiança exigido, mundo visual, metáfora simbólica candidata e o que
   a marca deve evitar. Nenhum "visual mode" pré-definido do brandkit
   (Dark Security, Light Editorial, etc.) cobre proteção trauma-informada
   sem adaptação — usar a lógica estratégica e os métodos de concepção do
   skill como metodologia, nunca aplicar um modo pronto sem adaptar.
2. Escolher 1-2 métodos de concepção de **símbolo** do brandkit
   (Monograma+Significado, Ação do Produto, Fusão de Metáfora, Espaço
   Negativo, ou Geometria de Construção) e gerar 2-3 direções de
   identidade — todas centradas num símbolo/ícone próprio e chamativo,
   nunca uma direção que seja só o nome "Amparo" estilizado — paleta
   (hex), tipografia de marca e justificativa ligada ao brief E à
   pesquisa de Renata para cada uma.
3. Verificar contraste WCAG AA (4.5:1 texto normal, 3:1 texto grande) em
   cada par de cor candidato antes de finalizar qualquer paleta — ajustar
   ou descartar combinações que não passem.
4. Escrever o card de abertura/contexto (`00-abertura.html`): prosa
   narrativa curta (nome, tagline, problema, solução, promessa, público)
   no tom de voz do Amparo — nunca dado bruto de pesquisa ou estatística.
   Avaliar se uma imagem gerada por IA eleva este card, seguindo
   `direcao-imagens-ia.md` à risca (sujeito preferencial: mulher real
   usando celular, segura e confiante, refletindo o público real de
   Renata — nunca imagética literal de violência, alarme, ou exposição
   do propósito do app); se sim, usar `image-ai-generator` com
   `--mode test` antes de `--mode production` — recurso pontual, nunca
   obrigatório.
5. Se houver ferramenta de geração de imagem disponível, também tentar
   gerar a imagem-conceito de brand-kit board (3x3) do brandkit como
   apoio visual opcional — nunca bloquear a entrega se a ferramenta não
   existir ou falhar.
6. Usar `DesignSync`: (a) `list_projects` para verificar se já existe o
   projeto "Amparo — Marca & Design System" (Projeto 1 da squad); (b) se
   não existir, `create_project` com esse nome; (c) escrever localmente
   os arquivos HTML — o card de abertura e as direções de identidade —
   em `squads/marca-design-amparo/_claude-design/identity/` (o card de
   abertura com `<!-- @dsCard group="Abertura" -->`, as direções com
   `group="Identidade"`); (d) `finalize_plan` declarando esses paths;
   (e) `write_files` com `localPath` apontando para os arquivos escritos.
7. Compilar a especificação completa, incluindo a recomendação final, em
   `output/identidade-visual.md`, e parar — o checkpoint seguinte (Step 6)
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
Projeto: "Amparo — Marca & Design System" (Projeto 1 da squad)
identity/00-abertura.html (grupo "Abertura"), identity/logo-direcao-1.html,
identity/logo-direcao-2.html, identity/logo-direcao-3.html,
identity/paleta-tipografia.html (grupo "Identidade").

## Próximo Passo
Aguardando aprovação no checkpoint antes do design system completo.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Apenas uma direção de identidade é apresentada, sem alternativas reais.
2. Alguma direção usa imagética literal de violência/socorro óbvio, ou
   vermelho/laranja saturado como cor dominante.
3. Alguma direção é apenas o nome "Amparo" estilizado (wordmark), sem
   símbolo/ícone próprio — exigência explícita do usuário, não opcional.

## Quality Criteria

- [ ] No mínimo 2-3 direções de identidade apresentadas, cada uma com
      paleta, tipografia, lógica de símbolo e justificativa.
- [ ] Toda direção tem um símbolo/ícone próprio — nenhuma é apenas o
      nome "Amparo" estilizado sem elemento gráfico.
- [ ] Nenhuma direção expõe o propósito do app de forma literal/óbvia.
- [ ] A recomendação final é explícita e justificada com base no brief E
      na pesquisa de Renata.
- [ ] O projeto Claude Design "Amparo — Marca & Design System" foi
      localizado via `list_projects` antes de qualquer `create_project`,
      e os arquivos publicados têm o comentário
      `<!-- @dsCard group="Abertura" -->` ou `group="Identidade"`.
- [ ] O card de abertura (`00-abertura.html`) apresenta o projeto em
      prosa narrativa, sem dado bruto de pesquisa.
- [ ] Se uma imagem foi gerada por IA, foi validada em `--mode test`
      antes de `--mode production` e não viola as regras trauma-
      informadas.
