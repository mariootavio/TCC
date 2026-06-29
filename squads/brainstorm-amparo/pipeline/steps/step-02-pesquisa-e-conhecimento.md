---
execution: subagent
agent: sofia-sabedoria
inputFile: squads/brainstorm-amparo/output/foco-brainstorm.md
outputFile: squads/brainstorm-amparo/pipeline/data/research-brief.md
model_tier: powerful
---

# Step 2: Pesquisa e Conhecimento

## Context Loading

Load these files before executing:
- `squads/brainstorm-amparo/output/foco-brainstorm.md` — o foco do brainstorm
  e o recorte de benchmarking definidos pelo usuário no checkpoint anterior.
- `_opensquad/_memory/company.md` — contexto do projeto Amparo (problema
  central, solução, público-alvo, tom de voz).
- `squads/tcc-documentacao/pipeline/data/research-brief.md` — dados de
  violência doméstica, legislação e benchmarking já levantados pela squad
  irmã, reutilizáveis sem repesquisa.
- `squads/brainstorm-amparo/pipeline/data/domain-framework.md` — framework
  operacional consolidado (MoSCoW, Kano, RICE, checklist DFV) usado pela
  squad inteira, para calibrar o que será relevante para Bruno e Carla nas
  etapas seguintes.
- `squads/brainstorm-amparo/pipeline/data/quality-criteria.md` — critérios de
  qualidade que o brief de conhecimento final precisa atender.
- Outputs relevantes de outras squads (ex.: `squads/design-ux-ui-amparo/`), se
  existirem, para mapear funcionalidades e fluxos já definidos.

## Instructions

### Process

1. Ler o foco do brainstorm e o recorte de benchmarking definidos pelo usuário
   e reafirmar mentalmente o escopo antes de iniciar qualquer leitura ou
   busca — nunca pesquisar fora do recorte sem necessidade.
2. Executar as três tasks do agente em sequência:
   `estudar-projeto-amparo.md` (conhecimento interno do projeto),
   `pesquisar-benchmarking-seguranca.md` (conhecimento externo/benchmarking,
   usando as skills `web_search` e `web_fetch` conforme o recorte escolhido),
   e finalmente `compilar-brief-conhecimento.md` (compilação final).
3. Para o conhecimento interno, reutilizar sempre que possível os dados já
   levantados pela squad tcc-documentacao, mantendo fonte e nível de confiança
   originais — nunca repesquisar do zero.
4. Para o conhecimento externo, garantir que toda funcionalidade de
   benchmarking listada tenha um gap ou limitação documentada junto — nunca
   apenas o ponto forte.
5. Identificar e registrar explicitamente os gaps de mercado como "espaço em
   branco" — no mínimo 2 oportunidades concretas — e escrever a recomendação
   final apontando quais gaps merecem prioridade nesta rodada.
6. Compilar o brief de conhecimento final no formato padrão (Conhecimento
   Interno, Conhecimento Externo/Benchmarking, Gaps de Mercado, Recomendação)
   e salvá-lo em `squads/brainstorm-amparo/pipeline/data/research-brief.md`,
   sobrescrevendo o conteúdo placeholder gerado na criação da squad.

## Output Format

The output MUST follow this exact structure:
```
BRIEF DE CONHECIMENTO — AMPARO
Foco desta rodada: {foco recebido no checkpoint}
Preparado em: {YYYY-MM-DD}

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CONHECIMENTO INTERNO DO PROJETO

{funcionalidades já existentes/planejadas, com origem}
{tom de voz}
{dados-chave já levantados pela squad tcc-documentacao, com fonte e confiança}

CONHECIMENTO EXTERNO — BENCHMARKING

{tabela: App | Funcionalidade-chave | Gap documentado}

GAPS DE MERCADO (ESPAÇO EM BRANCO)

{lista numerada de gaps, com fonte e confiança quando aplicável}

RECOMENDAÇÃO PARA O BRAINSTORM

{1-2 frases apontando quais gaps priorizar nesta rodada}
```

## Output Example

```
BRIEF DE CONHECIMENTO — AMPARO
Foco desta rodada: Funcionalidades de rede de apoio e prevenção
Preparado em: 2026-06-26

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CONHECIMENTO INTERNO DO PROJETO

Funcionalidades já definidas (company.md / squads de design, se
executadas): botão de emergência com acionamento discreto, cofre de
documentação segura, rede de apoio pessoal (contatos de confiança),
acesso a profissionais (psicólogos/assistência jurídica parceira).
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

## Veto Conditions

Reject and redo if ANY of these are true:
1. Alguma funcionalidade de benchmarking aparece sem gap/limitação
   documentado.
2. A seção de Gaps de Mercado está ausente ou tem menos de 2 oportunidades
   concretas.

## Quality Criteria

- [ ] O conhecimento interno do projeto está presente e atualizado antes de
      qualquer recomendação externa.
- [ ] Nenhum dado já levantado pela squad tcc-documentacao foi repetido com
      fonte diferente sem necessidade.
- [ ] A recomendação final referencia explicitamente pelo menos um gap
      identificado nas seções anteriores.
