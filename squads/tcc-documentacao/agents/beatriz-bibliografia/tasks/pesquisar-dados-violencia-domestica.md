---
task: "Pesquisar Dados de Violência Doméstica"
order: 1
input: |
  - foco_pesquisa: Conteúdo de squads/tcc-documentacao/output/research-focus.md (tema/recorte definido pelo usuário no checkpoint)
  - company_context: Contexto do projeto Amparo (_opensquad/_memory/company.md)
output: |
  - dados_estatisticos: Lista de achados estatísticos com fonte, URL, data de acesso e nível de confiança
  - contradicoes: Lista de divergências identificadas entre fontes, se houver
---

# Pesquisar Dados de Violência Doméstica

Busca estatísticas oficiais sobre violência doméstica contra mulheres no
Brasil — feminicídio, subnotificação, perfil de vítimas/agressores — em
fontes como FBSP, DataSenado, IPEA e ONU Mulheres, cruzando cada dado-chave
contra pelo menos uma segunda fonte independente antes de atribuir confiança.

## Process

1. Reler o foco de pesquisa do checkpoint e restated mentalmente o recorte
   (tema + período) antes de iniciar qualquer busca — nunca assumir o recorte.
2. Buscar em fontes oficiais priorizadas (FBSP, DataSenado/Senado, Ministério
   da Justiça, IPEA, ONU Mulheres) por estatísticas de feminicídio,
   subnotificação e perfil de vítimas/agressores, coletando 2-3 fontes de
   qualidade.
3. Para cada dado-chave coletado, buscar uma segunda fonte independente que
   confirme ou contradiga o valor — registrar o resultado do cruzamento.
4. Atribuir nível de confiança a cada achado: ALTA (3+ fontes concordam),
   MÉDIA (2 fontes), BAIXA (fonte única ou dados conflitantes).
5. Registrar URL completa e data de acesso de cada fonte usada.
6. Se houver contradição entre fontes (ex.: divergência de números entre
   Datafolha e DataSenado), registrar ambas as posições explicitamente, sem
   escolher um lado silenciosamente.

## Output Format

```yaml
dados_estatisticos:
  - achado: "Descrição do dado estatístico"
    valor: "Número ou métrica específica"
    confianca: "ALTA | MÉDIA | BAIXA"
    fonte: "Nome da instituição/publicação"
    url: "URL completa"
    acessado_em: "YYYY-MM-DD"
contradicoes:
  - descricao: "Divergência identificada entre fontes X e Y"
    fonte_a: "Valor e fonte A"
    fonte_b: "Valor e fonte B"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
DADOS ESTATÍSTICOS — VIOLÊNCIA DOMÉSTICA NO BRASIL

1. Em 2025, 1.568 mulheres foram vítimas de feminicídio no Brasil, novo
   recorde histórico, alta de 4,7% em relação a 2024 (1.492 vítimas). Desde a
   tipificação do crime em 2015, ao menos 13.703 mulheres já foram mortas por
   essa razão no país.
   Confiança: ALTA
   Fonte: 20º Anuário Brasileiro de Segurança Pública (FBSP, 2026)
   URL: https://dossies.agenciapatriciagalvao.org.br/dados-e-fontes/pesquisa/19o-anuario-brasileiro-de-seguranca-publica-fbsp-2025/
   Acessado em: 2026-06-26

2. Estudo do Observatório da Mulher contra a Violência (Senado) estima
   subnotificação de 61% no registro de violência contra a mulher — 6 em
   cada 10 vítimas não procuram a delegacia.
   Confiança: ALTA
   Fonte: DataSenado / Câmara dos Deputados
   URL: https://www.camara.leg.br/noticias/1038979-estudo-do-senado-aponta-subnotificacao-de-61-no-registro-de-violencia-contra-mulher/
   Acessado em: 2026-06-26

3. Cerca de 64-66% dos feminicídios ocorrem dentro da própria residência da
   vítima, e 8 em cada 10 são cometidos por companheiro ou ex-companheiro.
   Confiança: ALTA
   Fonte: Nota Técnica FBSP — Dia da Mulher 2026
   Acessado em: 2026-06-26

CONTRADIÇÕES IDENTIFICADAS

- Nenhuma divergência relevante encontrada entre as fontes consultadas nesta
  rodada; os três achados acima são corroborados por pelo menos duas fontes
  institucionais independentes cada.
```

## Quality Criteria

- [ ] Todo dado estatístico tem fonte, URL e data de acesso registrados.
- [ ] Achados de confiança ALTA têm pelo menos 2 fontes independentes
      corroborando o valor.
- [ ] Contradições entre fontes, quando existirem, estão documentadas com
      ambas as posições e evidências.

## Veto Conditions

Reject and redo if ANY are true:
1. Algum dado estatístico aparece sem URL de fonte ou sem data de acesso.
2. Um achado recebeu confiança ALTA com base em uma única fonte.
