# Research Brief — Landing Page Amparo

Compilado a partir de pesquisa dedicada em 4 domínios: UX/conversão de landing page de causa social, implementação front-end React/Next.js com animação, o padrão de Saída Rápida para sites de apoio a vítimas de violência doméstica, e checklist de qualidade/acessibilidade mobile-first.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 1. UX & Conversão de Landing Page — Causa Social / App-Download

### Framework estrutural principal

Hero (above the fold) → Problema/Solução → Como Funciona/Funcionalidades → Prova Social institucional → Mensagem multi-público → CTA final + Rodapé com Saída Rápida.

- **Hero**: headline emocional e clara, subheadline com a proposta de valor em uma frase, CTA primário de alto contraste, visual simbólico (nunca foto realista de violência/vítima).
- **Problema → Solução**: nomeia o problema social com estatística, posiciona o app como ponte de solução, sem explorar trauma graficamente.
- **Funcionalidades**: blocos de 3-4 features-chave (ícone + título curto + 1 frase de benefício, nunca lista de specs técnicas).
- **Prova social institucional**: como é causa sensível, substitui depoimentos nominais por selos de credibilidade (Lei Maria da Penha, parcerias com ONGs, números agregados anônimos — nunca identificação de vítimas reais).
- **Mensagem multi-público**: a mulher em risco (CTA primário), a rede de apoio dela (CTA secundário "indicar para alguém"), e parceiros institucionais/banca (seção "sobre o projeto").
- **CTA final + rodapé**: repetição do CTA de download + links institucionais + Saída Rápida sempre visível (não só no rodapé).

Segundo framework usado dentro de cada seção: **AIDA adaptado** (Atenção via estatística/headline → Interesse via contexto sem detalhes gráficos → Desejo mostrando a transformação possível → Ação com CTA único por seção).

### Anti-padrões específicos (resumo — ver anti-patterns.md para a lista completa)

Fotos realistas de violência; múltiplos CTAs concorrentes no hero; copy vago/institucional; depoimentos nominais de vítimas; ausência de Saída Rápida; autoplay de som/vídeo; excesso de scroll antes do CTA principal.

### Vocabulário de domínio

Usar: *above the fold*, *hero section*, *proposta de valor*, *CTA primário/secundário*, *prova social*, *funil de conversão*, *trust signals*, *microcopy*.
Evitar: "clique aqui" como texto de link sem contexto semântico; "bastante informação" como objetivo de página; chamar animação de "efeito bonito" sem relação com função.

