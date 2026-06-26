---
task: "Compilar Research Brief"
order: 4
input: |
  - dados_estatisticos: Output da task pesquisar-dados-violencia-domestica.md
  - legislacao_aplicavel: Output da task pesquisar-legislacao.md
  - apps_similares: Output da task pesquisar-benchmarking-apps.md
  - gaps_literatura: Output da task pesquisar-benchmarking-apps.md
output: |
  - research_brief: Documento Markdown consolidado no formato padrão (Key Findings, Legislação, Benchmarking, Sources, Gaps, Recomendações)
---

# Compilar Research Brief

Consolida todos os achados das três tasks anteriores (dados, legislação,
benchmarking) no formato padrão de research brief, com tabela de fontes,
níveis de confiança e recomendações diretas para a argumentação do TCC.

## Process

1. Reunir os outputs das três tasks de pesquisa (dados, legislação,
   benchmarking) e organizá-los nas seções padrão: Key Findings, Legislação
   Aplicável, Benchmarking, Sources, Gaps, Recomendações.
2. Construir a tabela consolidada de Sources, atribuindo a cada fonte um
   tipo (Oficial/Institucional, Legal, Acadêmico, Imprensa especializada) e
   uma nota de relevância de 1 a 10.
3. Revisar se algum dado-chave entre as três tasks apresenta contradição não
   resolvida — se houver, mover para uma seção explícita de "Contradições
   Identificadas" em vez de omitir.
4. Escrever a seção de Recomendações para a Argumentação do TCC: 2-4
   recomendações concretas que conectam os achados pesquisados a possíveis
   teses do trabalho (ex.: usar a subnotificação como argumento central).
5. Escrever a seção de Gaps da Pesquisa, incluindo qualquer ausência de dado
   relevante identificada durante as três tasks anteriores.
6. Revisar o brief completo contra o checklist de qualidade (todas as seções
   presentes, toda afirmação com fonte e confiança) antes de salvar o arquivo
   final em `squads/tcc-documentacao/pipeline/data/research-brief.md`.

## Output Format

```yaml
research_brief:
  tema: "Tema da pesquisa conforme o checkpoint"
  recorte_temporal: "Período coberto"
  preparado_em: "YYYY-MM-DD"
  key_findings: [...]
  legislacao_aplicavel: [...]
  benchmarking: [...]
  sources: [...]
  gaps: [...]
  recomendacoes: [...]
```

## Output Example

> Use como referência de qualidade, não como template rígido. Ver
> `pipeline/data/research-brief.md` para o exemplo completo de referência.

```
RESEARCH BRIEF
Tema: Violência doméstica contra mulheres no Brasil — dados, legislação e benchmarking
Recorte temporal: Dados mais recentes disponíveis (2024-2026)
Preparado em: 2026-06-26

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

KEY FINDINGS — DADOS E ESTATÍSTICAS

1. Em 2025, 1.568 mulheres foram vítimas de feminicídio no Brasil...
   Confiança: ALTA | Fonte: FBSP, 2026 | Acessado em: 2026-06-26

LEGISLAÇÃO APLICÁVEL

- Lei 11.340/2006 (Lei Maria da Penha)...
- Lei 14.022/2020...

BENCHMARKING — APPS SIMILARES

| App | Origem | Diferencial | Gap conhecido |
|---|---|---|---|
| PenhaS | Brasil | Tecnologia + curadoria humana | Acionamento manual |

SOURCES

| # | Fonte | Tipo | Relevância | Data |
|---|---|---|---|---|
| 1 | FBSP | Oficial | 9/10 | 2026 |

RECOMENDAÇÕES PARA A ARGUMENTAÇÃO DO TCC

1. Usar a subnotificação de 61% como argumento central da justificativa.

GAPS DA PESQUISA

- Não há série estatística oficial sobre efetividade de apps de denúncia.
```

## Quality Criteria

- [ ] O brief contém todas as seções padrão (Key Findings, Legislação
      Aplicável, Benchmarking, Sources, Gaps, Recomendações).
- [ ] Toda fonte na tabela Sources tem tipo e nota de relevância atribuídos.
- [ ] A seção de Recomendações conecta achados específicos a possíveis teses
      do TCC, não generalidades.

## Veto Conditions

Reject and redo if ANY are true:
1. Alguma das seções padrão do research brief está ausente.
2. Uma contradição identificada nas tasks anteriores foi omitida em vez de
   registrada explicitamente na seção apropriada.
