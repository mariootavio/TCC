---
execution: inline
agent: wagner-wcag
inputFile: squads/fluxos-uxui-amparo/output/prototipo-navegavel.md
outputFile: squads/fluxos-uxui-amparo/output/revisao-design.md
---

# Step 9: Revisar Design

## Context Loading

Load these files before executing:
- `squads/fluxos-uxui-amparo/output/design-system-figma.md` (Caio)
- `squads/fluxos-uxui-amparo/output/fluxos-ux.md` (Joana)
- `squads/fluxos-uxui-amparo/output/padroes-seguranca-discricao.md` (Daniela)
- `squads/fluxos-uxui-amparo/output/telas-alta-fidelidade.md` (Telma)
- `squads/fluxos-uxui-amparo/output/prototipo-navegavel.md` (Pietro)
- `squads/fluxos-uxui-amparo/pipeline/data/quality-criteria.md`

## Instructions

### Process

1. Carregar o skill `wcag-audit-patterns` antes de iniciar a auditoria de
   acessibilidade, para cobertura completa dos quatro princípios POUR.
2. Ler todos os outputs anteriores da squad por completo antes de iniciar
   qualquer pontuação.
3. Percorrer 100% das páginas/frames do arquivo Figma e 100% das conexões do
   protótipo navegável — nunca avaliar por amostragem.
4. Para cada tela: verificar consistência com o design system de Caio,
   conformidade WCAG 2.2 AA + auditoria POUR completa, e aplicação correta
   da heurística de Nielsen citada por Joana.
5. Para cada elemento de segurança/discrição: verificar conformidade estrita
   com `padroes-seguranca-discricao.md` — qualquer desvio aciona rejeição
   automática do veredito geral.
6. Verificar a integridade do protótipo de Pietro: ausência de telas mortas/
   links quebrados, uso correto de overlays, transição instantânea
   confirmada na saída rápida.
7. Compilar `output/revisao-design.md`: tabela de pontuação, correções
   específicas com frame/página exata, e veredito geral.

## Output Format

The output MUST follow this exact structure:
```
==============================
 VEREDITO DA REVISÃO DE DESIGN: {APROVAR/REJEITAR/APROVAR COM RESSALVAS}
==============================

Escopo revisado: {cobertura}

[GATILHO DE REJEIÇÃO AUTOMÁTICA — se aplicável]

TABELA DE PONTUAÇÃO POR CRITÉRIO
| Critério | Cobertura avaliada | Status |
|---|---|---|

CORREÇÕES ESPECÍFICAS OBRIGATÓRIAS:
{N}. Frame/Página "{nome exato}": {problema} — {correção}.

VEREDITO GERAL: {justificativa da regra de decisão aplicada}
```

## Output Example

```
==============================
 VEREDITO DA REVISÃO DE DESIGN: REJEITAR
==============================

Escopo revisado: 100% das páginas/frames + 100% das conexões do protótipo.

GATILHO DE REJEIÇÃO AUTOMÁTICA — VIOLAÇÃO DE SEGURANÇA/DISCRIÇÃO
Frame "Rede de Apoio / Notificação de Confirmação — Padrão": texto exibe
"Sua guardiã Marina confirmou seu alerta" — viola Padrão 2 de
padroes-seguranca-discricao.md (notificação deve ser neutra).

TABELA DE PONTUAÇÃO POR CRITÉRIO
| Critério | Cobertura avaliada | Status |
|---|---|---|
| Consistência com design system | 100% | OK |
| WCAG 2.2 AA — Touch target (2.5.8) | 100% | FALHA — botão 20x20px |
| Auditoria POUR completa | 100% | FALHA — ver correções |
| Integridade do protótipo (Pietro) | 100% | OK |

CORREÇÕES ESPECÍFICAS OBRIGATÓRIAS:
1. Frame "Rede de Apoio / Notificação de Confirmação — Padrão":
   substituir por texto genérico. CORREÇÃO BLOQUEANTE.
2. Frame "Emergência / Confirmação — Erro Sem Conexão": aumentar botão
   "Cancelar" para no mínimo 24x24px.

VEREDITO GERAL: REJEITAR — violação de segurança/discrição anula a
média geral. Retorna ao Step 7 (Telma Tela).
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. A revisão foi feita por amostragem em vez de cobrir 100% das telas e do
   protótipo.
2. Uma correção foi reportada sem citar o frame/página exata onde o
   problema ocorre.

## Quality Criteria

- [ ] 100% das telas e conexões foram percorridas.
- [ ] Toda violação de segurança/discrição está destacada como gatilho de
      rejeição automática.
- [ ] `wcag-audit-patterns` foi carregado e aplicado.
- [ ] Veredito geral é inequivocamente APROVAR, REJEITAR ou APROVAR COM
      RESSALVAS.
