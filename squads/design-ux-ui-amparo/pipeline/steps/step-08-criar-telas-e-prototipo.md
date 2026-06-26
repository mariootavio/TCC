---
execution: inline
agent: telma-tela
inputFile: squads/design-ux-ui-amparo/output/fluxos-ux.md
outputFile: squads/design-ux-ui-amparo/output/telas-prototipo.md
---

# Step 8: Criar Telas e Protótipo

## Context Loading

Load these files before executing:
- `squads/design-ux-ui-amparo/output/fluxos-ux.md` — fluxos de UX aprovados no checkpoint anterior (Step 7)
- `squads/design-ux-ui-amparo/output/design-system.md` — design system aprovado (componentes e tokens)
- `squads/design-ux-ui-amparo/pipeline/data/research-brief.md` — pesquisa de prototipagem navegável no Figma (seção 5)
- `squads/design-ux-ui-amparo/pipeline/data/quality-criteria.md` — critérios de qualidade de Telma Tela
- `squads/design-ux-ui-amparo/agents/telma-tela/tasks/criar-telas-alta-fidelidade.md`
- `squads/design-ux-ui-amparo/agents/telma-tela/tasks/montar-prototipo-navegavel.md`

## Instructions

### Process

1. Executar a task `criar-telas-alta-fidelidade.md`: antes de qualquer chamada
   a `use_figma`, invocar `figma:figma-use` junto com `figma:figma-generate-design`.
   Organizar o Figma em páginas por fluxo, usando exclusivamente componentes e
   tokens do design system aprovado — sinalizar qualquer lacuna em vez de
   criar estilo ad-hoc.
2. Verificar em cada tela criada: touch target mínimo 24x24px, contraste
   conforme tokens semânticos, posição consistente do botão de saída rápida
   (WCAG 3.2.6), foco visível não obscurecido (WCAG 2.4.11).
3. Executar a task `montar-prototipo-navegavel.md`: conectar as telas usando
   overlays para modais/confirmações, Interactive Components para estados de
   botão, e Smart Animate para transições com continuidade visual — exceto a
   saída rápida, que usa transição "Instant".
4. Testar a navegação completa do protótipo por todos os fluxos críticos:
   nenhum link quebrado, nenhuma tela morta, incluindo o caminho de saída
   rápida funcionando de qualquer ponto.
5. Consolidar tudo em `output/telas-prototipo.md` e apresentar o link do
   protótipo — o próximo step (Step 9, Wagner) faz a revisão antes da
   aprovação final do usuário.

## Output Format

The output MUST follow this exact structure:
```markdown
# Telas e Protótipo — Amparo

## Organização do Arquivo Figma
[lista de páginas por fluxo]

## Telas Criadas
### [Página: nome] / [Frame: nome]
Fluxo de origem: [referência ao fluxo de Joana]
Componentes usados: [lista]
Verificação de acessibilidade: [touch target, contraste, foco]
(repetir por tela relevante)

## Protótipo Navegável
Link Figma: [link]
Conexões mapeadas: [lista origem → destino, tipo de transição]
Verificação de navegação completa: [resultado do teste — frames sem conexão, caminho de saída rápida testado]

## Próximo Passo
Encaminhado para revisão de Wagner WCAG antes da aprovação final.
```

## Output Example

```markdown
# Telas e Protótipo — Amparo

## Organização do Arquivo Figma
"03. Onboarding", "04. Fluxo de Denúncia", "05. Modo Discreto e Saída Rápida",
"06. Rede de Apoio"

## Telas Criadas

### Página "04. Fluxo de Denúncia" / Frame "Emergência - Confirmação"
Fluxo de origem: definir-padroes-seguranca-discrecao.md (Joana), Estado 2
Componentes usados: Button/Emergency/Large, Alert-Banner, App-Header
Verificação de acessibilidade: touch target 56x56px (Button), contraste
8.1:1, saída rápida no canto superior direito (posição idêntica nas 18
telas do fluxo).

## Protótipo Navegável
Link Figma: figma.com/proto/amparo-design-system/amparo-mvp
Conexões mapeadas: [Qualquer tela] --saída rápida (Instant)--> [Tela Neutra];
[Tela Neutra] --toque longo 1.5s (Smart Animate)--> [Tela Início]; [Lista de
Registros] --"+ Novo Registro" (Overlay)--> [Modal: Escolher tipo de captura]

Verificação de navegação completa: 22 frames, 0 sem conexão, caminho de
saída rápida testado a partir de cada um dos 22 frames — nenhuma tela morta.

## Próximo Passo
Encaminhado para revisão de Wagner WCAG antes da aprovação final.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Alguma tela usa estilo visual fora do design system aprovado, sem
   sinalizar como lacuna.
2. O teste de navegação completa não foi executado, ou identificou tela
   morta/link quebrado não corrigido antes da entrega.

## Quality Criteria

- [ ] 100% dos elementos visuais correspondem a token/componente do design
      system aprovado.
- [ ] O botão de saída rápida aparece na posição idêntica em 100% das telas.
- [ ] O protótipo permite percorrer as 4 jornadas críticas sem tela morta.
- [ ] As skills `figma:figma-use` e `figma:figma-generate-design` foram
      carregadas antes das chamadas de criação de tela no Figma.
