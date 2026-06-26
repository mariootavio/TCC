---
task: "Pesquisar Benchmarking de Apps"
order: 3
input: |
  - foco_pesquisa: Conteúdo de squads/tcc-documentacao/output/research-focus.md
  - legislacao_aplicavel: Achados da task pesquisar-legislacao.md (para identificar dependências jurídicas de cada solução)
output: |
  - apps_similares: Tabela com app, origem, diferencial e gap conhecido
  - gaps_literatura: Lista de limitações documentadas em revisões acadêmicas do campo
---

# Pesquisar Benchmarking de Apps

Identifica apps e soluções similares ao Amparo (nacionais e internacionais),
suas funcionalidades, diferenciais e gaps documentados na literatura, sempre
registrando tanto o que cada solução faz bem quanto sua limitação conhecida.

## Process

1. Buscar apps brasileiros de proteção/denúncia de violência doméstica (ex.:
   PenhaS, Botão do Pânico estadual), documentando funcionalidades principais
   e a instituição responsável.
2. Buscar apps internacionais equivalentes (ex.: Circle of 6, bSafe),
   documentando seu diferencial de UX ou funcionalidade central.
3. Buscar revisões sistemáticas acadêmicas sobre apps de prevenção/proteção à
   violência doméstica (ex.: bases PMC, MDPI, Scielo) que documentem
   limitações recorrentes do campo (ex.: dependência de acionamento manual,
   vulnerabilidade de armazenamento).
4. Para cada app, registrar explicitamente o gap ou limitação conhecida,
   sempre que a fonte permitir — isso alimenta diretamente os achados de
   lacuna que sustentam a contribuição do Amparo.
5. Verificar se algum app depende de pré-requisito jurídico (ex.: medida
   protetiva prévia) cruzando com os achados da task de legislação.

## Output Format

```yaml
apps_similares:
  - app: "Nome do app"
    origem: "País/instituição"
    diferencial: "O que faz de diferente/bem"
    gap_conhecido: "Limitação documentada"
    fonte: "URL"
gaps_literatura:
  - gap: "Descrição da limitação recorrente"
    fonte: "Revisão/estudo de origem"
    amostra: "Tamanho da amostra estudada, se disponível"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
BENCHMARKING — APPS SIMILARES

| App | Origem | Diferencial | Gap conhecido |
|---|---|---|---|
| PenhaS | Brasil (Instituto AzMina) | Combina tecnologia + curadoria humana (voluntárias) | Depende de acionamento manual da vítima |
| Circle of 6 | EUA | UX de 2 toques, mensagens sociais discretas | Sem integração com legislação brasileira (LMP/MPU) |
| bSafe | Noruega/internacional | Evidência forense (vídeo+geo com timestamp) | Armazenamento local de provas é vulnerável |
| Botão do Pânico estadual (PR, AM) | Brasil (estadual) | Acionamento direto da PM com geolocalização | Depende de liberação judicial prévia |

GAPS IDENTIFICADOS NA LITERATURA (revisão sistemática MDPI/PMC, 2023 — 621
apps mapeados, 136 revisados em profundidade, publicados entre 2012-2022)

- Falta de automação: alertas dependem de acionamento manual da vítima, sem
  mecanismos de detecção automática de risco.
- Dependência de conectividade: soluções falham sem internet/sinal de rede.
- Armazenamento local de provas é vulnerável caso o agressor tenha acesso
  físico ao celular da vítima.
- Medo de o agressor descobrir o app é barreira de adoção citada
  amplamente como obstáculo de uso real.
```

## Quality Criteria

- [ ] Toda solução listada tem ao menos um diferencial e um gap conhecido
      documentados.
- [ ] Gaps da literatura acadêmica citam a fonte (revisão/estudo) e, quando
      disponível, o tamanho da amostra analisada.
- [ ] Dependências jurídicas de cada solução (ex.: necessidade de medida
      protetiva prévia) estão sinalizadas quando aplicável.

## Veto Conditions

Reject and redo if ANY are true:
1. Um app é listado sem gap conhecido nem ressalva sobre ausência de gap
   documentado na fonte consultada.
2. Um gap da literatura é citado sem referência à fonte/estudo de origem.
