# Research Brief — Landing Page Amparo

Compilado a partir de pesquisa dedicada em 3 domínios: UX/conversão de
landing page de causa social, prototipagem de alta fidelidade e motion no
Figma, e checklist de qualidade/acessibilidade aplicada a design (não a
código).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 1. UX & Conversão de Landing Page — Causa Social / App-Download

### Framework estrutural principal

Hero (above the fold) → Problema/Solução → Como Funciona/Funcionalidades →
Prova Social institucional → Mensagem multi-público → CTA final + Rodapé.

- **Hero**: headline emocional e clara, subheadline com a proposta de
  valor em uma frase, CTA primário de alto contraste, visual simbólico ou
  fotografia editorial (nunca foto realista de violência/vítima).
- **Problema → Solução**: nomeia o problema social com estatística,
  posiciona o app como ponte de solução, sem explorar trauma graficamente.
- **Funcionalidades**: blocos de 3-4 features-chave (ícone, título curto
  e 1 frase de benefício, nunca lista de specs técnicas).
- **Prova social institucional**: como é causa sensível, substitui
  depoimentos nominais por selos de credibilidade (Lei Maria da Penha,
  parcerias com ONGs, números agregados anônimos — nunca identificação de
  vítimas reais).
- **Mensagem multi-público**: a mulher em risco (CTA primário), a rede de
  apoio dela (CTA secundário "indicar para alguém"), e parceiros
  institucionais/banca (seção "sobre o projeto").
- **CTA final + rodapé**: repetição do CTA de download + links
  institucionais.

Segundo framework usado dentro de cada seção: **AIDA adaptado** (Atenção
via estatística/headline → Interesse via contexto sem detalhes gráficos →
Desejo mostrando a transformação possível → Ação com CTA único por seção).

### Anti-padrões específicos (resumo — ver anti-patterns.md para a lista completa)

Fotos realistas de violência; múltiplos CTAs concorrentes no hero; copy
vago/institucional; depoimentos nominais de vítimas; excesso de scroll
antes do CTA principal; motion sem propósito.

### Vocabulário de domínio

Usar: *above the fold*, *hero section*, *proposta de valor*, *CTA
primário/secundário*, *prova social*, *funil de conversão*, *trust
signals*, *microcopy*.
Evitar: "clique aqui" como texto de link sem contexto semântico; "bastante
informação" como objetivo de página; chamar motion de "efeito bonito" sem
relação com função.

Sources: [Nonprofit Landing Page Best Practices](https://www.trajectorywebdesign.com/blog/nonprofit-landing-page-best-practices), [Optimizing Donation Landing Pages](https://fundraiseup.com/blog/Optimizing-Donation-Landing-Pages/), [Landing Page Structure](https://www.involve.me/blog/landing-page-structure), [Hero Sections That Really Convert](https://hype4.academy/articles/design/hero-sections-that-really-convert), [10 Common Landing Page Mistakes](https://www.neue.world/insights/10-landing-page-mistakes-that-are-costing-you-conversions), [CTA Design Pitfalls](https://vwo.com/blog/common-call-to-action-mistakes/)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 2. Prototipagem de Alta Fidelidade e Motion no Figma

### Padrões concretos

- **Scroll-reveal simulado**: no Figma, representado como estado
  "revelado" de um componente (opacity/posição), ativado via interação de
  scroll do protótipo ou Smart Animate entre variantes — dispara a
  intenção de entrada sem depender de código real.
- **Stagger visual**: variantes sequenciais de um componente com atraso
  incremental entre elementos de uma lista, simulado via Smart Animate
  com easing e delay configurados por camada.
- **Micro-interações**: variantes de hover/pressed em componentes
  interativos (botões, cards), com mudança sutil de escala (1.02–1.05) ou
  cor — configuradas como interações do protótipo Figma.
- **Transições de seção**: Smart Animate entre frames representando
  estados de scroll ou navegação, para simular parallax e transições
  "wow" sem depender de biblioteca de animação real.

### Consistência e organização do arquivo Figma

- Variáveis de cor/tipografia/espaçamento espelhando `brand/design-system.md`
  configuradas uma vez (via `figma-generate-library`) e reutilizadas em
  toda seção — nunca valores soltos por frame.
- Nomenclatura atômica consistente (`Atoms/Button/Primary`,
  `Organisms/Hero`) para que o arquivo seja navegável e editável por
  qualquer pessoa que abrir depois.
- Frames responsivos por seção (desktop 1440px, tablet 768px, mobile
  375px), sempre alinhados ao grid definido por Vitória.

Sources: [Figma Smart Animate](https://help.figma.com/hc/en-us/articles/360039818854-Prototype-with-smart-animate), [Figma Interactive Components](https://help.figma.com/hc/en-us/articles/360055203533-Guide-to-interactive-components), [Figma Variables](https://help.figma.com/hc/en-us/articles/15145852043927-Guide-to-variables-in-Figma), [Prototyping best practices](https://www.figma.com/best-practices/guide-to-prototyping/)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 3. Checklist de Qualidade/Acessibilidade Aplicada a Design

WCAG AA relevante para revisão de design (não de código): contraste 4.5:1
(texto normal) / 3:1 (texto grande, 1.4.3), tamanho de alvo de toque ≥44px
recomendado (2.5.8), hierarquia tipográfica lógica (2.4.6), foco visual
representado no protótipo para elementos interativos (2.4.7).

Consistência responsiva: mesma hierarquia de informação em desktop,
tablet e mobile, com adaptação proporcional de tipografia e espaçamento —
nunca reordenação que quebre a lógica de leitura entre breakpoints.

Sources: [WCAG Target Size Guide](https://testparty.ai/blog/wcag-target-size-guide), [Mobile Accessibility — W3C](https://www.w3.org/TR/mobile-accessibility-mapping/), [Figma Accessibility Plugins & Practices](https://www.figma.com/community/accessibility)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

**Nota:** esta squad entrega um arquivo Figma completo e navegável como
produto final — não uma prévia de um site que será codificado depois.
Por isso todo critério de qualidade (fidelidade, acessibilidade,
consistência responsiva) é avaliado diretamente no Figma, nunca adiado
para uma etapa de implementação futura.
