---
execution: inline
agent: rafael-rigor
inputFile: squads/landing-page-amparo/output/animacoes.md
outputFile: squads/landing-page-amparo/output/revisao-final.md
---

# Step 9: Revisar Qualidade

## Context Loading

Load these files before executing:
- `squads/landing-page-amparo/output/animacoes.md` (Mariana).
- `squads/landing-page-amparo/output/implementacao-frontend.md` (Fábio).
- `squads/landing-page-amparo/output/especificacao-visual.md` (Vitória).
- `squads/landing-page-amparo/output/estrutura-conteudo.md` (Camila).
- `pipeline/data/quality-criteria.md` — critérios completos de avaliação.

## Instructions

### Process

1. Carregar as skills `wcag-audit-patterns` e `web-design-guidelines` antes
   de iniciar qualquer avaliação.
2. Verificar a Saída Rápida primeiro, antes de qualquer outro critério:
   posição fixa, ausência total de animação, `window.location.replace()`,
   atalho Esc-Esc funcional, ausência de modal de confirmação. Qualquer
   falha aqui já determina REJEITAR.
3. Revisar fidelidade visual: comparar a implementação com
   `especificacao-visual.md` seção por seção.
4. Revisar qualidade de código: warnings de hydration, erros de console,
   arquitetura de componentes, uso correto de Server/Client Components.
5. Revisar acessibilidade completa: teclado, foco visível, ARIA, contraste,
   `prefers-reduced-motion`, tamanho de alvos de toque.
6. Medir Core Web Vitals (LCP, CLS, INP) em condição mobile/4G simulada,
   comparando contra as metas de `pipeline/data/quality-criteria.md`.
7. Compilar o veredito em `revisao-final.md`: gatilho de rejeição automática
   em destaque (se houver), tabela de pontuação, correções obrigatórias com
   localização exata, pontos fortes, e veredito final.

## Output Format

```
==============================
 VEREDITO: {APROVAR | APROVAR COM RESSALVAS | REJEITAR}
==============================
GATILHO DE REJEIÇÃO AUTOMÁTICA: {nenhum | descrição + arquivo/linha exatos}

SCORING:
| Critério | Score | Resumo |
|---|---|---|
| Fidelidade à marca/visual | X/10 | ... |
| Qualidade de código | X/10 | ... |
| WCAG AA | X/10 | ... |
| Core Web Vitals | X/10 | ... |
| Saída Rápida | X/10 | ... |

OVERALL: X.X/10

Ponto forte: ...
Correção obrigatória: ... (arquivo/linha exatos)

VERDICT: ...
```

## Output Example

Ver `pipeline/data/output-examples.md`, Exemplo 7 — vereditos completos de
aprovação condicional e de rejeição automática por falha na Saída Rápida.

## Veto Conditions

Reject and redo if ANY of these are true:
1. A revisão não verificou a Saída Rápida explicitamente em primeiro lugar.
2. Algum critério recebeu nota sem justificativa escrita.
3. Core Web Vitals foram medidos apenas em condição desktop, não mobile/4G.

## Quality Criteria

- [ ] 100% das seções avaliadas, nunca por amostragem
- [ ] Toda correção obrigatória cita arquivo/linha/seção exata
- [ ] Pelo menos um ponto forte citado, mesmo em veredito de rejeição
- [ ] Veredito final consistente com a tabela de pontuação (sem contradição)
