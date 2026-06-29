---
execution: inline
agent: daniela-discricao
inputFile: squads/fluxos-uxui-amparo/output/arquitetura-informacao.md
outputFile: squads/fluxos-uxui-amparo/output/padroes-seguranca-discricao.md
---

# Step 4: Definir Padrões de Segurança e Discrição

## Context Loading

Load these files before executing:
- `squads/fluxos-uxui-amparo/output/arquitetura-informacao.md` — funcionalidades
  classificadas como ação global (candidatas naturais a padrões de
  discrição transversais).
- `squads/fluxos-uxui-amparo/pipeline/data/research-brief.md` — seção UX de
  Segurança e Discrição (Safety Net Project, disguise/mask mode, quick exit,
  notificações sem preview, minimização de rastro).
- `squads/brainstorm-amparo/pipeline/data/research-brief.md` — RF-CORE-02
  (modo disfarçado), decisão de produto já tomada pelo product owner.

## Instructions

### Process

1. Ler a arquitetura de informação de Iara para identificar quais
   funcionalidades exigem padrões de discrição aplicados de forma
   transversal (ações globais).
2. Ler a seção de UX de Segurança e Discrição do research brief desta squad
   e o RF-CORE-02 do backlog do brainstorm como base operacional — Daniela
   nunca reinterpreta o conceito do modo disfarçado, apenas o
   operacionaliza.
3. Definir a regra de saída rápida: posição fixa, toque único, transição
   instantânea (nunca animada), e destino exato.
4. Definir a regra do modo disfarçado (RF-CORE-02): configuração, ativação e
   reversão do ícone/tela falsos, sem necessidade de desinstalar o app.
5. Definir a política de notificações neutras (sem preview de conteúdo
   sensível) e a regra de minimização de rastro no histórico do sistema
   (app switcher, capturas de tela recentes).
6. Compilar `output/padroes-seguranca-discricao.md`, com cada padrão
   acompanhado do racional de risco específico que mitiga.

## Output Format

The output MUST follow this exact structure:
```
PADRÕES DE SEGURANÇA E DISCRIÇÃO — AMPARO
Base: RF-CORE-02 + pesquisa Safety Net Project (research-brief.md desta squad)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PADRÃO 1: SAÍDA RÁPIDA (QUICK EXIT)
Regra: {especificação exata}
Racional de risco: {ameaça mitigada}
Destino: {tela neutra}

PADRÃO 2: MODO DISFARÇADO (RF-CORE-02)
Regra: {especificação exata}
Racional de risco: {ameaça mitigada}

PADRÃO 3: NOTIFICAÇÕES NEUTRAS
Regra: {especificação exata}
Racional de risco: {ameaça mitigada}

PADRÃO 4: MINIMIZAÇÃO DE RASTRO NO SISTEMA
Regra: {especificação exata}
Racional de risco: {ameaça mitigada}
```

## Output Example

```
PADRÕES DE SEGURANÇA E DISCRIÇÃO — AMPARO
Base: RF-CORE-02 (backlog brainstorm-amparo) + pesquisa Safety Net Project
(research-brief.md desta squad, seção UX de Segurança e Discrição).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PADRÃO 1: SAÍDA RÁPIDA (QUICK EXIT)
Regra: ícone fixo no canto superior direito, idêntico em 100% das telas
(exceto quando o modo disfarçado já estiver ativo). 1 toque. Transição
INSTANTÂNEA — sem animação, sem easing, sem Smart Animate.
Racional de risco: qualquer atraso perceptível cria janela de exposição
se o agressor observar a tela por cima do ombro da usuária.
Destino: tela neutra configurável pela usuária no onboarding (nunca a
tela de login do próprio Amparo).

PADRÃO 2: MODO DISFARÇADO (RF-CORE-02)
Regra: troca de ícone e tela inicial configurável pela usuária (aliases:
calculadora, diário, previsão do tempo), sem desinstalar o app.
Racional de risco: reduz risco de descoberta do app pelo agressor ao
inspecionar a tela inicial do celular.

PADRÃO 3: NOTIFICAÇÕES NEUTRAS
Regra: nenhuma notificação push/lock screen exibe nome de contato ou
conteúdo do alerta — sempre texto genérico fixo.
Racional de risco: conteúdo de notificação fica visível mesmo com tela
bloqueada, em qualquer momento que o agressor veja o celular de relance.

PADRÃO 4: MINIMIZAÇÃO DE RASTRO NO SISTEMA
Regra: app switcher e capturas de tela recentes exibem a interface do
modo disfarçado, nunca o conteúdo real em uso.
Racional de risco: histórico de apps recentes é vetor de descoberta
documentado pela pesquisa de tecnologia e segurança.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Algum padrão foi definido sem racional de risco explícito associado.
2. A regra de saída rápida permite transição animada ou posição variável
   entre telas.

## Quality Criteria

- [ ] Todo padrão tem racional de risco explícito.
- [ ] Saída rápida especifica posição fixa, 1 toque, transição instantânea.
- [ ] Política de notificações neutras cobre todas as funcionalidades que
      geram notificação no backlog.
- [ ] RF-CORE-02 foi operacionalizado fielmente, sem reinterpretação.
