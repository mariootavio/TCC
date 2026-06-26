---
task: "Estruturar Referencial Teórico"
order: 1
input: |
  - research_brief: Conteúdo de squads/tcc-documentacao/pipeline/data/research-brief.md
  - company_context: Contexto do projeto Amparo (_opensquad/_memory/company.md)
output: |
  - referencial_teorico: Texto estruturado por subtema (dados, legislação, benchmarking) com citação autor-data
  - lista_referencias_parcial: Lista preliminar de referências no formato NBR 6023:2025
---

# Estruturar Referencial Teórico

Organiza os achados do research brief em um referencial teórico coerente,
com citação correta (autor-data, NBR 10520:2023) e sem fontes sem autoria
clara — esta é a base conceitual que sustenta o problema de pesquisa do TCC.

## Process

1. Ler o research-brief.md completo e agrupar os achados por subtema: dados e
   estatísticas, legislação aplicável, benchmarking de soluções existentes.
2. Para cada subtema, redigir uma subseção em prosa acadêmica (não lista de
   tópicos), conectando os achados em uma narrativa lógica — nunca apenas
   colar os dados do brief sem síntese.
3. Atribuir cada afirmação factual a uma fonte específica usando o sistema
   autor-data (ex.: "(FBSP, 2026)" ou "Segundo o DataSenado (2025)..."),
   conforme NBR 10520:2023 — nunca incluir afirmação sem atribuição.
4. Ao final da subseção de benchmarking, sintetizar explicitamente a lacuna
   que esses achados revelam, preparando a transição para a justificativa da
   contribuição do Amparo.
5. Compilar a lista preliminar de referências no formato NBR 6023:2025,
   incluindo todas as fontes citadas nas subseções redigidas.
6. Verificar que toda fonte citada no texto aparece na lista de referências e
   vice-versa — nenhuma fonte órfã em qualquer direção.

## Output Format

```yaml
referencial_teorico:
  subsecoes:
    - titulo: "2.X Nome da subseção"
      texto: "Prosa acadêmica com citações autor-data"
lista_referencias_parcial:
  - "SOBRENOME, Nome ou INSTITUIÇÃO. Título. Fonte, ano. Disponível em: URL. Acesso em: data."
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
2.3 Soluções Tecnológicas Existentes para Proteção contra Violência
Doméstica

O campo de aplicativos voltados à prevenção e ao enfrentamento da violência
doméstica já conta com iniciativas relevantes no Brasil e no exterior, cada
uma com enfoques e limitações distintos.

No contexto brasileiro, o aplicativo PenhaS, desenvolvido pelo Instituto
AzMina, destaca-se por combinar recursos tecnológicos com curadoria humana:
a usuária pode acionar um botão de pedido de ajuda que notifica até cinco
contatos de confiança ou a polícia, registrar provas por meio de um
gravador integrado, e acessar atendimento privado diário com profissionais
e voluntárias da organização (TECHTUDO, 2024).

No cenário internacional, o aplicativo Circle of 6 prioriza a simplicidade
extrema de uso: a vítima aciona uma rede de seis contatos de confiança com
apenas dois toques (SWHELPER, 2016).

Uma revisão sistemática internacional, que analisou 621 aplicativos
identificados e revisou em profundidade 136 deles publicados entre 2012 e
2022, identificou limitações recorrentes: a dependência quase exclusiva de
acionamento manual da vítima, sem mecanismos de detecção automática de
risco; e a vulnerabilidade do armazenamento local de evidências (MDPI,
2023).

Essas limitações documentadas na literatura internacional constituem a
lacuna que fundamenta a proposta de desenvolvimento do Amparo.

LISTA DE REFERÊNCIAS (preliminar)

TECHTUDO. PenhaS: app de proteção à mulher recebe nova função. 2024.
Disponível em: [URL]. Acesso em: 26 jun. 2026.
```

## Quality Criteria

- [ ] Toda afirmação factual tem atribuição autor-data explícita.
- [ ] As subseções estão organizadas por subtema (dados, legislação,
      benchmarking), não como lista solta de achados.
- [ ] A lista de referências preliminar tem correspondência 1:1 com as
      citações no texto redigido.

## Veto Conditions

Reject and redo if ANY are true:
1. Alguma afirmação factual aparece sem atribuição autor-data.
2. Uma fonte é citada no texto sem aparecer na lista de referências
   preliminar, ou vice-versa.
