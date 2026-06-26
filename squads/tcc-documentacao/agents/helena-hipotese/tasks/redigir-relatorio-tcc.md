---
task: "Redigir Relatório do TCC"
order: 2
input: |
  - referencial_teorico: Output da task estruturar-referencial-teorico.md
  - research_brief: Conteúdo de squads/tcc-documentacao/pipeline/data/research-brief.md
  - company_context: Contexto do projeto Amparo (_opensquad/_memory/company.md)
output: |
  - relatorio_tcc: Documento Markdown completo (introdução, justificativa, problema, objetivos, referencial teórico, metodologia, desenvolvimento, considerações finais, referências) salvo em squads/tcc-documentacao/output/relatorio-tcc.md
---

# Redigir Relatório do TCC

Redige o relatório estruturado completo (introdução, justificativa,
problema, objetivos, desenvolvimento, considerações finais) seguindo a
estrutura ABNT NBR 14724:2024, com base no referencial teórico já estruturado
e no research brief aprovado.

## Process

1. Construir e compartilhar o outline do relatório antes de redigir o texto
   completo: introdução (tema, justificativa, problema, objetivos,
   metodologia) → desenvolvimento (referencial teórico, metodologia
   detalhada, resultados/discussão) → considerações finais.
2. Redigir a introdução conectando os dados estatísticos do research brief
   numa progressão lógica que culmine no problema de pesquisa — evitar
   abertura genérica sem dado concreto.
3. Redigir o problema de pesquisa com recorte específico e verificável,
   evitando enunciados amplos demais.
4. Redigir os objetivos (geral e específicos) usando verbos de ação
   mensuráveis (desenvolver, avaliar, comparar, propor) — cada objetivo
   específico deve ter correspondência planejada com uma seção dos
   resultados.
5. Incorporar o referencial teórico já estruturado na seção de
   desenvolvimento, mantendo a atribuição autor-data em toda afirmação.
6. Redigir as considerações finais retomando explicitamente o problema de
   pesquisa e cada objetivo específico, sem introduzir conteúdo novo.
7. Revisar o documento completo: parágrafos com no máximo 4-5 frases,
   subtítulos a cada 200-300 palavras, jargão definido na primeira menção, e
   lista de referências completa em NBR 6023:2025.
8. Salvar o relatório completo em
   `squads/tcc-documentacao/output/relatorio-tcc.md`.

## Output Format

```yaml
relatorio_tcc:
  secoes:
    - "1 Introdução"
    - "1.1 Justificativa"
    - "1.2 Problema de Pesquisa"
    - "1.3 Objetivos"
    - "2 Referencial Teórico"
    - "3 Metodologia"
    - "4 Desenvolvimento / Resultados"
    - "5 Considerações Finais"
    - "Referências"
  arquivo_saida: "squads/tcc-documentacao/output/relatorio-tcc.md"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

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
b) Identificar as lacunas funcionais presentes nas soluções similares já
   disponíveis;
c) Especificar e desenvolver as funcionalidades centrais do Amparo com base
   nas lacunas identificadas.

5 CONSIDERAÇÕES FINAIS

Este trabalho partiu do problema de pesquisa sobre como reduzir as
barreiras de acesso à proteção para mulheres em situação de violência
doméstica. O objetivo geral foi cumprido por meio do desenvolvimento do
Amparo, que endereça diretamente as lacunas identificadas no referencial
teórico...
```

## Quality Criteria

- [ ] O outline foi compartilhado e validado antes da redação do texto
      completo.
- [ ] Todo objetivo específico usa verbo de ação mensurável e corresponde a
      uma seção dos resultados.
- [ ] Nenhum parágrafo excede 5 frases; nenhuma seção excede 300 palavras
      sem subtítulo.
- [ ] As considerações finais retomam o problema e os objetivos sem
      conteúdo novo.

## Veto Conditions

Reject and redo if ANY are true:
1. O texto completo foi redigido sem outline previamente compartilhado.
2. Algum objetivo específico usa verbo intangível (entender, saber, conhecer)
   sem correspondência verificável nos resultados.
