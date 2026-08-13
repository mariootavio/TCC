DESIGN SYSTEM RECONSTRUÍDO NO FIGMA — AMPARO
Fonte de origem: `brand/design-system.md` + `brand/LogoAmparo.svg` (fonte primária e travada, conforme checkpoint Step 1 — nenhum projeto Claude Design local foi usado).
Arquivo Figma: "App" (fileKey `uq8ZErrErmrt2lCfLPq6j3`)
Páginas criadas: 📱 Telas do App (existente, renomeada) · 🎨 Fundações · 🧩 Botão · 🧩 Botão SOS · 🧩 Input · 🧩 Card

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

TOKENS PRIMITIVOS (Figma Variables — coleção "Primitives", modo "Value")

| Token | Valor | Fonte |
|---|---|---|
| color/vinho-amparo | #954B6E | design-system.md, seção 5 "Sistema Cromático — Cor primária" |
| color/vinho-profundo | #4B2A3F | seção 5 "Cores secundárias" |
| color/malva-suave | #C58DA8 | seção 5 "Cores secundárias" |
| color/areia-acolhedora | #F2EAE4 | seção 5 "Cores secundárias" |
| color/grafite-leitura | #333333 | seção 5 "Cores neutras" |
| color/cinza-silencio | #8E8984 | seção 5 "Cores neutras" |
| color/branco-base | #FFFFFF | seção 5 "Cores neutras" |
| color/alerta-sos | #C62828 | seção 5 "Cores funcionais" |
| color/confirmacao-guardiao | #2E7D6B | seção 5 "Cores funcionais" |
| color/vinho-amparo-hover / -pressed | derivado (-10% / -15% de brilho) | seção 8 "Estados de interação" — regra aplicada, não valor novo |
| color/confirmacao-guardiao-hover / -pressed | derivado (-10% / -15%) | idem |
| color/alerta-sos-hover / -pressed | derivado (-10% / -15%) | idem |
| spacing/4…80 (10 valores) | 4·8·12·16·24·32·40·48·64·80 | seção 7 "Espaçamento" |
| radius/sm, md, lg, pill | 8·12·20·999 | seção 7 "Raios de Borda" |

TOKENS SEMÂNTICOS (coleção "Semantic", modo "Default" — sem dark mode, não documentado)

| Token | Aponta para | Uso |
|---|---|---|
| color/bg/screen | areia-acolhedora | Fundo de tela padrão |
| color/bg/surface | branco-base | Cards, inputs |
| color/bg/dark | vinho-profundo | Fundo escuro |
| color/text/body | grafite-leitura | Texto corrido |
| color/text/muted | cinza-silencio | Legendas |
| color/text/on-primary | branco-base | Texto sobre botão primário/confirmação/SOS |
| color/text/on-dark | areia-acolhedora | Texto sobre fundo escuro |
| color/text/brand | vinho-amparo | Wordmark (decisão checkpoint Caio, 2026-08-13) |
| color/action/primary | vinho-amparo | Fundo/borda de ação primária |
| color/action/primary-text | vinho-amparo | Texto do botão secundário |
| color/feedback/sos | alerta-sos | Botão SOS |
| color/feedback/confirm | confirmacao-guardiao | Botão de confirmação |
| color/border/default | cinza-silencio | Borda padrão de input |
| color/border/focus | vinho-amparo | Borda de input em foco |

TEXT STYLES (6) — Quicksand SemiBold/Medium, Nunito Sans SemiBold/Regular, Inter Regular. Fonte: seção 6 "Tipografia — Hierarquia".
EFFECT STYLE — "Sombra/Card": 0 2px 8px rgba(0,0,0,0.06). Fonte: seção 8 "Cards".

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

VERIFICAÇÃO DE CONTRASTE WCAG AA

| Par | Contraste | Status |
|---|---|---|
| text/on-primary sobre action/primary (botão primário) | 5.98:1 | ATENDE |
| action/primary-text sobre bg/surface (botão secundário) | 5.98:1 | ATENDE |
| text/body sobre bg/screen | 10.63:1 | ATENDE |
| **text/muted sobre bg/screen (legendas)** | **2.91:1** | **NÃO ATENDE (mínimo 4.5:1, nem atinge 3:1 de texto grande)** |
| text/on-dark sobre bg/dark | 10.38:1 | ATENDE |
| text/brand sobre bg/screen (wordmark) | 5.03:1 | ATENDE |
| text/on-primary sobre feedback/confirm | 4.93:1 | ATENDE |
| text/on-primary sobre feedback/sos | 5.62:1 | ATENDE |

