# Domain Framework — Fluxos & UI/Protótipo Amparo

Framework operacional consolidado para os 7 agentes da squad. A squad
transforma em Figma (telas reais + protótipo navegável) o que as squads
`brainstorm-amparo` (backlog priorizado) e `marca-design-amparo` (design
system, via Claude Design) já produziram — nenhum agente desta squad
repesquisa ou inventa conteúdo que já existe nessas fontes.

**Design system travado:** a identidade visual e o design system do Amparo
já estão finalizados e aprovados em `brand/design-system.md` (especificação
completa: paleta hex, tipografia, espaçamento, componentes) e
`brand/LogoAmparo.svg` (logo vetorial oficial) — ver `brand/README.md`.
Esses arquivos são a fonte primária e mais confiável (sempre disponíveis,
independente do estado do projeto Claude Design). Todo agente desta squad
que reconstruir tokens/componentes/logo no Figma deve usar exatamente os
valores de `brand/design-system.md`/`brand/LogoAmparo.svg` — nunca um valor
novo, ajustado ou "melhorado".

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Visão Geral do Fluxo

```
Caio (reconstrói design system no Figma)
   → Iara (mapeia arquitetura de informação, usando o backlog do brainstorm)
   → Daniela (define padrões de segurança/discrição — RF-CORE-02 operacionalizado)
   → Joana (desenha fluxos de UX, ancorados ao backlog, respeitando IA + segurança)
   → [checkpoint: aprovar fluxos]
   → Telma (cria telas de alta fidelidade, usando exclusivamente o design system de Caio)
   → Pietro (monta protótipo navegável, conecta as telas de Telma)
   → Wagner (revisa: design system, WCAG 2.2 AA + POUR, heurísticas, integridade do protótipo)
   → [checkpoint: aprovação final]
```

Cada etapa depende estritamente da anterior — nenhuma etapa pode ser
adiantada ou pulada. A squad tem dois checkpoints intermediários (Step 1,
seleção de inputs; Step 6, aprovação de fluxos) e um checkpoint final
(Step 10).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 1. Caio Componentes — Fundação do Design System

Lê `brand/design-system.md` e `brand/LogoAmparo.svg` (fonte primária e
travada) e reconstrói fielmente tokens (Figma Variables) e componentes
(hierarquia atômica, Variant Properties) no Figma. A squad `marca-design-
amparo` foi reformulada e agora estende esse mesmo design system sob
demanda (novos componentes/telas, implementados diretamente no Figma via
MCP) — se ela já tiver adicionado algo relevante ao arquivo Figma, usar
como complemento/cross-check (`output/manual-extensoes.md` da squad lista
o que foi adicionado e onde). Princípio central: tradução fiel, nunca
reinterpretação. Ausência de informação na
fonte = pendência explícita, nunca valor inventado.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 2. Iara Informação — Arquitetura de Informação

Mapeia todas as funcionalidades do backlog real do brainstorm (RF-CORE +
ideias priorizadas por RICE) em Navegação Principal, Ação Global ou Ação
Secundária/Contextual. Nunca mapeia uma funcionalidade fora do backlog real —
lacunas são sinalizadas, nunca preenchidas com invenção.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 3. Daniela Discrição — Segurança e Discrição UX

Operacionaliza o RF-CORE-02 (já decidido pelo product owner) em padrões
concretos: saída rápida (posição fixa, transição instantânea), modo
disfarçado, notificações neutras, minimização de rastro no sistema. Define
isso ANTES de qualquer fluxo comum ser desenhado — requisito de primeira
classe, não adendo.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 4. Joana Jornada — Fluxos de UX

Desenha as jornadas críticas ponta a ponta, aplicando simultaneamente a
arquitetura de Iara e os padrões de Daniela. Toda jornada cita
explicitamente o RF-CORE/ideia do backlog que implementa. Mapeia caminho
feliz E caminho de erro em todo fluxo crítico, nomeando a heurística de
Nielsen aplicada em cada decisão.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 5. Telma Tela — Telas de Alta Fidelidade

Traduz os fluxos aprovados de Joana em telas, usando exclusivamente os
componentes/tokens já reconstruídos por Caio. Nunca cria estilo novo
ad-hoc — sinaliza pendência para Caio. Não monta protótipo — entrega
estática, organizada por página/fluxo.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 6. Pietro Prototipagem — Protótipo Navegável

Conecta as telas de Telma: overlays para temporários, Interactive Components
para estados de botão, Smart Animate para continuidade visual — EXCETO na
saída rápida, que é sempre transição instantânea. Testa 100% da navegação
crítica antes de entregar.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 7. Wagner WCAG — Revisão de Design

Avalia 100% das telas e do protótipo (nunca por amostragem): design system,
WCAG 2.2 AA + auditoria POUR completa (skill `wcag-audit-patterns`),
heurísticas de Nielsen, integridade do protótipo. Qualquer violação de
segurança/discrição definida por Daniela é gatilho de rejeição automática,
independente da média geral. Veredito: APROVAR / REJEITAR / APROVAR COM
RESSALVAS.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Resumo de Responsabilidades por Agente

| Agente | Entrada principal | Saída | Ferramenta/skill nativa principal |
|---|---|---|---|
| Caio Componentes | `brand/design-system.md` + `brand/LogoAmparo.svg` | `design-system-figma.md` + arquivo Figma | figma-use, figma-generate-library, figma-create-design-system-rules |
| Iara Informação | Backlog brainstorm-amparo + design-system-figma.md | `arquitetura-informacao.md` | — (texto/diagrama) |
| Daniela Discrição | arquitetura-informacao.md + RF-CORE-02 | `padroes-seguranca-discricao.md` | — (texto) |
| Joana Jornada | arquitetura + padrões de segurança + backlog | `fluxos-ux.md` | figma-use-figjam (opcional) |
| Telma Tela | fluxos-ux.md (aprovado) + design-system-figma.md | `telas-alta-fidelidade.md` + telas Figma | figma-use, figma-generate-design |
| Pietro Prototipagem | telas-alta-fidelidade.md + fluxos-ux.md + padrões | `prototipo-navegavel.md` + protótipo Figma | figma-use |
| Wagner WCAG | todos os outputs anteriores | `revisao-design.md` | wcag-audit-patterns |
