---
execution: inline
agent: iara-informacao
inputFile: squads/fluxos-uxui-amparo/output/design-system-figma.md
outputFile: squads/fluxos-uxui-amparo/output/arquitetura-informacao.md
---

# Step 3: Mapear Arquitetura de Informação

## Context Loading

Load these files before executing:
- `squads/fluxos-uxui-amparo/output/design-system-figma.md` — inventário de
  componentes de navegação já reconstruídos por Caio (bottom nav, FAB etc.).
- `squads/brainstorm-amparo/output/{run mais recente}/v{versão mais alta}/ideias-brainstorm.md` —
  backlog real de ideias priorizadas por RICE da squad `brainstorm-amparo`.
- `squads/brainstorm-amparo/pipeline/data/research-brief.md` — RF-CORE-01 a
  RF-CORE-05, requisitos centrais definidos pelo product owner.
- `_opensquad/_memory/company.md` — RF-CORE-06 (classificação de risco por
  IA/ML), seções "Funcionalidades Core (RF-CORE) — Confirmadas" e
  "Classificação de Risco (IA/ML)".
- `squads/fluxos-uxui-amparo/pipeline/data/domain-framework.md` — papel de
  Iara na cadeia de agentes e critérios de classificação estrutural.

## Instructions

### Process

1. Localizar o arquivo mais recente de `ideias-brainstorm.md` (run mais
   recente, versão mais alta) e ler as RF-CORE do `research-brief.md` da
   squad `brainstorm-amparo` — esta é a fonte real e única do backlog a
   mapear, nunca uma lista inventada.
2. Classificar cada funcionalidade (RF-CORE + ideias priorizadas) em
   exatamente uma categoria: Navegação Principal, Ação Global, Ação
   Secundária/Contextual, ou Camada Transversal (RF-CORE-06 — classificação
   de risco, que modula outras funcionalidades sem ser um destino de
   navegação próprio; listar explicitamente cada tela/fluxo já classificado
   que precisa refletir o nível de risco), com justificativa explícita para
   cada classificação.
3. Agrupar funcionalidades relacionadas em até 5 itens de navegação
   principal, evitando uma bottom nav sobrecarregada — consolidar
   funcionalidades de baixo RICE/uso pouco frequente sob agrupamentos como
   "Mais", quando necessário.
4. Identificar e listar separadamente qualquer lacuna — jornada que parece
   necessária para a missão do produto, mas sem funcionalidade
   correspondente documentada no backlog — sem propor solução, apenas
   sinalizando para decisão humana.
5. Compilar `output/arquitetura-informacao.md` com a hierarquia completa,
   justificativas e a seção de lacunas identificadas.

## Output Format

The output MUST follow this exact structure:
```
ARQUITETURA DE INFORMAÇÃO — AMPARO
Fonte: {arquivo ideias-brainstorm.md, run/versão} + {research-brief.md, RF-CORE}

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

AÇÕES GLOBAIS (acesso instantâneo, de qualquer tela)
{N}. {Nome} — {RF-CORE-XX/Ideia}. Justificativa: {racional}.

NAVEGAÇÃO PRINCIPAL (bottom nav)
{N}. {Nome} — {fonte}. {agrupamentos, se houver}

AÇÕES SECUNDÁRIAS/CONTEXTUAIS
{N}. {Nome} — {fonte}. Contexto: {fluxo em que vive}.

CAMADA TRANSVERSAL — CLASSIFICAÇÃO DE RISCO (RF-CORE-06)
{Fonte: company.md. Lista de telas/fluxos já mapeados acima que precisam
refletir o nível de risco BAIXO/MÉDIO/ALTO, citando a ação de sistema exata
de company.md em cada caso.}

LACUNAS IDENTIFICADAS (sem funcionalidade correspondente no backlog)
{N}. {Descrição da lacuna} — sinalizado para decisão do usuário, não preenchido nesta arquitetura.
```

## Output Example

```
ARQUITETURA DE INFORMAÇÃO — AMPARO
Fonte: ideias-brainstorm.md (run 2026-06-27-145210, v1) +
research-brief.md (RF-CORE-01 a RF-CORE-05), squad brainstorm-amparo.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

AÇÕES GLOBAIS (acesso instantâneo, de qualquer tela)
1. Botão do pânico/SOS — RF-CORE-01. Justificativa: pesquisa de UX de
   segurança exige acionamento de emergência em 1-2 toques, de qualquer
   ponto do app.
2. Modo disfarçado / saída rápida — RF-CORE-02. Justificativa: mesma
   exigência de acesso instantâneo.

NAVEGAÇÃO PRINCIPAL (bottom nav)
1. Início — painel resumo.
2. Documentação — RF-CORE-04.
3. Rede de Apoio — RF-CORE-05 + Ideia 6 (perfis de dependentes).
4. Chat de Apoio — RF-CORE-03.
5. Mais — agrupa Ideia 11 (biblioteca de direitos), evitando exceder 5
   itens. Nota: Ideia 10 (avaliação de risco) foi substituída por
   RF-CORE-06, ver camada transversal abaixo.

AÇÕES SECUNDÁRIAS/CONTEXTUAIS
1. Anexar evidência — contextual dentro de Documentação (RF-CORE-04).
2. Confirmar recebimento de alerta — contextual dentro de Rede de Apoio
   (RF-CORE-05).

CAMADA TRANSVERSAL — CLASSIFICAÇÃO DE RISCO (RF-CORE-06)
1. Início: BAIXO = monitoramento discreto + info educativa; MÉDIO = alerta
   discreto pré-configurado + recursos de apoio; ALTO = prioriza mecanismos
   de emergência.
2. Documentação (RF-CORE-04): ALTO aciona proteção reforçada de evidências.

LACUNAS IDENTIFICADAS (sem funcionalidade correspondente no backlog)
1. Onboarding padrão (sem QR code): o backlog cobre apenas onboarding via
   QR code em pontos de acolhimento (Ideia 17) — sinalizado para decisão
   do usuário, não preenchido nesta arquitetura.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Alguma funcionalidade mapeada não existe no backlog real de
   `brainstorm-amparo` (RF-CORE ou ideia priorizada) nem em company.md
   (RF-CORE-06).
2. A bottom nav excede 5 itens sem agrupamento/justificativa explícita.
3. RF-CORE-06 foi classificada como item de bottom nav/ação global/ação
   secundária isolada em vez de Camada Transversal.

## Quality Criteria

- [ ] Toda funcionalidade do backlog aparece classificada em exatamente uma
      categoria estrutural.
- [ ] Nenhuma funcionalidade inventada fora do backlog real.
- [ ] Navegação principal não excede 5 itens sem agrupamento justificado.
- [ ] Lacunas identificadas estão em seção separada, sem preenchimento por
      funcionalidade inventada.
- [ ] RF-CORE-06 documentada como Camada Transversal, com a lista explícita
      de telas/fluxos afetados e as ações de sistema de company.md.
