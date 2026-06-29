---
execution: inline
agent: bruno-brainstorm
inputFile: squads/brainstorm-amparo/pipeline/data/research-brief.md
outputFile: squads/brainstorm-amparo/output/ideias-brainstorm.md
---

# Step 4: Gerar Ideias

## Context Loading

Load these files before executing:
- `squads/brainstorm-amparo/pipeline/data/research-brief.md` — brief de
  conhecimento aprovado de Sofia Sabedoria (Step 2/3): conhecimento interno do
  projeto, benchmarking externo, e gaps de mercado.
- `squads/brainstorm-amparo/pipeline/data/domain-framework.md` — definições
  detalhadas de MoSCoW e Kano (seções 1 e 2), as lentes de classificação que
  Bruno deve aplicar a cada ideia gerada.
- `squads/brainstorm-amparo/pipeline/data/anti-patterns.md` — anti-padrões de
  brainstorm de produto (seção Bruno Brainstorm) a evitar ativamente durante a
  geração.
- `squads/brainstorm-amparo/pipeline/data/output-examples.md` — exemplo
  completo de backlog de ideias (Exemplo 2), usado como referência de
  formato e profundidade.

## Instructions

### Process

1. Ler o brief de conhecimento aprovado de Sofia Sabedoria por completo antes
   de gerar qualquer ideia — nunca pular direto para soluções.
2. Para cada gap de mercado e dor documentada no brief, gerar entre 2 e 4
   ideias de funcionalidade ou fluxo que respondam especificamente a ela,
   seguindo a task `gerar-ideias-funcionalidades-fluxos.md` do agente —
   geração pura, sem autocensura nesta etapa.
3. Classificar cada ideia em MoSCoW e Kano conforme `domain-framework.md`, e
   para toda ideia semelhante a uma funcionalidade de benchmarking, explicitar
   a diferenciação — nunca incluir uma ideia idêntica a uma commodity de
   mercado sem diferenciação clara.
4. Compilar a seção "Won't have" com qualquer direção conscientemente
   excluída do escopo desta rodada, com justificativa, e salvar o backlog
   final em `squads/brainstorm-amparo/output/ideias-brainstorm.md`. Nunca
   atribuir prioridade RICE — essa etapa é exclusiva do Step 5 (Carla
   Critério).

## Output Format

The output MUST follow this exact structure:
```
BACKLOG DE IDEIAS — BRAINSTORM AMPARO
Foco desta rodada: {foco recebido no checkpoint}
Baseado no brief de conhecimento de Sofia Sabedoria ({data})

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

{N}. {NOME DA IDEIA EM CAIXA ALTA}
   Descrição: {descrição funcional}
   Dor/gap que resolve: {referência explícita ao brief de Sofia}
   MoSCoW: {Must have | Should have | Could have}
   Kano: {Básica | Performance | Encantadora}
   Diferenciação: {nota, se aplicável a benchmarking}

(repetir para cada ideia gerada)

WON'T HAVE (ESCOPO EXCLUÍDO NESTA RODADA)

- {item excluído}: {justificativa}
```

## Output Example

```
BACKLOG DE IDEIAS — BRAINSTORM AMPARO
Foco desta rodada: Funcionalidades de rede de apoio e prevenção
Baseado no brief de conhecimento de Sofia Sabedoria (2026-06-26)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. ALERTA SILENCIOSO POR PADRÃO DE COMPORTAMENTO
   Descrição: monitoramento opcional de padrões de uso do celular (ex.:
   buscas repetidas por "delegacia da mulher", quedas abruptas de
   localização compartilhada) que sugere à usuária, de forma discreta,
   ativar o plano de segurança — sem acionar terceiros automaticamente.
   Dor/gap que resolve: gap de mercado #1 do brief (nenhum app revisado
   usa IA/sinais comportamentais para alertas proativos).
   MoSCoW: Should have
   Kano: Encantadora (delighter)
   Diferenciação: nenhum app de benchmarking pesquisado oferece isso;
   não é commodity de mercado.

2. CONFIRMAÇÃO ANTI-FALSO-POSITIVO NO BOTÃO DE EMERGÊNCIA
   Descrição: ao acionar o botão de emergência, um cancelamento
   silencioso de 5 segundos (gesto discreto, não um pop-up visível)
   evita disparo acidental sem expor a usuária a uma tela óbvia.
   Dor/gap que resolve: gap de mercado #2 (falta de mecanismo
   anti-falso-positivo padronizado).
   MoSCoW: Must have
   Kano: Básica (esperada em qualquer app de emergência sério)
   Diferenciação: bSafe e Circle of 6 não documentam esse mecanismo.

3. REDE DE APOIO COM PAPÉIS DEFINIDOS
   Descrição: ao montar a rede de apoio, a usuária define um papel para
   cada contato (ex.: "pode buscar provas", "pode acionar polícia", "só
   para conversar").
   Dor/gap que resolve: falta de granularidade observada no Circle of 6.
   MoSCoW: Could have
   Kano: Performance
   Diferenciação: adiciona granularidade ausente no benchmarking.

WON'T HAVE (ESCOPO EXCLUÍDO NESTA RODADA)

- Integração com tornozeleira eletrônica do agressor: depende de órgão
  público, inviável para o escopo do TCC.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Alguma ideia aparece no backlog sem ligação explícita a uma dor ou gap do
   brief de Sofia Sabedoria.
2. A seção "Won't have" está ausente, mesmo havendo direções plausíveis fora
   do escopo desta rodada.

## Quality Criteria

- [ ] Toda ideia tem classificação MoSCoW e Kano preenchidas.
- [ ] Nenhuma ideia duplica uma funcionalidade de benchmarking sem nota de
      diferenciação.
- [ ] Nenhuma prioridade RICE foi atribuída nesta etapa.
