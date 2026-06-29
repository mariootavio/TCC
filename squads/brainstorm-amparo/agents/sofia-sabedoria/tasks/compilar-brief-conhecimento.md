---
task: "Compilar Brief de Conhecimento"
order: 3
input: |
  - conhecimento_interno: Saída da task estudar-projeto-amparo.md (funcionalidades existentes, tom de voz, dados já levantados)
  - conhecimento_externo: Saída da task pesquisar-benchmarking-seguranca.md (apps de referência, gaps de mercado)
output: |
  - research_brief: Documento final em Markdown salvo em squads/brainstorm-amparo/pipeline/data/research-brief.md
---

# Compilar Brief de Conhecimento

Compila o conhecimento interno (projeto) e externo (domínio/benchmarking) em
um único brief de conhecimento estruturado, identificando explicitamente os
"espaços em branco" (gaps) que Bruno Brainstorm pode explorar na geração de
ideias.

## Process

1. Reunir as saídas das duas tasks anteriores: conhecimento interno
   (`estudar-projeto-amparo.md`) e conhecimento externo
   (`pesquisar-benchmarking-seguranca.md`).
2. Montar o documento final seguindo a estrutura padrão: cabeçalho com foco e
   data, seção de Conhecimento Interno, seção de Conhecimento Externo
   (Benchmarking), seção de Gaps de Mercado, e Recomendação para o Brainstorm.
3. Verificar que toda funcionalidade de benchmarking listada tem gap
   documentado, e que a seção de Gaps de Mercado tem no mínimo 2 oportunidades
   concretas — se algum item estiver incompleto, retornar à task correspondente
   antes de finalizar.
4. Escrever a Recomendação para o Brainstorm: 1-2 frases apontando quais gaps
   merecem prioridade de exploração nesta rodada, com base no foco recebido no
   checkpoint.
5. Salvar o documento final em
   `squads/brainstorm-amparo/pipeline/data/research-brief.md`, sobrescrevendo
   o conteúdo placeholder gerado na criação da squad.

## Output Format

```yaml
research_brief:
  foco: "Área de interesse desta rodada (do checkpoint)"
  preparado_em: "YYYY-MM-DD"
  conhecimento_interno:
    funcionalidades_existentes: [...]
    tom_de_voz: "..."
    dados_ja_levantados: [...]
  conhecimento_externo:
    apps_referencia: [...]
  gaps_de_mercado: [...]
  recomendacao: "Texto da recomendação para o brainstorm"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
BRIEF DE CONHECIMENTO — AMPARO
Foco desta rodada: Funcionalidades de rede de apoio e prevenção
Preparado em: 2026-06-26

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CONHECIMENTO INTERNO DO PROJETO

Funcionalidades já definidas: botão de emergência com acionamento
discreto, cofre de documentação segura, rede de apoio pessoal (contatos
de confiança), acesso a profissionais (psicólogos/assistência jurídica
parceira).
Tom de voz: acolhedor, empático, seguro, sem jargão técnico.
Dado-chave já levantado (tcc-documentacao): subnotificação de 61% dos
casos de violência doméstica no Brasil (Fonte: DataSenado, Confiança:
ALTA).

CONHECIMENTO EXTERNO — BENCHMARKING

| App | Funcionalidade-chave | Gap documentado |
|---|---|---|
| bSafe | Follow Me + fake call | Acionamento manual, sem detecção automática |
| Circle of 6 | Círculo de 6 contatos pré-definidos | Sem cofre de evidências |
| Guardiã Maria da Penha/SP Mulher Segura | Cruzamento com tornozeleira do agressor | Depende de integração institucional, não replicável sem órgão público |

GAPS DE MERCADO (ESPAÇO EM BRANCO)

1. Nenhum app revisado usa IA ou sinais comportamentais para alertas
   proativos — todos dependem de acionamento manual.
2. Falta de mecanismo anti-falso-positivo padronizado.
3. Foco quase exclusivo em resposta emergencial, pouca prevenção
   primária.

RECOMENDAÇÃO PARA O BRAINSTORM

Priorizar ideias que explorem os gaps acima, evitando duplicar
funcionalidades já commodity (botão de pânico genérico) sem
diferenciação clara.
```

## Quality Criteria

- [ ] O brief contém as 5 seções padrão: Conhecimento Interno, Conhecimento
      Externo, Gaps de Mercado, Recomendação.
- [ ] Nenhuma funcionalidade de benchmarking aparece sem gap correspondente.
- [ ] A seção de Gaps de Mercado tem no mínimo 2 itens concretos.
- [ ] O arquivo final foi salvo em
      `squads/brainstorm-amparo/pipeline/data/research-brief.md`.

## Veto Conditions

Reject and redo if ANY are true:
1. O brief final omite a seção de Conhecimento Interno do projeto.
2. A Recomendação para o Brainstorm está ausente ou não referencia nenhum gap
   específico identificado nas seções anteriores.
