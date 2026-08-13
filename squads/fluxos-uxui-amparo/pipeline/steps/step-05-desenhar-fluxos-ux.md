---
execution: inline
agent: joana-jornada
inputFile: squads/fluxos-uxui-amparo/output/padroes-seguranca-discricao.md
outputFile: squads/fluxos-uxui-amparo/output/fluxos-ux.md
---

# Step 5: Desenhar Fluxos de UX

## Context Loading

Load these files before executing:
- `squads/fluxos-uxui-amparo/output/arquitetura-informacao.md` (Iara) —
  estrutura de navegação a respeitar em cada fluxo, incluindo a seção
  "Camada Transversal — Classificação de Risco (RF-CORE-06)".
- `squads/fluxos-uxui-amparo/output/padroes-seguranca-discricao.md`
  (Daniela) — padrões de segurança/discrição a aplicar dentro de cada fluxo.
- backlog mais recente de `squads/brainstorm-amparo/output/.../ideias-brainstorm.md`
  e RF-CORE do `research-brief.md` dessa squad — ancoragem obrigatória de
  todo fluxo.
- `_opensquad/_memory/company.md` — seção "Classificação de Risco (IA/ML) —
  RF-CORE-06", com as ações de sistema exatas por nível (BAIXO/MÉDIO/ALTO).
- `squads/fluxos-uxui-amparo/output/design-system-figma.md` (Caio) —
  componentes já existentes, referenciáveis na descrição do fluxo.

## Instructions

### Process

1. Ler a arquitetura de informação de Iara e os padrões de segurança de
   Daniela por completo antes de iniciar qualquer fluxo.
2. Ler o backlog mais recente do brainstorm e as RF-CORE para confirmar a
   ancoragem de cada fluxo a ser desenhado — nenhum fluxo sem essa
   referência.
3. Para cada jornada crítica (acionar emergência, registrar
   denúncia/evidência, ativar modo discreto, contatar rede de apoio, e
   demais jornadas priorizadas), desenhar a sequência completa do caminho
   feliz, citando a heurística de Nielsen aplicada em cada decisão relevante.
4. Mapear ao menos um caminho de erro/exceção (falha de rede, cancelamento,
   interrupção abrupta) em todo fluxo crítico, com destino definido.
5. Indicar explicitamente, dentro de cada fluxo, os pontos de verificação de
   segurança onde os padrões de Daniela se aplicam.
6. Para todo fluxo que a arquitetura de Iara sinalizou como afetado pela
   camada transversal RF-CORE-06, desenhar as três variações de
   comportamento (BAIXO/MÉDIO/ALTO) como subseção do fluxo, citando a ação
   de sistema exata de company.md — nunca permitindo que o nível de risco
   bloqueie ou atrase o acionamento manual de emergência (RF-CORE-01).
7. Compilar `output/fluxos-ux.md`, com um fluxo por jornada, ancoragem ao
   backlog, heurísticas nomeadas, caminhos de erro mapeados, e variações por
   nível de risco onde aplicável.

## Output Format

The output MUST follow this exact structure:
```
FLUXO: {NOME DO FLUXO}
Ancoragem: {RF-CORE-XX e/ou Ideia N, score RICE}
Classificação: {Fluxo crítico / Fluxo padrão}

CAMINHO FELIZ
{N}. {passo} — Heurística de Nielsen {número} — {nome}: {justificativa}

CAMINHO DE ERRO: {NOME DO CENÁRIO DE ERRO}
{N}. {passo}
Ponto de verificação de segurança: {referência ao padrão de Daniela}

VARIAÇÃO POR NÍVEL DE RISCO (RF-CORE-06, se aplicável ao fluxo)
- BAIXO: {ação de sistema de company.md}
- MÉDIO: {ação de sistema de company.md}
- ALTO: {ação de sistema de company.md}
```

## Output Example

```
FLUXO: ACIONAMENTO DE EMERGÊNCIA (BOTÃO DO PÂNICO/SOS)
Ancoragem: RF-CORE-01.
Classificação: Fluxo crítico.

CAMINHO FELIZ
1. Usuária aciona o botão de emergência (ação global) — 1 toque, mesmo
   com tela bloqueada. Heurística de Nielsen 1 — Visibilidade do status
   do sistema: feedback imediato confirma o acionamento.
2. App envia localização em tempo real à rede de guardiões (RF-CORE-05) —
   notificação neutra, conforme Padrão 2 de Daniela.
3. Guardiões confirmam recebimento — status atualizado em tempo real.

CAMINHO DE ERRO: SEM CONEXÃO DE DADOS
1. App detecta ausência de conexão ao tentar enviar localização.
2. Fallback via SMS/USSD com dados mínimos (Ideia 8 do backlog, RICE
   3,75) — SMS auto-excluído após confirmação de entrega.
Ponto de verificação de segurança: saída rápida (Padrão 1 de Daniela)
permanece acessível durante toda a tentativa de envio.

VARIAÇÃO POR NÍVEL DE RISCO (RF-CORE-06)
- BAIXO/MÉDIO: nenhuma alteração no acionamento em si.
- ALTO: passo 2 prioriza o envio à rede de guardiões (menor timeout de
  retry), conforme "mecanismos de emergência priorizados" de company.md —
  o acionamento nunca é bloqueado ou atrasado pelo nível de risco.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Algum fluxo foi desenhado sem citar o RF-CORE ou ideia do backlog que
   implementa.
2. Algum fluxo crítico não tem caminho de erro mapeado com destino definido.
3. Algum fluxo/tela sinalizado por Iara como afetado por RF-CORE-06 não tem
   as três variações (BAIXO/MÉDIO/ALTO) desenhadas, ou o nível de risco
   bloqueia/atrasa o acionamento manual de emergência.

## Quality Criteria

- [ ] Todo fluxo cita explicitamente sua ancoragem ao backlog priorizado.
- [ ] Todo fluxo crítico tem caminho de erro/interrupção mapeado.
- [ ] Toda decisão de fluxo cita a heurística de Nielsen aplicada.
- [ ] Nenhum fluxo contradiz um padrão de segurança/discrição de Daniela.
- [ ] Todo fluxo/tela sinalizado por Iara como afetado por RF-CORE-06 tem as
      três variações desenhadas, citando a ação de sistema exata de
      company.md, sem bloquear o acionamento manual de emergência.
