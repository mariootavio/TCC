# Output Examples — Squad Documentação TCC (Amparo)

> Exemplos completos compilados a partir de `artifacts.output_examples` de cada
> agente em `design.yaml`. Servem como referência de qualidade e profundidade
> esperada — não como template rígido a ser copiado literalmente.

## Beatriz Bibliografia — Exemplo de Research Brief (recorte: dados e benchmarking)

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

BENCHMARKING — APPS SIMILARES

| App | Origem | Diferencial | Gap conhecido |
|---|---|---|---|
| PenhaS | Brasil (Instituto AzMina) | Tecnologia + curadoria humana | Acionamento manual |
| Circle of 6 | EUA | UX de 2 toques | Sem integração com LMP brasileira |

SOURCES

| # | Fonte | Tipo | Relevância | Data |
|---|---|---|---|---|
| 1 | Anuário FBSP | Oficial | 9/10 | 2026 |
| 2 | DataSenado | Oficial | 9/10 | 2024-2025 |

RECOMENDAÇÕES PARA A ARGUMENTAÇÃO DO TCC

1. Usar a subnotificação de 61% como argumento central da justificativa.
2. Posicionar o Amparo na lacuna entre apps institucionais e apps de ONG.

GAPS DA PESQUISA

- Não há série estatística oficial brasileira consolidada sobre efetividade
  de apps de denúncia.
```
(Exemplo completo de referência: ver `_build/design.yaml`, artifacts de
`beatriz-bibliografia`, que contém dois research briefs integrais — um geral
e um focado em legislação.)

## Diana Defesa — Exemplo de Tese Argumentativa com Contra-argumento

```
TESE 1: A subnotificação, não a ausência de violência, é a barreira central
a ser endereçada.

Evidência de suporte: Estudo do Observatório da Mulher contra a Violência
(Senado, DataSenado) estima subnotificação de 61% no registro de violência
contra a mulher no Brasil. (Fonte: research-brief.md, Seção "Dados e
Estatísticas", Confiança: ALTA)

Contra-argumento provável da banca: "Se a vítima não denuncia por medo do
agressor, um app não resolve esse medo — por que a solução tecnológica
endereçaria a causa raiz?"

Resposta preparada: O Amparo não substitui o enfrentamento do medo, mas
reduz a fricção e o risco do primeiro passo: documentação segura de provas
sem exposição imediata, rede de apoio pessoal antes da denúncia formal, e
acesso a profissionais para construir um plano de saída gradual.
```

## Helena Hipótese — Exemplo de Trecho de Introdução (TCC)

```
1 INTRODUÇÃO

A violência doméstica contra mulheres no Brasil permanece como um dos
problemas sociais mais persistentes e subnotificados do país. Segundo
estudo do Observatório da Mulher contra a Violência, vinculado ao Senado
Federal, estima-se que 61% das mulheres vítimas de violência doméstica não
procuram a delegacia para registrar ocorrência (DATASENADO, 2025). Esse
dado revela que a lacuna central no combate à violência doméstica não é
apenas a prevenção do ato em si, mas a ausência de canais acessíveis,
seguros e discretos para que a vítima possa buscar ajuda.

1.2 Problema de Pesquisa

Diante do exposto, este trabalho parte do seguinte problema de pesquisa: de
que forma uma plataforma mobile pode reduzir as barreiras de acesso à
documentação de evidências, à rede de apoio pessoal e à denúncia para
mulheres em situação de violência doméstica no Brasil?

1.3.1 Objetivo Geral

Desenvolver e avaliar uma plataforma mobile (Amparo) que combine
funcionalidades de emergência, documentação segura de evidências, rede de
apoio pessoal e acesso a profissionais.
```
(Exemplo completo de referência: ver `_build/design.yaml`, artifacts de
`helena-hipotese`, que contém o trecho integral de Introdução e do
referencial teórico sobre benchmarking.)

## Renata Referência — Exemplo de Veredito de Revisão

```
==============================
 VEREDITO DA REVISÃO: APROVAÇÃO CONDICIONAL
==============================

Conteúdo: Capítulo 1 (Introdução) + Pacote de Argumentação de Defesa
Revisão: 1 de 3

------------------------------
 TABELA DE PONTUAÇÃO
------------------------------
| Critério                          | Nota  | Resumo                        |
|------------------------------------|-------|-------------------------------|
| Conformidade ABNT (citação/refs)  | 8/10  | 1 referência sem ano          |
| Solidez das evidências citadas     | 9/10  | Todos os dados rastreáveis    |
| Qualidade da argumentação de defesa| 6/10  | 1 contra-argumento sem resposta|
------------------------------
 MÉDIA GERAL: 8,0/10
------------------------------

FEEDBACK DETALHADO:

Ponto forte: A Introdução conecta de forma eficaz o dado de subnotificação
com os dados de feminicídio do FBSP.

Mudança obrigatória: Na Tese 3, a resposta ao contra-argumento da banca
está incompleta. Finalizar com base na documentação técnica real do Amparo.

VEREDITO: APROVAÇÃO CONDICIONAL — Conteúdo em patamar alto (8,0/10), mas
a resposta incompleta da Tese 3 deve ser corrigida antes da aprovação final.
```
(Exemplo completo de referência, incluindo um caso de REJEIÇÃO por
inconsistência factual: ver `_build/design.yaml`, artifacts de
`renata-referencia`.)
