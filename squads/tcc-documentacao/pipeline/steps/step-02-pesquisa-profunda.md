---
execution: subagent
agent: beatriz-bibliografia
inputFile: squads/tcc-documentacao/output/research-focus.md
outputFile: squads/tcc-documentacao/pipeline/data/research-brief.md
model_tier: powerful
---

# Step 2: Pesquisa Profunda

## Context Loading

Load these files before executing:
- `squads/tcc-documentacao/output/research-focus.md` — o foco de pesquisa
  definido pelo usuário no checkpoint anterior (subtema priorizado, recorte
  temporal, itens específicos a cobrir).
- `_opensquad/_memory/company.md` — contexto do projeto Amparo (problema
  central, solução, público-alvo) para calibrar a relevância dos achados.
- `squads/tcc-documentacao/pipeline/data/domain-framework.md` — framework
  operacional de pesquisa de Beatriz Bibliografia (mapeamento de fontes por
  subtema, critérios de confiança).
- `squads/tcc-documentacao/pipeline/data/quality-criteria.md` — critérios de
  qualidade que o research brief final precisa atender.

## Instructions

### Process

1. Ler o foco de pesquisa e restated o recorte (subtema + período) antes de
   iniciar qualquer busca — nunca pesquisar fora do recorte sem necessidade.
2. Executar as quatro tasks do agente em sequência:
   `pesquisar-dados-violencia-domestica.md`, `pesquisar-legislacao.md`,
   `pesquisar-benchmarking-apps.md`, e finalmente
   `compilar-research-brief.md`, usando as skills `web_search` e
   `web_fetch` para todas as buscas.
3. Para cada subtema, coletar 2-3 fontes de qualidade, cruzar dados-chave
   contra pelo menos uma segunda fonte independente, e atribuir nível de
   confiança (ALTA/MÉDIA/BAIXA) a cada achado conforme os critérios do
   domain-framework.
4. Compilar o research brief final no formato padrão (Key Findings,
   Legislação Aplicável, Benchmarking, Sources, Gaps, Recomendações) e
   salvá-lo em `squads/tcc-documentacao/pipeline/data/research-brief.md`.

## Output Format

The output MUST follow this exact structure:
```
RESEARCH BRIEF
Tema: {tema da pesquisa}
Recorte temporal: {período coberto}
Preparado em: {YYYY-MM-DD}

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

KEY FINDINGS — DADOS E ESTATÍSTICAS

{lista numerada de achados, cada um com Confiança, Fonte, URL, Acessado em}

LEGISLAÇÃO APLICÁVEL

{lista de normas com status de vigência}

BENCHMARKING — APPS SIMILARES

{tabela: App | Origem | Diferencial | Gap conhecido}

GAPS IDENTIFICADOS NA LITERATURA

{lista de limitações documentadas em revisões acadêmicas}

SOURCES

{tabela: # | Fonte | Tipo | Relevância | Data}

RECOMENDAÇÕES PARA A ARGUMENTAÇÃO DO TCC

{lista numerada de recomendações}

GAPS DA PESQUISA

{lista de ausências de dados identificadas}
```

## Output Example

```
RESEARCH BRIEF
Tema: Violência doméstica contra mulheres no Brasil — dados, legislação e benchmarking
Recorte temporal: Dados mais recentes disponíveis (2024-2026)
Preparado em: 2026-06-26

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

KEY FINDINGS — DADOS E ESTATÍSTICAS

1. Em 2025, 1.568 mulheres foram vítimas de feminicídio no Brasil, novo
   recorde histórico, alta de 4,7% em relação a 2024 (1.492 vítimas).
   Confiança: ALTA
   Fonte: 20º Anuário Brasileiro de Segurança Pública (FBSP, 2026)
   URL: https://dossies.agenciapatriciagalvao.org.br/dados-e-fontes/pesquisa/19o-anuario-brasileiro-de-seguranca-publica-fbsp-2025/
   Acessado em: 2026-06-26

2. Estudo do Observatório da Mulher contra a Violência (Senado) estima
   subnotificação de 61% no registro de violência contra a mulher.
   Confiança: ALTA
   Fonte: DataSenado / Câmara dos Deputados
   Acessado em: 2026-06-26

LEGISLAÇÃO APLICÁVEL

- Lei 11.340/2006 (Lei Maria da Penha): cria mecanismos de proteção e as
  medidas protetivas de urgência (MPU). Vigente, com 18+ alterações desde
  2006 — verificado em 2026-06-26.
- Lei 14.022/2020: prazo de 48h para encaminhamento de denúncias do Ligue
  180.

BENCHMARKING — APPS SIMILARES

| App | Origem | Diferencial | Gap conhecido |
|---|---|---|---|
| PenhaS | Brasil (AzMina) | Tecnologia + curadoria humana | Acionamento manual |

GAPS IDENTIFICADOS NA LITERATURA

- Armazenamento local de provas é vulnerável (MDPI/PMC, 2023, 136 apps
  revisados).

SOURCES

| # | Fonte | Tipo | Relevância | Data |
|---|---|---|---|---|
| 1 | FBSP | Oficial | 9/10 | 2026 |
| 2 | DataSenado | Oficial | 9/10 | 2025 |

RECOMENDAÇÕES PARA A ARGUMENTAÇÃO DO TCC

1. Usar a subnotificação de 61% como argumento central da justificativa.

GAPS DA PESQUISA

- Não há série estatística oficial sobre efetividade de apps de denúncia.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Algum achado-chave aparece sem URL de fonte e data de acesso.
2. Alguma seção padrão do research brief (Key Findings, Legislação,
   Benchmarking, Sources, Gaps, Recomendações) está ausente.

## Quality Criteria

- [ ] Todo achado de confiança ALTA é corroborado por pelo menos 2 fontes
      independentes.
- [ ] A seção de legislação cita apenas normas com vigência verificada.
- [ ] A seção de Gaps está preenchida, mesmo que com poucos itens.
