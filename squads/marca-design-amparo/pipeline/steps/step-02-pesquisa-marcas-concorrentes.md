---
execution: subagent
agent: renata-referencia
inputFile: squads/marca-design-amparo/output/brief-design.md
outputFile: squads/marca-design-amparo/output/pesquisa-marcas-concorrentes.md
---

# Step 2: Pesquisa de Marcas e Concorrentes

## Context Loading

Load these files before executing:
- `squads/marca-design-amparo/output/brief-design.md` — brief de design
  aprovado no checkpoint Step 1
- `_opensquad/_memory/company.md` — contexto do projeto Amparo

Nota: este é um levantamento leve de referências de design, não uma
pesquisa acadêmica — sem exigência de fonte + nível de confiança em cada
item (isso fica para a pesquisa de cor do Step 3). Objetivo: dar
repertório visual real a Flávia antes de ela criar a identidade.

## Instructions

### Process

1. Usar `web_search`/`web_fetch` para olhar rapidamente 3-4 concorrentes
   diretos (apps/plataformas de proteção ou denúncia de violência
   doméstica, Brasil ou internacional) e 2-3 referências adjacentes
   (apps de segurança pessoal ou bem-estar com identidade visual forte).
2. Também levantar 2-3 marcas de **qualquer setor** conhecidas por um
   logotipo-símbolo forte (não um wordmark) — referência de execução,
   não de categoria.
3. Para cada marca: anotar em 1-2 linhas o tipo de logotipo (símbolo /
   wordmark / combinação), a paleta observada, e uma impressão rápida
   (o que funciona, o que não serve de referência para o Amparo).
4. Fechar com uma recomendação direta para Flávia: reforçar que o logo
   do Amparo deve ser um símbolo/ícone chamativo — nunca um wordmark
   simples — citando 1-2 exemplos do levantamento que sustentam isso.
5. Compilar em `output/pesquisa-marcas-concorrentes.md`. Sem decisão de
   identidade fechada — é repertório para Flávia usar no Step 5.

## Output Format

```markdown
# Pesquisa de Marcas e Concorrentes — Amparo

## Concorrentes diretos e adjacentes
- **[Marca]** — [símbolo/wordmark/combinação], paleta [cores], [impressão rápida]
- **[Marca]** — ...

## Referências de logotipo-símbolo (outros setores)
- **[Marca]** — [o que o símbolo faz bem], [relevância para o Amparo]

## Recomendação para Flávia
[reforço direto de que o logo precisa ser símbolo/ícone, com 1-2 exemplos]
```

## Output Example

```markdown
# Marcas e Concorrentes — Amparo

## Concorrentes diretos e adjacentes
- **PenhaS (Instituto AzMina)** — símbolo (megafone) + wordmark, roxo/
  branco/rosa-magenta. Símbolo comunica "voz", mas roxo é clichê do
  setor no Brasil — evitar como cor dominante única.
- **bSafe** — símbolo (escudo) + wordmark, azul/branco. Escudo é
  visualmente óbvio demais, sem sutileza.
- **Calm** — símbolo (espiral orgânica), azul-petróleo/branco. Ícone
  abstrato funciona muito bem em tamanho pequeno de app.

## Referências de logotipo-símbolo (outros setores)
- **Airbnb** — símbolo abstrato ("Bélo") sem texto, reconhecível em
  favicon. Prova que forma abstrata carrega sentido emocional sem
  literalidade — caminho para "acolhimento" sem clichê.

## Recomendação para Flávia
Concorrentes de peso (Calm) e referência fora do setor (Airbnb) confirmam:
símbolo próprio > wordmark puro, principalmente pensando em ícone de app
pequeno. Gerar direções centradas em símbolo/monograma, nunca uma opção
que seja só o nome "Amparo" estilizado.
```

## Quality Criteria

- [ ] Pelo menos 5 marcas reais levantadas no total (concorrentes +
      referências de símbolo).
- [ ] Cada marca tem o tipo de logotipo identificado explicitamente.
- [ ] A recomendação final reforça claramente a exigência de símbolo/
      ícone, não wordmark.
