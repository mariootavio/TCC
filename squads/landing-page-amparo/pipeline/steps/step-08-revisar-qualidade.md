---
execution: inline
agent: rafael-rigor
inputFile: squads/landing-page-amparo/output/implementacao-figma.md
outputFile: squads/landing-page-amparo/output/revisao-final.md
---

# Step 8: Revisar Qualidade

## Context Loading

Load these files before executing:
- `squads/landing-page-amparo/output/implementacao-figma.md` (Diego).
- `squads/landing-page-amparo/output/especificacao-visual.md` (Vitória).
- `squads/landing-page-amparo/output/estrutura-conteudo.md` (Camila).
- `pipeline/data/quality-criteria.md` — critérios completos de avaliação.
- `pipeline/data/direcao-imagens-ia.md` — regras trauma-informadas para
  avaliar as imagens geradas.

## Instructions

### Process

1. Carregar as skills `wcag-audit-patterns` e `web-design-guidelines` antes
   de iniciar qualquer avaliação.
2. Revisar fidelidade de copy: comparar o texto construído no Figma com
   `estrutura-conteudo.md` seção por seção.
3. Revisar fidelidade visual e de marca: comparar a implementação com
   `especificacao-visual.md` seção por seção — cores, tipografia,
   espaçamento, grid, todos rastreáveis a `brand/design-system.md`.
4. Revisar os assets: verificar se as imagens geradas seguem
   `direcao-imagens-ia.md` e se o motion aplicado tem propósito declarado
   e coerência com a direção de Vitória.
5. Revisar acessibilidade e consistência responsiva: contraste, hierarquia
   tipográfica, tamanho de alvos de toque, e consistência entre os frames
   desktop/tablet/mobile de cada seção.
6. Compilar o veredito em `revisao-final.md`: tabela de pontuação,
   correções obrigatórias com localização exata (página/frame), pontos
   fortes, e veredito final.

## Output Format

```text
==============================
 VEREDITO: {APROVAR | APROVAR COM RESSALVAS | REJEITAR}
==============================

SCORING:
| Critério | Score | Resumo |
|---|---|---|
| Fidelidade de copy | X/10 | ... |
| Fidelidade à marca/visual | X/10 | ... |
| Qualidade dos assets/motion | X/10 | ... |
| WCAG AA (design) | X/10 | ... |
| Consistência responsiva | X/10 | ... |

OVERALL: X.X/10

Ponto forte: ...
Correção obrigatória: ... (página/frame exatos)

VERDICT: ...
```

## Output Example

Ver `pipeline/data/output-examples.md`, Exemplo 8 — veredito completo de
aprovação condicional.

## Veto Conditions

Reject and redo if ANY of these are true:
1. Algum critério recebeu nota sem justificativa escrita.
2. A revisão não cobriu 100% das seções e frames responsivos.
3. Uma imagem ou motion foi avaliado sem checar `direcao-imagens-ia.md`.

## Quality Criteria

- [ ] 100% das seções e frames avaliados, nunca por amostragem
- [ ] Toda correção obrigatória cita página/frame exata
- [ ] Pelo menos um ponto forte citado, mesmo em veredito de rejeição
- [ ] Veredito final consistente com a tabela de pontuação (sem contradição)
