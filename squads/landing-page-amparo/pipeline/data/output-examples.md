# Output Examples — Landing Page Amparo

## Exemplo 1: Hero copy (Camila Conteúdo)

```text
HEADLINE: "Você não está sozinha. Amparo está com você."
SUBHEADLINE: "Um app gratuito e discreto para pedir ajuda, registrar provas
e se conectar com uma rede de apoio em segundos — mesmo quando você não
pode falar."
CTA PRIMÁRIO: "Baixar o Amparo grátis" (ícone App Store/Play Store)
MICROCOPY DE CONFIANÇA: "100% gratuito · Discreto · Disponível 24h"
```

## Exemplo 2: Bloco de funcionalidade (Camila Conteúdo)

```text
🔘 Botão de emergência discreto
Um toque silencioso aciona sua rede de confiança e compartilha sua
localização — sem alarmes, sem chamar atenção.
[ancoragem: RF-CORE-01 do backlog brainstorm-amparo]
```

## Exemplo 3: Prova social institucional (Camila Conteúdo)

```text
"O Amparo segue as diretrizes da Lei Maria da Penha e foi desenvolvido em
consulta com especialistas em proteção à mulher."
[selos: Disque 180, Lei 11.340/2006, parceiros institucionais]
"+12.000 mulheres já contam com a rede de apoio do Amparo."
(estatística agregada e anônima — nunca nomes ou rostos identificáveis)
```

## Exemplo 4: Seção de design system (Vitória Visual)

```text
DESIGN SYSTEM — Landing Page Amparo
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Fonte: brand/design-system.md — fonte única, travada, sempre disponível.

Cores:
  Primária:   #954B6E (Vinho Amparo — CTAs, headlines)
  Secundária: #C58DA8 (Malva Suave — acentos, ícones)
  Fundo:      #F2EAE4 (Areia Acolhedora — fundo de seção)
  Texto:      #333333 (Grafite Leitura, nunca preto puro)
  Sucesso/Apoio: #2E7D6B (verde institucional — selos, confirmações)

Tipografia:
  Títulos: 'Quicksand', SemiBold 600
  Corpo:   'Nunito Sans', Regular 400
  Hero:      40px / 600 (desktop) · 28px / 600 (mobile)
  Heading:   24px / 500
  Body:      16px / 400
  Caption:   12px / 400

Espaçamento: base 8px, seções com padding vertical de 96px (desktop) / 56px (mobile)
Grid: 12 colunas, max-width 1200px, gutter 24px
Border radius: 12px (cards/botões)
Contraste: todos os pares texto/fundo ≥4.5:1 (verificado)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

## Exemplo 5: Especificação de seção com imagery e motion (Vitória Visual)

```text
SEÇÃO: Hero
Layout: grid de 2 colunas desktop (texto 60% / imagem 40%);
  1 coluna mobile (texto, depois imagem)
Imagery: fotografia editorial de mulher real olhando o celular, luz natural,
  paleta calibrada em Vinho Amparo/Areia Acolhedora — ver direcao-imagens-ia.md
Espaçamento: padding-top 120px desktop / 72px mobile
Motion: entrada em fade+slide sutil (opacity + translateY 16px) no headline
  e subheadline ao carregar; CTA primário com micro-interação de hover
  (scale 1.03). Nenhum motion contínuo/looping que distraia da leitura.
Responsivo: H1 reduzido proporcionalmente em mobile, imagem migra para
  baixo do texto em telas <768px
```

## Exemplo 6: Implementação de seção no Figma com asset gerado (Diego Assets)

```markdown
# Implementação Figma — Seção Hero

Arquivo Figma: "Amparo — Landing Page" (criado nesta execução)
Página: "Landing Page / Desktop"
Frame: "Hero — 1440px" (+ "Hero — 768px" e "Hero — 375px")

Variáveis usadas: color/primary/vinho-amparo (#954B6E),
color/bg/areia-acolhedora (#F2EAE4), text/h1 (Quicksand SemiBold 40px)

Imagem gerada (image-ai-generator, --mode production):
"Editorial photograph of a confident Black woman in her late 20s,
smiling softly while looking at her smartphone, natural window light,
warm neutral background in dusty wine and sandy beige tones
(#954B6E, #F2EAE4)..."

Motion aplicado (figma-use-motion): fade + translateY 16px→0 no headline
(300ms, ease-out); Smart Animate de hover no CTA (scale 1.03, 150ms).

Pendências: nenhuma.
```

## Exemplo 7: Execução de ajuste em arquivo já existente (Diego Assets)

```markdown
# Implementação Figma — Ajuste na seção Funcionalidades

Arquivo Figma: "Amparo — Landing Page" (já existente, registrado em
_memory/memories.md da execução de 2026-07-05) — atualizado, não recriado.
Mudança: adicionado o 4º card de funcionalidade (RF-CORE-07, aprovado por
Camila nesta execução) ao grid já existente. Nenhum frame ou variável
pré-existente foi removido ou renomeado.
```

## Exemplo 8: Veredito de revisão (Rafael Rigor)

```text
==============================
 VEREDITO: APROVAR COM RESSALVAS
==============================

SCORING:
| Critério                     | Score | Resumo                                       |
|-------------------------------|-------|-----------------------------------------------|
| Fidelidade de copy            | 9/10  | Ancoragem correta, CTA único por seção         |
| Fidelidade à marca/visual     | 9/10  | Paleta e tipografia seguem o spec exatamente   |
| Qualidade dos assets/motion   | 8/10  | Imagens coerentes; 1 motion sem propósito claro|
| WCAG AA (design)              | 8/10  | Contraste OK; 1 alvo de toque abaixo de 44px   |
| Consistência responsiva       | 9/10  | Frames desktop/tablet/mobile coerentes         |

OVERALL: 8.6/10

Ponto forte: a seção Prova Social usa exatamente os selos e a tipografia
especificados por Vitória, com excelente hierarquia visual.

Correção obrigatória: reduzir o alvo de toque do ícone social no rodapé
(atualmente 32×32px, frame "Landing Page / Mobile") para no mínimo 44×44px.
Correção obrigatória: o motion de parallax na seção "Como Funciona" não tem
propósito declarado por Vitória — remover ou justificar antes da aprovação final.

VERDICT: APROVAR COM RESSALVAS — 2 correções obrigatórias antes da
aprovação final do usuário no Step 9.
```
