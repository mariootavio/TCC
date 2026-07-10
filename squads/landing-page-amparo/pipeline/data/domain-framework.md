# Domain Framework — Landing Page Amparo

Framework operacional consolidado para os 4 agentes da squad. A squad
transforma em uma landing page real no Figma o que as squads
`brainstorm-amparo` (backlog priorizado) já produziu e a identidade visual
já finalizada em `brand/` — nenhum agente desta squad inventa
funcionalidade do app ou tokens visuais que não estejam ancorados em uma
fonte real.

**Design system travado:** a identidade visual do Amparo já está
finalizada e aprovada em `brand/design-system.md` (paleta hex, tipografia,
espaçamento, componentes) e `brand/LogoAmparo.svg` (logo vetorial oficial)
— ver `brand/README.md`. Esses arquivos SEMPRE existem e são a fonte
primária; não existe cenário de "paleta provisória PENDENTE" nesta squad.
Todo agente que definir ou implementar visual (cor, fonte, espaçamento,
logo) usa exatamente os valores de `brand/design-system.md`, nunca um
valor novo ou aproximado.

**Entregável 100% Figma:** esta squad não produz código. O produto final é
um arquivo Figma completo e navegável — copy, visual, imagens e motion —
pronto para ser apresentado, compartilhado ou usado como especificação de
origem para uma eventual implementação em código futura (fora do escopo
desta squad).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Visão Geral do Fluxo

```text
[Checkpoint: referências + inputs — novo build ou ajuste]
   → Camila Conteúdo (estrutura + copy)
   → [checkpoint: aprovar estrutura]
   → Vitória Visual (especificação visual + imagery + motion, baseada na marca)
   → [checkpoint: aprovar especificação visual]
   → Diego Assets (construção no Figma + geração de imagens + motion no protótipo)
   → [checkpoint: aprovar landing page no Figma]
   → Rafael Rigor (revisão: copy, marca, assets, WCAG AA, consistência responsiva)
   → [checkpoint: aprovação final]
```

Cada etapa depende estritamente da anterior. A squad tem quatro
checkpoints intermediários (steps 1, 3, 5, 7) e um checkpoint final
(step 9). Rejeição de Rafael (step 8) volta ao step 6 (Diego), que
coordena correções de visual/copy/assets conforme a causa do problema.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 1. Camila Conteúdo — Estrutura e Copy

Lê o backlog mais recente de `brainstorm-amparo` e o company.md para nunca
inventar funcionalidade. Define a arquitetura de seções (Hero,
Problema/Solução, Funcionalidades, Como Funciona, Prova Social
institucional, Sobre o Projeto/TCC, Contato/Download) e o copy de cada
seção usando o framework AIDA/PAS adaptado de `copywriting.md`, endereçando
a mensagem específica para os 3 públicos simultâneos.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 2. Vitória Visual — Especificação Visual

Traduz a estrutura de Camila em um sistema de design completo: paleta de
cores, tipografia, grid, espaçamento, imagery, direção de motion e frames
responsivos. Lê `brand/design-system.md` e `brand/LogoAmparo.svg`
(identidade JÁ FINALIZADA e travada) e usa fielmente os valores de lá —
nunca reinterpreta, ajusta ou propõe alternativa. A especificação visual
desta squad é 100% derivada de `brand/design-system.md`, nunca inventada.
Usa as skills `design-taste-frontend` e `high-end-visual-design` apenas
para composição/layout/hierarquia/motion, nunca para escolher cor ou
tipografia fora da marca.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 3. Diego Assets — Implementação no Figma & Produção de Assets

Constrói a landing page inteira no arquivo Figma do Amparo (via MCP),
seção por seção, aplicando fielmente o copy de Camila e a especificação de
Vitória. Configura variáveis de design system (via `figma-generate-library`),
monta a página com `figma-generate-design`, gera imagens via
`image-ai-generator` seguindo `direcao-imagens-ia.md`, e aplica motion no
protótipo via `figma-use-motion`. Se já existe um arquivo Figma desta
landing page (registrado em `_memory/memories.md`), atualiza esse arquivo
em vez de criar um novo — suporta ajustes incrementais entre execuções.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 4. Rafael Rigor — Revisão Final

Avalia 100% da landing page construída no Figma: fidelidade de copy,
fidelidade à especificação visual e à marca, qualidade e propósito dos
assets (imagens e motion), WCAG AA aplicado a design (skill
`wcag-audit-patterns`), Web Interface Guidelines (skill
`web-design-guidelines`), e consistência entre frames responsivos.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Resumo de Responsabilidades por Agente

| Agente | Entrada principal | Saída | Skill nativa principal |
|---|---|---|---|
| Camila Conteúdo | backlog brainstorm-amparo + company.md + referências | `estrutura-conteudo.md` | — (texto) |
| Vitória Visual | estrutura-conteudo.md + brand/design-system.md | `especificacao-visual.md` | design-taste-frontend, high-end-visual-design, frontend-design |
| Diego Assets | especificacao-visual.md | `implementacao-figma.md` + arquivo Figma real | figma-use, figma-generate-design, figma-generate-library, figma-use-motion, image-ai-generator |
| Rafael Rigor | todos os outputs anteriores | `revisao-final.md` | web-design-guidelines, wcag-audit-patterns |
