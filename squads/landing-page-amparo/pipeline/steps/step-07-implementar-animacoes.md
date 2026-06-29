---
execution: inline
agent: mariana-movimento
inputFile: squads/landing-page-amparo/output/implementacao-frontend.md
outputFile: squads/landing-page-amparo/output/animacoes.md
---

# Step 7: Implementar Animações

## Context Loading

Load these files before executing:
- `squads/landing-page-amparo/output/implementacao-frontend.md` (Fábio) —
  estrutura de componentes já implementada, incluindo o caminho absoluto do
  projeto.
- `squads/landing-page-amparo/output/especificacao-visual.md` (Vitória) —
  tom visual que a animação precisa reforçar.
- `pipeline/data/research-brief.md` (seção 2) — padrões de animação,
  performance e acessibilidade.

## Instructions

### Process

1. Carregar as skills `gpt-taste`, `vercel-react-view-transitions` e
   `full-output-enforcement` antes de escrever qualquer animação.
2. Configurar `prefers-reduced-motion` no nível raiz do projeto (ex.:
   `MotionConfig reducedMotion="user"`) antes de adicionar qualquer animação
   individual.
3. Localizar o componente de Saída Rápida no código de Fábio e confirmar
   explicitamente que ele NÃO será tocado por nenhuma das etapas seguintes.
4. Aplicar scroll-reveal (`whileInView` + `viewport={{ once: true }}`) e
   stagger em listas de itens (Funcionalidades, Como Funciona, Prova Social).
5. Aplicar micro-interações (`whileHover`/`whileTap`, scale 1.02–1.05) em
   botões e cards interativos — exceto na Saída Rápida.
6. Aplicar efeitos avançados (parallax sutil no Hero, ou ScrollTrigger com
   pinning/scrubbing em uma seção que se beneficie de destaque) onde fizer
   sentido, sempre animando exclusivamente `transform`/`opacity`.
7. Verificar explicitamente que a Saída Rápida permanece livre de qualquer
   animação, e compilar `animacoes.md` com a lista de animações aplicadas
   por seção e essa confirmação.

## Output Format

```
CONFIGURAÇÃO GLOBAL
prefers-reduced-motion: {configurado, onde}

ANIMAÇÕES POR SEÇÃO
- {seção}: {tipo de animação, propriedades animadas, trigger}

VERIFICAÇÃO — SAÍDA RÁPIDA
Resultado: {CONFIRMADO livre de animação / problema encontrado e corrigido}
```

## Output Example

Ver `pipeline/data/output-examples.md`, Exemplo 6 (scroll-reveal com stagger)
e a verificação explícita de exclusão da Saída Rápida no agente Mariana
Movimento — o output real cobre todas as seções animadas com esse mesmo
nível de precisão técnica.

## Veto Conditions

Reject and redo if ANY of these are true:
1. O componente de Saída Rápida recebeu qualquer `motion.*`, `transition`, `whileHover` ou `whileInView`.
2. Alguma animação anima propriedades de layout (`width`, `top`, `margin`) em vez de `transform`/`opacity`.
3. `prefers-reduced-motion` não está configurado globalmente.

## Quality Criteria

- [ ] Toda animação usa exclusivamente `transform`/`opacity`
- [ ] `viewport={{ once: true }}` em 100% dos scroll-reveals
- [ ] Saída Rápida confirmada como livre de animação (declaração explícita no output)
- [ ] Nenhuma seção com animação simultânea excessiva
