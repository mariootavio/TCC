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
  estrutura de navegação a respeitar em cada fluxo.
- `squads/fluxos-uxui-amparo/output/padroes-seguranca-discricao.md`
  (Daniela) — padrões de segurança/discrição a aplicar dentro de cada fluxo.
- backlog mais recente de `squads/brainstorm-amparo/output/.../ideias-brainstorm.md`
  e RF-CORE do `research-brief.md` dessa squad — ancoragem obrigatória de
  todo fluxo.
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
6. Compilar `output/fluxos-ux.md`, com um fluxo por jornada, ancoragem ao
   backlog, heurísticas nomeadas, e caminhos de erro mapeados.

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
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Algum fluxo foi desenhado sem citar o RF-CORE ou ideia do backlog que
   implementa.
2. Algum fluxo crítico não tem caminho de erro mapeado com destino definido.

## Quality Criteria

- [ ] Todo fluxo cita explicitamente sua ancoragem ao backlog priorizado.
- [ ] Todo fluxo crítico tem caminho de erro/interrupção mapeado.
- [ ] Toda decisão de fluxo cita a heurística de Nielsen aplicada.
- [ ] Nenhum fluxo contradiz um padrão de segurança/discrição de Daniela.