⚠️ **Discrepância WCAG encontrada, não corrigida silenciosamente:** "Cinza Silêncio" (#8E8984) usado como `color/text/muted` sobre o fundo padrão "Areia Acolhedora" (#F2EAE4) tem contraste real de apenas 2.91:1 — abaixo até do mínimo de 3:1 para texto grande/componentes UI. Isso afeta toda legenda/texto de apoio do app. Reportado para decisão da squad `marca-design-amparo`: escurecer o neutro secundário ou restringir seu uso a fundos brancos (`bg/surface`, onde o mesmo par teria ~3.4:1 — ainda insuficiente para texto normal).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

COMPONENTES RECONSTRUÍDOS (hierarquia atômica)

- **ComponentSet "Botão"** (página 🧩 Botão) — 12 variantes: Tipo (Primário/Secundário/Confirmação) × Estado (Padrão/Hover/Pressed/Desabilitado). Fonte: seção 8 "Componentes — Botões" + "Estados de interação". Pressed aplicado como escala 98% física na variante (interação real de transição cabe a Pietro no Step 8). Desabilitado usa opacidade de nó 40%, conforme regra documentada.
- **ComponentSet "Botão SOS"** (página 🧩 Botão SOS) — 2 variantes: Padrão/Pressed. Circular (radius-pill), fundo `feedback/sos`. **Pendência:** nenhum ícone vetorial oficial de "Botão do Pânico" está disponível em `brand/` — usado rótulo textual "SOS" como placeholder até a squad `marca-design-amparo` fornecer o ícone (grid 24×24, outline, conforme seção 9).
- **ComponentSet "Input"** (página 🧩 Input) — 2 variantes: Padrão/Foco. Altura 48px (12+24+12), radius 8px, borda 1px cinza-silêncio → foco vinho-amparo. **Pendência:** estados de Erro e Desabilitado não estão documentados em design-system.md — não inventados, sinalizados para decisão humana.
- **Component "Card"** (página 🧩 Card) — radius 12px, sombra "Sombra/Card", padding 16px, fundo `bg/surface` sobre `bg/screen`. Sem variantes (nenhuma documentada).

Todos os componentes têm 100% dos fills/strokes/padding/radius vinculados a Figma Variables (auditoria de bindings: 0 valores hardcoded nos componentes reais — os únicos fills não vinculados encontrados são os frames de fundo cinza da grade de documentação, que não fazem parte da especificação de produto).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

OUTRAS DISCREPÂNCIAS DO CHECKPOINT (já resolvidas com o usuário)

1. Cor do wordmark "Amparo" (tela existente usava #5F4B6E, não documentado) → decisão do usuário: usar `color/text/brand` = Vinho Amparo (#954B6E). Aplicar essa correção na tela "Welcome Screen" é responsabilidade de Telma Tela (Step 7), não de Caio.
2. Altura do Botão Secundário (44px na tela existente vs. 48px documentado) → decisão do usuário: padronizar em 48px. Já refletido no componente reconstruído.

PENDÊNCIAS (resumo)

1. Ícone vetorial do Botão SOS ("Botão do Pânico") ausente em `brand/` — usando placeholder textual.
2. Estados de Erro/Desabilitado do Input não documentados.
3. Contraste WCAG do token `color/text/muted` sobre `color/bg/screen` não atende ao mínimo (ver seção de contraste acima) — decisão de marca pendente.

Nenhuma pendência foi preenchida com valor inventado.

NOTA DE AMBIENTE: a skill `figma:figma-create-design-system-rules`, referenciada em `domain-framework.md` e `quality-criteria.md` desta squad, não está disponível no catálogo de skills Figma instalado neste ambiente (apenas figma-use, figma-generate-library, figma-generate-design, figma-use-figjam, figma-use-slides, figma-use-motion, figma-implement-motion, figma-code-connect, figma-create-new-file, figma-design-to-code, figma-swiftui). Esta etapa específica foi pulada — Telma Tela (Step 7) deve usar este mesmo arquivo (`design-system-figma.md`) como referência de regras de uso, já que o artefato dedicado não pôde ser gerado.