Sources: [Nonprofit Landing Page Best Practices](https://www.trajectorywebdesign.com/blog/nonprofit-landing-page-best-practices), [Optimizing Donation Landing Pages](https://fundraiseup.com/blog/Optimizing-Donation-Landing-Pages/), [Landing Page Structure](https://www.involve.me/blog/landing-page-structure), [Hero Sections That Really Convert](https://hype4.academy/articles/design/hero-sections-that-really-convert), [10 Common Landing Page Mistakes](https://www.neue.world/insights/10-landing-page-mistakes-that-are-costing-you-conversions), [CTA Design Pitfalls](https://vwo.com/blog/common-call-to-action-mistakes/)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 2. Front-end React + Next.js com Animação (Framer Motion / GSAP / View Transitions)

### Padrões concretos

- **Scroll-triggered reveals**: `whileInView` com `viewport={{ once: true, amount: 0.3 }}` — dispara só na primeira entrada, evita custo de reanimação.
- **Staggered entrance**: `staggerChildren` (0.08–0.15s) + `delayChildren` no `variants` do elemento pai.
- **Micro-interações**: `whileHover`/`whileTap` com `scale: 1.02–1.05` + sombra — nunca animar width/height.
- **Parallax sutil**: `useScroll` + `useTransform` mapeando progresso de scroll a `translateY` discreto (10–40px) em elementos decorativos, nunca no texto de leitura.
- **GSAP ScrollTrigger avançado** (via skill `gpt-taste`): pinning, stacking, scrubbing para seções com efeito "wow" controlado.
- **View Transitions nativas** (via skill `vercel-react-view-transitions`): transições de seção/rota sem dependência de biblioteca externa, complementando Framer Motion/GSAP.

### Performance e acessibilidade

- `prefers-reduced-motion` obrigatório em 100% das animações (`MotionConfig reducedMotion="user"` ou `useReducedMotion()`).
- Animar exclusivamente `transform`/`opacity` — nunca width/height/top/left/background-color/font-size.
- `next/image` (lazy por padrão) + `next/dynamic` para componentes pesados.
- Metas de Core Web Vitals (p75, mobile): **LCP < 2.5s, CLS < 0.1, INP < 200ms**.

Sources: [Framer Motion Scroll Animations](https://jb.desishub.com/blog/framer-motion), [Motion for React — Scroll Animations](https://motion.dev/docs/react-scroll-animations), [Staggered Animation in Next.js](https://singlesyntax.com/blog/staggered-animation-in-nextjs), [Core Web Vitals 2026](https://www.corewebvitals.io/core-web-vitals), [Accessibility + Core Web Vitals](https://apogeewatcher.com/blog/accessibility-core-web-vitals), [Why React Animations Feel Janky](https://medium.com/@rahul.dinkar/why-your-react-animations-feel-janky-and-how-to-fix-it-without-rewriting-ui-08326dec3ba0)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 3. Padrão "Saída Rápida" — Sites de Apoio a Vítimas de Violência Doméstica

Padrão consolidado, usado por organizações reais (thehotline.org, Barrier Free Living, techsafety.org/Safety Net Project). **Obrigatório nesta squad, não opcional.**

- **Posição**: botão fixo (`position: fixed`), canto superior ou inferior direito, visível em 100% das páginas, `z-index` acima de qualquer overlay.
- **Rótulo**: curto e autoexplicativo ("X", "Sair", "Saída Rápida").
- **Comportamento**: redireciona IMEDIATAMENTE (sem confirmação/modal) via `window.location.replace()` para um site neutro real (não página em branco).
- **Atalho de teclado**: Esc-Esc (duas vezes em janela curta) dispara a mesma ação, em qualquer ponto do site.
- **Limitação transparente**: o quick exit NÃO apaga o histórico do navegador de fato — comunicar isso com um link para dicas de navegação segura, nunca prometer invisibilidade total.
- **Discrição do site inteiro**: `<title>`/meta description/Open Graph neutros (sem "violência doméstica" explícito), favicon neutro, zero autoplay de som/vídeo, sem pop-ups agressivos.

Sources: [The National Domestic Violence Hotline](https://www.thehotline.org/), [Quick Escape Button — Columbia Health](https://www.health.columbia.edu/content/quick-escape-button), [Safety First — Barrier Free Living](https://www.bflnyc.org/safety-first-the-importance-of-a-websites-domestic-violence-related-escape-button/), [Exit From This Website Quickly — techsafety.org](https://www.techsafety.org/exit-from-this-website-quickly), [Internet Safety for Survivors](https://www.thehotline.org/plan-for-safety/internet-safety/)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 4. Checklist de Qualidade/Acessibilidade — Mobile-First Animado

WCAG AA relevante para conteúdo animado: `prefers-reduced-motion` (2.3.3), sem flash >3x/s (2.3.1), navegação 100% por teclado (2.1.1), ordem de foco lógica (2.4.3), animações >5s pausáveis (2.2.2), contraste 4.5:1/3:1 (1.4.3), alt apropriado (1.1.1), touch target ≥24px CSS / 44-48px recomendado (2.5.8).

Mobile-first: media queries `min-width`, breakpoints por conteúdo, `viewport` sem `user-scalable=no`, 8-12px de espaçamento entre alvos clicáveis, sem dependência de hover, testado em 375/768/1440px + dispositivo real.

Sources: [WCAG Target Size Guide](https://testparty.ai/blog/wcag-target-size-guide), [Responsive Design Checklist 2025](https://www.webstacks.com/blog/responsive-design-guide), [Mobile Accessibility — W3C](https://www.w3.org/TR/mobile-accessibility-mapping/), [Core Web Vitals 2026](https://www.corewebvitals.io/core-web-vitals)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Nota:** o domínio 3 (Saída Rápida) é o requisito mais diferenciador e crítico do projeto — tratado por todos os agentes como não-negociável, presente desde a estrutura de Camila até a revisão final de Rafael, nunca como "extra" de acessibilidade.
