# Quality Criteria — Landing Page Amparo

## Conversão / UX de Conteúdo (Camila)

- [ ] CTA primário visível sem scroll (above the fold) a partir de 375px de largura
- [ ] Proposta de valor compreensível em ≤5 segundos de leitura do hero
- [ ] Máximo 1 CTA primário visualmente dominante por seção; CTAs secundários com hierarquia visual inferior
- [ ] Toda funcionalidade do app citada no copy está ancorada no backlog real de `brainstorm-amparo` (nunca inventada)
- [ ] Os 3 públicos (vítima/rede de apoio, ONGs/parceiros, banca) têm pelo menos uma seção ou CTA endereçado a eles
- [ ] Zero depoimento nominal/identificável de vítima real; prova social usa apenas dados agregados/institucionais
- [ ] Especificação da Saída Rápida presente e completa (posição, rótulo, comportamento, atalho de teclado)

## Visual (Vitória)

- [ ] Design system documentado antes de qualquer seção (cores, tipografia, grid, espaçamento), traduzido a partir de `brand/design-system.md`
- [ ] Paleta/tipografia vem fielmente e exatamente de `brand/design-system.md` (fonte travada, sempre disponível) — zero cor, fonte ou espaçamento inventado
- [ ] Contraste de texto ≥4.5:1 (normal) / ≥3:1 (grande/ícones) em toda combinação cor/fundo
- [ ] Breakpoints responsivos definidos por conteúdo (não só por dispositivo)
- [ ] Nenhum elemento de imagem realista de violência/vítima — apenas simbólico/abstrato

## Código (Fábio)

- [ ] Projeto Next.js + TypeScript + Tailwind criado no diretório externo confirmado pelo usuário no Step 1 (fora do repositório do TCC)
- [ ] Zero erros de console / zero warnings de hydration mismatch
- [ ] Componente de Saída Rápida: fixo, global (layout raiz), `window.location.replace()`, atalho Esc-Esc, SEM nenhuma transição/animação
- [ ] `<title>`, meta description e Open Graph neutros (sem termos explícitos de violência doméstica)
- [ ] Zero autoplay de áudio/vídeo com som
- [ ] 100% dos elementos interativos navegáveis por teclado com foco visível
- [ ] Imagens via `next/image`, sem CLS perceptível

## Animação (Mariana)

- [ ] Toda animação usa exclusivamente `transform`/`opacity` — nenhuma propriedade de layout animada
- [ ] 100% das animações respeitam `prefers-reduced-motion`
- [ ] `viewport={{ once: true }}` em todo scroll-reveal (sem reanimação ao subir/descer)
- [ ] Saída Rápida explicitamente excluída de qualquer animação/transição
- [ ] Sem excesso de animação simultânea — uso intencional, não decorativo

## Revisão Final (Rafael) — Core Web Vitals (p75, mobile, 4G simulado)

- [ ] LCP < 2.5s
- [ ] CLS < 0.1
- [ ] INP < 200ms
- [ ] Lighthouse Accessibility score ≥ 95
- [ ] Lighthouse Performance score ≥ 90 (mobile)
- [ ] Touch targets ≥ 44×44px em CTAs principais e no botão de Saída Rápida
- [ ] **Gatilho de rejeição automática**: qualquer falha na Saída Rápida (ausente, animada, com confirmação, ou histórico não tratado via `replace()`) — independente da média geral de score
