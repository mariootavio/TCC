---
task: "Gerar Ideias de Funcionalidades e Fluxos"
order: 1
input: |
  - research_brief: Conteúdo de squads/brainstorm-amparo/pipeline/data/research-brief.md (brief de conhecimento aprovado de Sofia Sabedoria)
output: |
  - backlog_ideias: Lista estruturada de ideias com descrição, dor/gap, MoSCoW, Kano e nota de diferenciação
  - secao_wont_have: Lista de itens conscientemente excluídos do escopo desta rodada, com justificativa
---

# Gerar Ideias de Funcionalidades e Fluxos

Gera o backlog estruturado de ideias de novas funcionalidades e fluxos para o
Amparo, classificando cada ideia em MoSCoW e Kano, e justificando a ligação de
cada uma com uma dor real ou gap de mercado identificado por Sofia Sabedoria.

## Process

1. Ler o brief de conhecimento aprovado de Sofia Sabedoria por completo antes
   de gerar qualquer ideia — nunca pular direto para soluções.
2. Para cada gap de mercado e dor documentada no brief, gerar entre 2 e 4
   ideias de funcionalidade ou fluxo que respondam especificamente a ela
   (geração pura, sem autocensura nesta etapa).
3. Classificar cada ideia em MoSCoW (Must/Should/Could/Won't have) com base no
   alinhamento com a missão do Amparo e na presença/ausência de uma dor
   documentada.
4. Classificar cada ideia em Kano (Básica/Performance/Encantadora) para
   garantir equilíbrio entre essencial e diferencial no backlog final.
5. Para cada ideia que se assemelhe a uma funcionalidade já existente em apps
   de benchmarking (ex.: botão de pânico), explicitar o que a torna
   diferenciada — nunca incluir uma ideia idêntica a uma commodity de mercado
   sem diferenciação clara.
6. Estruturar o backlog final com: nome da ideia, descrição, dor/gap que
   resolve, classificação MoSCoW, classificação Kano, e nota de diferenciação
   (se aplicável).
7. Compilar a seção "Won't have" com qualquer ideia ou direção
   conscientemente excluída do escopo desta rodada, com a justificativa.
8. Nunca atribuir prioridade final (RICE) às ideias — essa etapa é
   responsabilidade exclusiva de Carla Critério.

## Output Format

```yaml
backlog_ideias:
  - numero: 1
    nome: "Nome da ideia"
    descricao: "Descrição funcional da ideia"
    dor_gap: "Dor ou gap do brief de Sofia que esta ideia resolve"
    moscow: "Must have | Should have | Could have"
    kano: "Básica | Performance | Encantadora"
    diferenciacao: "Nota explicando o que diferencia de benchmarking, se aplicável"
secao_wont_have:
  - item: "Descrição do item excluído"
    justificativa: "Motivo da exclusão de escopo nesta rodada"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

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

WON'T HAVE (ESCOPO EXCLUÍDO NESTA RODADA)

- Integração com tornozeleira eletrônica do agressor: depende de órgão
  público, inviável para o escopo do TCC.
```

## Quality Criteria

- [ ] Toda ideia gerada cita explicitamente a dor/gap do brief que a originou.
- [ ] Toda ideia tem MoSCoW e Kano preenchidos.
- [ ] Nenhuma ideia duplica funcionalidade de benchmarking sem nota de
      diferenciação.

## Veto Conditions

Reject and redo if ANY are true:
1. Alguma ideia aparece no backlog sem ligação explícita a uma dor ou gap do
   brief de Sofia.
2. A seção "Won't have" está ausente ou vazia, mesmo havendo ideias
   plausíveis fora do escopo desta rodada.
