---
task: "Pesquisar Legislação"
order: 2
input: |
  - foco_pesquisa: Conteúdo de squads/tcc-documentacao/output/research-focus.md
  - dados_estatisticos: Achados da task pesquisar-dados-violencia-domestica.md (para contextualizar a relevância de cada norma)
output: |
  - legislacao_aplicavel: Lista de normas com número, ementa resumida, status de vigência e fonte
  - projetos_lei: Lista de PLs em tramitação relevantes ao tema
---

# Pesquisar Legislação

Levanta a Lei Maria da Penha, medidas protetivas, Lei 14.022/2020, a Lei do
Botão do Pânico e projetos de lei recentes sobre tecnologia e proteção a
mulheres, sempre verificando se a redação consultada é a vigente.

## Process

1. Buscar o texto integral da Lei 11.340/2006 (Lei Maria da Penha) na fonte
   oficial (Planalto), verificando se há alterações posteriores à publicação
   original que mudem a redação relevante ao tema da pesquisa.
2. Buscar a Lei 14.022/2020 e a Lei mais recente sobre monitoramento
   eletrônico/"botão do pânico" (ex.: Lei 15.125/2025), confirmando a redação
   vigente em fontes institucionais (Planalto, MPPB, TJAM ou equivalente
   estadual).
3. Buscar projetos de lei em tramitação relacionados a tecnologia e proteção
   a mulheres (ex.: PL 1242/24) na Câmara dos Deputados ou Senado, registrando
   que se trata de projeto, não de lei vigente.
4. Para cada norma, registrar: número da lei, ementa resumida, status
   (vigente/em tramitação), e ao menos um ponto relevante ao tema do Amparo
   (ex.: prazo de resposta, condição de acionamento).
5. Cruzar a leitura da norma com pelo menos uma fonte secundária (notícia
   institucional ou jurídica) quando a redação legal for ambígua ou técnica
   demais para citação direta sem contexto.

## Output Format

```yaml
legislacao_aplicavel:
  - norma: "Lei nº XX.XXX/AAAA"
    ementa: "Resumo de uma frase"
    status: "vigente | alterada | revogada"
    ponto_relevante: "O que importa para o Amparo"
    fonte: "URL oficial"
    acessado_em: "YYYY-MM-DD"
projetos_lei:
  - identificador: "PL XXXX/AA"
    ementa: "Resumo"
    status: "em tramitação"
    fonte: "URL"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
LEGISLAÇÃO APLICÁVEL

- Lei 11.340/2006 (Lei Maria da Penha): cria mecanismos de proteção e as
  medidas protetivas de urgência (MPU). Já sofreu 18+ alterações desde
  2006 — redação vigente confirmada via Planalto em 2026-06-26.
  Fonte: http://www.planalto.gov.br/ccivil_03/_ato2004-2006/2006/lei/l11340.htm

- Lei 14.022/2020: torna o atendimento a vítimas serviço essencial durante
  calamidade pública; prevê canais de comunicação virtual e prazo de 48h
  para encaminhamento de denúncias do Ligue 180.
  Fonte: http://www.planalto.gov.br/ccivil_03/_ato2019-2022/2020/lei/L14022.htm

- Lei 15.125/2025 ("Botão do Pânico"): permite cumulação de MPU com
  monitoramento eletrônico do agressor e dispositivo de alerta de
  aproximação — dependente de autorização judicial prévia em todos os casos
  documentados (MPPB, TJAM).
  Fonte: https://www.mppb.mp.br/index.php/pt/comunicacao/noticias/19-criminal/26611-botao-do-panico-e-lei-maria-da-penha-inovacoes-trazem-mais-protecao-para-mulheres

PROJETOS DE LEI EM TRAMITAÇÃO

- PL 1242/24: prevê que estados disponibilizem app de denúncia com recurso
  de acessibilidade — sinaliza demanda legislativa em curso alinhada à
  proposta do Amparo. Em tramitação, sujeito a alterações até aprovação.
  Fonte: https://www.camara.leg.br/noticias/1057649-projeto-preve-que-estados-disponibilizem-aplicativo-para-denuncia-de-violencia-domestica-com-recurso-de-acessibilidade/
```

## Quality Criteria

- [ ] Toda norma citada tem confirmação de vigência (ou status de
      tramitação) registrada com data de verificação.
- [ ] Projetos de lei são claramente identificados como "em tramitação", nunca
      apresentados como lei vigente.
- [ ] Cada norma tem ao menos um ponto relevante explicitado para o contexto
      do Amparo.

## Veto Conditions

Reject and redo if ANY are true:
1. Uma norma é citada sem verificação de vigência (redação desatualizada
   apresentada como atual).
2. Um projeto de lei em tramitação é apresentado como se fosse lei vigente.
