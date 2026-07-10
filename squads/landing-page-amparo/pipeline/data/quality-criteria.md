# Quality Criteria — Landing Page Amparo

## Conversão / UX de Conteúdo (Camila)

- [ ] CTA primário visível sem scroll (above the fold) no frame desktop e mobile
- [ ] Proposta de valor compreensível em ≤5 segundos de leitura do hero
- [ ] Máximo 1 CTA primário visualmente dominante por seção; CTAs secundários com hierarquia visual inferior
- [ ] Toda funcionalidade do app citada no copy está ancorada no backlog real de `brainstorm-amparo` (nunca inventada)
- [ ] Os 3 públicos (vítima/rede de apoio, ONGs/parceiros, banca) têm pelo menos uma seção ou CTA endereçado a eles
- [ ] Zero depoimento nominal/identificável de vítima real; prova social usa apenas dados agregados/institucionais

## Visual (Vitória)

- [ ] Design system documentado antes de qualquer seção (cores, tipografia, grid, espaçamento), traduzido a partir de `brand/design-system.md`
- [ ] Paleta/tipografia vem fielmente e exatamente de `brand/design-system.md` (fonte travada, sempre disponível) — zero cor, fonte ou espaçamento inventado
- [ ] Contraste de texto ≥4.5:1 (normal) / ≥3:1 (grande/ícones) em toda combinação cor/fundo
- [ ] Frames responsivos definidos por conteúdo (não só por dispositivo)
- [ ] Nenhum elemento de imagem realista de violência/vítima — apenas simbólico/abstrato ou fotografia editorial aprovada
- [ ] Toda direção de motion tem propósito declarado (guiar atenção ou dar feedback)

## Implementação Figma & Assets (Diego)

- [ ] Arquivo Figma criado (ou atualizado, se já existente e registrado em `_memory/memories.md`)
- [ ] Cores/tipografia aplicadas via variáveis Figma espelhando `brand/design-system.md`, nunca valores soltos
- [ ] 100% das seções especificadas por Camila/Vitória construídas, nenhuma pulada silenciosamente
- [ ] Toda imagem gerada cita o prompt exato e segue `direcao-imagens-ia.md`
- [ ] Motion aplicado via `figma-use-motion` apenas onde especificado, com propósito declarado
- [ ] Frames responsivos (desktop 1440px / tablet 768px / mobile 375px) presentes para cada seção
- [ ] Nomenclatura atômica consistente em todo o arquivo

## Revisão Final (Rafael)

- [ ] Fidelidade de copy: 100% do texto construído corresponde a `estrutura-conteudo.md`
- [ ] Fidelidade visual: 100% das seções correspondem a `especificacao-visual.md`
- [ ] WCAG AA aplicado a design: contraste, hierarquia, tamanho de alvo de toque ≥44×44px
- [ ] Consistência responsiva: mesma hierarquia de informação entre frames desktop/tablet/mobile
- [ ] Assets (imagens e motion) avaliados quanto a propósito e conformidade com `direcao-imagens-ia.md`
- [ ] Nenhuma nota atribuída sem justificativa escrita citando a página/frame exata
