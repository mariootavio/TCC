# Output Examples — Landing Page Amparo

## Exemplo 1: Hero copy (Camila Conteúdo)

```
HEADLINE: "Você não está sozinha. Amparo está com você."
SUBHEADLINE: "Um app gratuito e discreto para pedir ajuda, registrar provas
e se conectar com uma rede de apoio em segundos — mesmo quando você não
pode falar."
CTA PRIMÁRIO: "Baixar o Amparo grátis" (ícone App Store/Play Store)
MICROCOPY DE CONFIANÇA: "100% gratuito · Discreto · Disponível 24h"
```

## Exemplo 2: Bloco de funcionalidade (Camila Conteúdo)

```
🔘 Botão de emergência discreto
Um toque silencioso aciona sua rede de confiança e compartilha sua
localização — sem alarmes, sem chamar atenção.
[ancoragem: RF-CORE-01 do backlog brainstorm-amparo]
```

## Exemplo 3: Prova social institucional (Camila Conteúdo)

```
"O Amparo segue as diretrizes da Lei Maria da Penha e foi desenvolvido em
consulta com especialistas em proteção à mulher."
[selos: Disque 180, Lei 11.340/2006, parceiros institucionais]
"+12.000 mulheres já contam com a rede de apoio do Amparo."
(estatística agregada e anônima — nunca nomes ou rostos identificáveis)
```

## Exemplo 4: Especificação da Saída Rápida (Camila Conteúdo → Fábio Front-end)

```
COMPONENTE: Botão de Saída Rápida
Posição: fixed, top-right, z-index acima de qualquer overlay/modal
Rótulo: "Sair" (com ícone X)
Comportamento ao clicar: window.location.replace('https://www.google.com')
  — imediato, sem modal de confirmação
Atalho de teclado: Esc pressionado 2x em até 1s, em qualquer página
Texto de apoio (próximo ao botão, discreto): "Isso não apaga seu
histórico — veja como navegar com segurança" (link para dicas)
Restrição: este componente NUNCA recebe whileHover/whileInView/transition
de nenhuma biblioteca de animação.
```

## Exemplo 5: Seção de design system (Vitória Visual)

```
DESIGN SYSTEM — Landing Page Amparo
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Fonte: marca-design-amparo (design-system.md, v2) — OU "PENDENTE" se
ainda não publicado, com paleta provisória abaixo claramente marcada.

Cores:
  Primária:   #6B4EFF (violeta acolhedor — CTAs, headlines)
  Secundária: #FFB4A2 (coral suave — acentos, ícones)
  Fundo:      #FFF9F5 (off-white quente)
  Texto:      #2B2530 (quase-preto, nunca preto puro)
  Sucesso/Apoio: #4CAF8C (verde institucional — selos, confirmações)

Tipografia:
  Família:   'Inter', sans-serif
  Hero:      56px / 700 (desktop) · 36px / 700 (mobile)
  Heading:   32px / 700
  Body:      18px / 500
  Caption:   14px / 500

Espaçamento: base 8px, seções com padding vertical de 96px (desktop) / 56px (mobile)
Grid: 12 colunas, max-width 1200px, gutter 24px
Border radius: 16px (cards/botões)
Contraste: todos os pares texto/fundo ≥4.5:1 (verificado)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

## Exemplo 6: Animação de seção (Mariana Movimento)

```tsx
// Padrão de scroll-reveal reutilizável (Framer Motion)
const fadeInUp = {
  hidden: { opacity: 0, y: 24 },
  visible: { opacity: 1, y: 0, transition: { duration: 0.5, ease: "easeOut" } },
};

<motion.section
  initial="hidden"
  whileInView="visible"
  viewport={{ once: true, amount: 0.3 }}
  variants={fadeInUp}
>
  {/* conteúdo da seção */}
</motion.section>

// QuickExitButton.tsx — NUNCA recebe motion/transition
export function QuickExitButton() {
  return (
    <button
      onClick={() => window.location.replace("https://www.google.com")}
      className="fixed top-4 right-4 z-[9999] ..."
      aria-label="Saída rápida"
    >
      Sair
    </button>
  );
}
```

## Exemplo 7: Veredito de revisão (Rafael Rigor)

```
==============================
 VEREDITO: APROVAR COM RESSALVAS
==============================
Revisão: 1 de 3

SCORING:
| Critério                  | Score | Resumo                                |
|----------------------------|-------|----------------------------------------|
| Fidelidade à marca         | 9/10  | Paleta e tipografia seguem o spec       |
| Qualidade de código        | 8/10  | Componentes limpos, 1 warning de hydration |
| WCAG AA                    | 9/10  | Contraste e foco OK; 1 alt text faltando |
| Core Web Vitals            | 7/10  | LCP 2.8s (meta: <2.5s) — imagem hero pesada |
| Saída Rápida                | 10/10 | Fixa, instantânea, Esc-Esc funcional    |

GATILHO DE REJEIÇÃO AUTOMÁTICA: nenhum.

Required change: otimizar a imagem do hero (atualmente 1.2MB) via next/image
com formato AVIF/WebP para trazer o LCP abaixo de 2.5s.
Required change: adicionar alt text descritivo ao ícone da seção "Como funciona".

VERDICT: APROVAR COM RESSALVAS — 2 correções obrigatórias antes da aprovação final.
```
