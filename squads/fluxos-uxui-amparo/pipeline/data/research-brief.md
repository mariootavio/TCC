# Research Brief — Fluxos & UI/Protótipo Amparo

Research brief consolidado desta squad: UX de segurança e discrição, WCAG 2.2
AA, boas práticas de prototipagem navegável no Figma, e o resumo do
benchmarking de apps já levantado pela squad `tcc-documentacao`. Este brief
não repesquisa o que outras squads já levantaram — reutiliza e cita a fonte
original.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## UX de Segurança e Discrição

Referência principal: Safety Net Project (techsafety.org), guia "Choosing and
Using Apps: Considerations for Survivors".

Padrões-chave: disguise/mask mode (app se disfarça como algo neutro); saída
rápida (quick exit) em no máximo 1 toque de qualquer tela; notificações sem
preview de conteúdo na tela de bloqueio; minimização de rastro no histórico do
sistema/app-switcher.

Exemplo real: Aspire News App (disfarce completo como app de notícias).

Fontes: techsafety.org/choosingapps; PanicGuard (Mask Mode); domesticshelters.org;
Malwarebytes Labs (rastro digital).

Uso nesta squad: esta pesquisa fundamenta diretamente os 4 padrões definidos
por Daniela Discrição (Step 4) — saída rápida, modo disfarçado (RF-CORE-02),
notificações neutras, e minimização de rastro no sistema. Esses padrões são
tratados como requisito de primeira classe, definidos ANTES de qualquer fluxo
de funcionalidade comum ser desenhado por Joana Jornada (Step 5).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Acessibilidade Mobile — WCAG 2.2 AA

| Critério WCAG 2.2 | Exigência |
|---|---|
| 1.4.3 Contraste (mínimo) | 4.5:1 texto normal, 3:1 texto grande/componentes UI |
| 2.5.8 Tamanho do Alvo (mínimo) | 24x24px mínimo para elementos interativos |
| 2.4.11 Foco Não Obscurecido | Estado de foco nunca coberto por outro elemento |
| 2.5.7 Movimentos de Arraste | Toda interação por arrasto precisa de alternativa de toque único |
| 3.2.6 Ajuda Consistente | Posição estável de mecanismos de ajuda/saída entre telas |

Fontes: W3C WCAG 2.2 (especificação oficial); WCAG2Mobile (W3C); TestParty;
Deque Systems.

Uso nesta squad: estes 5 critérios são a base mínima de auditoria de Wagner
WCAG (Step 9), complementados pela auditoria completa dos 4 princípios POUR
(Perceivable, Operable, Understandable, Robust) via skill `wcag-audit-patterns`,
e pela verificação de contraste que Caio Componentes já faz ao reconstruir o
design system no Figma (Step 2).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Prototipagem Navegável no Figma

Separar fluxos por página dentro do arquivo Figma. Usar overlays para
modais/alertas/confirmações — nunca duplicar telas inteiras para representar
um estado temporário. Interactive Components para estados de componente
(hover, pressed). Smart Animate para transições com continuidade visual —
depende de nomenclatura consistente de camadas entre frames de estado
equivalente. Planejar as interações desde o início de cada fluxo. Testar a
navegação completa antes da entrega — sem telas mortas, sem links quebrados.

Fontes: Figma (High-Fidelity Prototyping); Figma Best Practices; Figma Help
Center.

Uso nesta squad: estrutura a divisão de trabalho entre Telma Tela (telas
estáticas, organizadas por página/fluxo, nomenclatura consistente de frames)
e Pietro Prototipagem (conexões, overlays, Interactive Components, Smart
Animate, teste de navegação completa). A única exceção a essas boas práticas
é a regra de transição instantânea (nunca Smart Animate) na saída rápida,
definida por Daniela Discrição e tratada como inegociável por Pietro.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Benchmarking de Apps (resumo — fonte completa em squads/tcc-documentacao/pipeline/data/research-brief.md)

| App | Diferencial | Gap conhecido | Uso no design Amparo |
|---|---|---|---|
| PenhaS | Curadoria humana + tecnologia | Depende de acionamento manual | Reforça necessidade de ação de emergência sempre visível |
| Circle of 6 | UX de 2 toques, discrição social | Sem integração com legislação BR | Inspira meta de baixa fricção |
| bSafe | Evidência forense (vídeo+geo+timestamp) | Armazenamento local vulnerável | Fluxo de documentação prevê backup seguro |

Uso nesta squad: este benchmarking fundamenta decisões de Iara Informação
(classificação de ações globais inspirada na exigência de baixa fricção) e
de Joana Jornada (fluxo de documentação de evidências com backup,
referenciando o gap de armazenamento local vulnerável do bSafe, já fechado
pela Ideia 3 do backlog priorizado do brainstorm — "Backup criptografado
automático em nuvem para evidências").

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Fontes Reutilizadas, Não Repesquisadas

Esta squad reutiliza, sem repesquisar:
- O backlog priorizado de ideias e as 5 RF-CORE da squad `brainstorm-amparo`
  (`squads/brainstorm-amparo/output/.../ideias-brainstorm.md` e
  `squads/brainstorm-amparo/pipeline/data/research-brief.md`).
- O design system e identidade visual publicados pela squad
  `marca-design-amparo` no Claude Design (lido via `DesignSync` por Caio
  Componentes).
- O benchmarking de apps e dados de violência doméstica já levantados pela
  squad `tcc-documentacao`
  (`squads/tcc-documentacao/pipeline/data/research-brief.md`).
