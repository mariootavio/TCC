---
execution: inline
agent: helena-hipotese
inputFile: squads/tcc-documentacao/pipeline/data/research-brief.md
outputFile: squads/tcc-documentacao/output/relatorio-tcc.md
---

# Step 4: Redação do Relatório do TCC

## Context Loading

Load these files before executing:
- `squads/tcc-documentacao/pipeline/data/research-brief.md` — research brief
  aprovado pelo usuário no checkpoint anterior (Step 3); base factual de toda
  afirmação do relatório.
- `_opensquad/_memory/company.md` — contexto do projeto Amparo (problema,
  solução, público-alvo, tom de voz).
- `squads/tcc-documentacao/pipeline/data/domain-framework.md` — framework
  operacional de redação de Helena Hipótese (estrutura ABNT, ordem de
  construção do outline).
- `squads/tcc-documentacao/pipeline/data/quality-criteria.md` — critérios de
  qualidade do relatório (alinhamento objetivo-resultado, citação
  autor-data, normas ABNT vigentes).

## Instructions

### Process

1. Executar a task `estruturar-referencial-teorico.md`: organizar os achados
   do research brief por subtema (dados, legislação, benchmarking) com
   citação autor-data (NBR 10520:2023).
2. Construir e compartilhar o outline do relatório completo (introdução,
   justificativa, problema de pesquisa, objetivos, referencial teórico,
   metodologia, desenvolvimento, considerações finais) antes de redigir o
   texto integral — validar com o usuário se houver dúvida sobre escopo.
3. Executar a task `redigir-relatorio-tcc.md`: redigir o relatório completo
   seguindo NBR 14724:2024, com objetivos usando verbos de ação mensuráveis e
   considerações finais retomando o problema/objetivos sem conteúdo novo.
4. Salvar o relatório completo em
   `squads/tcc-documentacao/output/relatorio-tcc.md`, incluindo a lista de
   referências em NBR 6023:2025.

## Output Format

The output MUST follow this exact structure:
```
1 INTRODUÇÃO
{parágrafos conectando dados do research brief ao problema}

1.1 Justificativa
{relevância acadêmica e social do tema}

1.2 Problema de Pesquisa
{enunciado específico e verificável}

1.3 Objetivos
1.3.1 Objetivo Geral
{verbo de ação mensurável}
1.3.2 Objetivos Específicos
a) ...
b) ...

2 REFERENCIAL TEÓRICO
2.1 {subtema 1 — dados/estatísticas}
2.2 {subtema 2 — legislação}
2.3 {subtema 3 — benchmarking}

3 METODOLOGIA
{tipo de pesquisa, abordagem, etapas}

4 DESENVOLVIMENTO / RESULTADOS
{correspondência direta com cada objetivo específico}

5 CONSIDERAÇÕES FINAIS
{retomada do problema e objetivos, sem conteúdo novo}

REFERÊNCIAS
{lista NBR 6023:2025}
```

## Output Example

```
1 INTRODUÇÃO

A violência doméstica contra mulheres no Brasil permanece como um dos
problemas sociais mais persistentes e subnotificados do país. Segundo
estudo do Observatório da Mulher contra a Violência, vinculado ao Senado
Federal, estima-se que 61% das mulheres vítimas de violência doméstica não
procuram a delegacia para registrar ocorrência (DATASENADO, 2025).

1.2 Problema de Pesquisa

Diante do exposto, este trabalho parte do seguinte problema de pesquisa: de
que forma uma plataforma mobile pode reduzir as barreiras de acesso à
documentação de evidências, à rede de apoio pessoal e à denúncia para
mulheres em situação de violência doméstica no Brasil?

1.3.1 Objetivo Geral

Desenvolver e avaliar uma plataforma mobile (Amparo) que combine
funcionalidades de emergência, documentação segura de evidências, rede de
apoio pessoal e acesso a profissionais.

1.3.2 Objetivos Específicos

a) Analisar os dados estatísticos, o arcabouço legal e as soluções
   tecnológicas existentes relacionados à violência doméstica no Brasil;
b) Identificar as lacunas funcionais presentes nas soluções similares;
c) Especificar e desenvolver as funcionalidades centrais do Amparo.

2.3 Soluções Tecnológicas Existentes

O aplicativo PenhaS, desenvolvido pelo Instituto AzMina, destaca-se por
combinar recursos tecnológicos com curadoria humana (TECHTUDO, 2024)...

5 CONSIDERAÇÕES FINAIS

Este trabalho partiu do problema de pesquisa sobre como reduzir as
barreiras de acesso à proteção para mulheres em situação de violência
doméstica. O objetivo geral foi cumprido por meio do desenvolvimento do
Amparo...
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O texto foi redigido sem outline previamente compartilhado.
2. Alguma afirmação factual no referencial teórico aparece sem atribuição
   autor-data.

## Quality Criteria

- [ ] Todo objetivo específico tem correspondência com uma seção dos
      resultados.
- [ ] Nenhum parágrafo excede 5 frases.
- [ ] A lista de referências tem correspondência 1:1 com as citações no
      texto.
