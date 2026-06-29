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
- `squads/fluxos-uxui-amparo/pipeline/data/domain-framework.md` — papel de
  Iara na cadeia de agentes e critérios de classificação estrutural.

## Instructions

### Process

1. Localizar o arquivo mais recente de `ideias-brainstorm.md` (run mais
   recente, versão mais alta) e ler as RF-CORE do `research-brief.md` da
   squad `brainstorm-amparo` — esta é a fonte real e única do backlog a
   mapear, nunca uma lista inventada.
2. Classificar cada funcionalidade (RF-CORE + ideias priorizadas) em
   exatamente uma categoria: Navegação Principal, Ação Global, ou Ação
   Secundária/Contextual, com justificativa explícita para cada
   classificação.
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
5. Mais — agrupa Ideia 11 (biblioteca de direitos) e Ideia 10 (avaliação
   de risco), evitando exceder 5 itens.

AÇÕES SECUNDÁRIAS/CONTEXTUAIS
1. Anexar evidência — contextual dentro de Documentação (RF-CORE-04).
2. Confirmar recebimento de alerta — contextual dentro de Rede de Apoio
   (RF-CORE-05).

LACUNAS IDENTIFICADAS (sem funcionalidade correspondente no backlog)
1. Onboarding padrão (sem QR code): o backlog cobre apenas onboarding via
   QR code em pontos de acolhimento (Ideia 17) — sinalizado para decisão
   do usuário, não preenchido nesta arquitetura.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Alguma funcionalidade mapeada não existe no backlog real de
   `brainstorm-amparo` (RF-CORE ou ideia priorizada).
2. A bottom nav excede 5 itens sem agrupamento/justificativa explícita.

## Quality Criteria

- [ ] Toda funcionalidade do backlog aparece classificada em exatamente uma
      categoria estrutural.
- [ ] Nenhuma funcionalidade inventada fora do backlog real.
- [ ] Navegação principal não excede 5 itens sem agrupamento justificado.
- [ ] Lacunas identificadas estão em seção separada, sem preenchimento por
      funcionalidade inventada.
