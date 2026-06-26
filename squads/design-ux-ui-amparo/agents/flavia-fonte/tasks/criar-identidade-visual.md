---
task: "Criar Identidade Visual"
order: 1
input: |
  - brief_design: Brief de design aprovado no checkpoint anterior (adjetivos de personalidade de marca, restrições de cor, referências visuais) — squads/design-ux-ui-amparo/output/brief-design.md
  - company_context: Contexto do projeto Amparo — _opensquad/_memory/company.md
output: |
  - identidade_visual: Documento com 2-3 direções de logo/identidade, paleta, simbolismo e tipografia de marca, com recomendação justificada — squads/design-ux-ui-amparo/output/identidade-visual.md
---

# Criar Identidade Visual

Cria o logo e a identidade visual de marca do Amparo (paleta inicial, simbolismo,
tipografia de marca) no Figma, com base no brief de design aprovado, aplicando
princípios de design trauma-informado e discrição visual como requisito de
segurança da usuária.

## Process

1. Carregar o brief de design aprovado e o contexto do projeto Amparo
   (`company.md`) — nunca iniciar o design sem esse brief. Extrair os adjetivos
   de personalidade de marca e quaisquer restrições de cor já indicadas.
2. Antes de qualquer chamada à ferramenta `use_figma`, invocar a skill
   `figma:figma-use` (pré-requisito obrigatório deste ambiente). Se o arquivo
   Figma do projeto ainda não existir, invocar primeiro `figma:figma-create-new-file`
   antes de chamar `create_new_file`.
3. Aplicar o framework de design trauma-informado: tons frios/calmantes (azuis,
   verdes, lilás) em vez de vermelho/amarelo de alta energia; simbolismo de
   proteção/acolhimento, nunca imagética literal de violência. Confirmar que o
   nome e o ícone da marca não expõem literalmente o propósito do app.
4. Gerar 2-3 variações reais de direção de logo/identidade no Figma (página
   "01. Identidade Visual"), cada uma com paleta, tipografia e justificativa
   amarrada ao brief de personalidade de marca.
5. Compilar as direções em um documento de apresentação com recomendação
   justificada, e salvar em `output/identidade-visual.md` para o checkpoint de
   aprovação seguinte.

## Output Format

```yaml
identidade_visual:
  preparado_em: "YYYY-MM-DD"
  arquivo_figma: "string — nome do arquivo e página"
  direcoes:
    - nome: "string — nome da direção (ex.: 'Porto Seguro')"
      recomendada: true | false
      logo_descricao: "string"
      paleta:
        primaria: "#HEX — nome da cor"
        secundaria: "#HEX — nome da cor"
        acento: "#HEX — nome da cor"
      tipografia: "string — nome da família tipográfica"
      justificativa: "string — amarrada ao brief e/ou requisito de segurança"
  recomendacao: "string — qual direção e por quê"
  proximo_passo: "string"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
IDENTIDADE VISUAL — AMPARO
Brief de origem: acolhedor, seguro, discreto
Arquivo Figma: Amparo — Marca & Design System (página "01. Identidade Visual")

DIREÇÃO 1 — "Porto Seguro" (recomendada)
Logo: monograma circular com a letra "A" estilizada formando duas mãos curvas
abstratas que se encontram — sem realismo, apenas forma geométrica suave.
Paleta: Primária #5B6B8C (azul-ardósia), Secundária #8B7FB8 (lilás suave),
Acento #2D9D8F (verde-jade).
Tipografia: 'Source Sans 3' (humanista, alta legibilidade).
Justificativa: tons frios seguem design trauma-informado, em contraste com o
vermelho/laranja associado a "alarme" institucional no benchmarking. O
monograma não contém símbolo óbvio de violência ou socorro.

DIREÇÃO 2 — "Abrigo": paleta terrosa + verde-oliva, logo com folha abstrata.
Risco de parecer app de bem-estar genérico.

DIREÇÃO 3 — "Constância": azul-petróleo + dourado discreto. Dourado pode ler
como "premium/financeiro", desviando do tom acolhedor pedido.

RECOMENDAÇÃO: Direção 1, por atender aos 3 adjetivos do brief e ao requisito de
não expor o propósito do app visualmente.

Próximo passo: aguardando aprovação no checkpoint antes do design system completo.
```

## Quality Criteria

- [ ] São apresentadas no mínimo 2 direções reais de identidade, nunca uma
      única opção fechada.
- [ ] Nenhuma direção usa imagética literal de violência ou expõe o propósito
      do app de forma óbvia (sem "SOS", escudo vermelho, cruz).
- [ ] Cada direção tem justificativa escrita amarrada ao brief de personalidade
      de marca ou ao requisito de segurança/discrição.
- [ ] A recomendação final é explícita e justificada, não deixada em aberto.

## Veto Conditions

Reject and redo if ANY are true:
1. Apenas uma direção de identidade é apresentada (sem alternativas reais para
   comparação).
2. Qualquer direção usa vermelho/laranja saturado como cor dominante ou contém
   simbolismo literal de violência/socorro óbvio.
3. A chamada a `use_figma` ou `create_new_file` ocorreu sem carregar a skill
   correspondente do Claude Code primeiro.
