# Domain Framework — Landing Page Amparo

Framework operacional consolidado para os 5 agentes da squad. A squad transforma em código real (Next.js) o que as squads `brainstorm-amparo` (backlog priorizado) e `marca-design-amparo` (identidade visual) já produziram — nenhum agente desta squad inventa funcionalidade do app ou tokens visuais que não estejam ancorados em uma fonte real.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Visão Geral do Fluxo

```
[Checkpoint: referências + inputs]
   → Camila Conteúdo (estrutura + copy + spec da Saída Rápida)
   → [checkpoint: aprovar estrutura]
   → Vitória Visual (especificação visual completa, baseada na marca)
   → [checkpoint: aprovar especificação visual]
   → Fábio Front-end (implementação real no diretório externo confirmado no Step 1)
   → Mariana Movimento (animações: Framer Motion + GSAP + View Transitions)
   → [checkpoint: aprovar implementação]
   → Rafael Rigor (revisão: marca, código, WCAG AA, Core Web Vitals, Saída Rápida)
   → [checkpoint: aprovação final]
```

Cada etapa depende estritamente da anterior. A squad tem quatro checkpoints intermediários (steps 1, 3, 5, 8) e um checkpoint final (step 10). Rejeição de Rafael (step 9) volta ao step 6 (Fábio), que coordena correções de código/animação/visual conforme a causa do problema.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 1. Camila Conteúdo — Estrutura, Copy e Spec da Saída Rápida

Lê o backlog mais recente de `brainstorm-amparo` e o company.md para nunca inventar funcionalidade. Define a arquitetura de seções (Hero, Problema/Solução, Funcionalidades, Como Funciona, Prova Social institucional, Sobre o Projeto/TCC, Contato/Download), o copy de cada seção usando o framework AIDA/PAS adaptado de `copywriting.md`, a mensagem específica para os 3 públicos simultâneos, e a especificação funcional (não visual) do botão de Saída Rápida: posição, rótulo, comportamento de redirecionamento, atalho de teclado. Esse requisito nasce aqui, antes de qualquer decisão visual ou de código — nunca como adendo posterior.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 2. Vitória Visual — Especificação Visual

Traduz a estrutura de Camila em um sistema de design completo: paleta de cores, tipografia, grid, espaçamento, imagery, breakpoints responsivos. Lê o design system publicado pela `marca-design-amparo`; se existir, usa fielmente os tokens de lá (nunca reinterpreta). Se não existir ainda, define uma paleta/tipografia provisória claramente marcada como "PENDENTE — substituir quando marca-design-amparo publicar". Usa as skills `design-taste-frontend` e `high-end-visual-design` para garantir um resultado moderno e premium, não genérico.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 3. Fábio Front-end — Implementação Real

Constrói o projeto Next.js + TypeScript + Tailwind + shadcn/ui no diretório externo confirmado pelo usuário no Step 1 (fora deste repositório — caminho registrado em `output/inputs-e-referencias.md`), nunca em squads/output/. Implementa cada seção como componente, aplica a especificação visual de Vitória, garante responsividade e acessibilidade (navegação por teclado, ARIA, contraste), e implementa o componente de Saída Rápida — fixo, global, no layout raiz, SEM nenhuma animação ou transição (ação instantânea via `window.location.replace()`, atalho Esc-Esc global).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 4. Mariana Movimento — Animações

Adiciona a camada de animação sobre o código de Fábio: scroll reveals com `viewport={{ once: true }}`, stagger em listas/cards, micro-interações em botões, parallax sutil em elementos decorativos, e — via skill `gpt-taste` — ScrollTrigger avançado (pinning/stacking/scrubbing) onde fizer sentido. Toda animação usa exclusivamente `transform`/`opacity`, respeita `prefers-reduced-motion`, e exclui explicitamente o componente de Saída Rápida de qualquer animação.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 5. Rafael Rigor — Revisão Final

Avalia 100% do site: fidelidade à especificação visual e à marca, qualidade do código (best practices React/Next.js), WCAG AA completo (skill `wcag-audit-patterns`), Web Interface Guidelines (skill `web-design-guidelines`), e Core Web Vitals (LCP/CLS/INP). Qualquer falha na Saída Rápida (ausente, animada, ou com confirmação antes de redirecionar) é gatilho de rejeição automática, independente da média geral — mesmo princípio do Wagner WCAG em `fluxos-uxui-amparo`.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Resumo de Responsabilidades por Agente

| Agente | Entrada principal | Saída | Skill nativa principal |
|---|---|---|---|
| Camila Conteúdo | backlog brainstorm-amparo + company.md + referências | `estrutura-conteudo.md` | — (texto) |
| Vitória Visual | estrutura-conteudo.md + design system marca-design-amparo | `especificacao-visual.md` | design-taste-frontend, high-end-visual-design, frontend-design |
| Fábio Front-end | especificacao-visual.md | `implementacao-frontend.md` + código no diretório externo confirmado no Step 1 | shadcn, vercel-react-best-practices, vercel-composition-patterns, full-output-enforcement |
| Mariana Movimento | implementacao-frontend.md | `animacoes.md` + código atualizado | gpt-taste, vercel-react-view-transitions, full-output-enforcement |
| Rafael Rigor | todos os outputs anteriores | `revisao-final.md` | web-design-guidelines, wcag-audit-patterns |
