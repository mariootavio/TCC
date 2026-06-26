---
type: checkpoint
outputFile: squads/tcc-documentacao/output/research-focus.md
---

# Step 1: Foco da Pesquisa

Este é o primeiro checkpoint do pipeline. Antes de iniciar qualquer pesquisa,
pergunte ao usuário qual é o foco desta rodada de pesquisa para o TCC do
Amparo.

Perguntas sugeridas:
- Qual subtema você quer priorizar nesta rodada: dados/estatísticas,
  legislação, benchmarking de apps, ou uma pesquisa geral cobrindo os três?
- Há algum recorte temporal específico (ex.: apenas dados de 2024-2026) ou
  vale usar os dados mais recentes disponíveis?
- Há alguma lei, app concorrente ou dado específico que você já sabe que
  quer ver coberto no research brief?

A resposta do usuário é salva em
`squads/tcc-documentacao/output/research-focus.md` e usada como `inputFile`
pelo Step 2 (Beatriz Bibliografia).

Se o usuário não tiver preferência, sugira o padrão: pesquisa geral cobrindo
as três frentes (dados, legislação, benchmarking), sem recorte temporal além
de priorizar as fontes mais recentes disponíveis.
