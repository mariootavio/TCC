---
task: "Criar Telas de Alta Fidelidade"
order: 1
input: |
  - fluxos_ux: Fluxos de UX aprovados no checkpoint anterior — squads/design-ux-ui-amparo/output/fluxos-ux.md
  - design_system: Design system aprovado (componentes e tokens) — squads/design-ux-ui-amparo/output/design-system.md
output: |
  - telas_alta_fidelidade: Telas de alta fidelidade no Figma organizadas por página/fluxo — incorporado em squads/design-ux-ui-amparo/output/telas-prototipo.md
---

# Criar Telas de Alta Fidelidade

Cria as telas de alta fidelidade no Figma para as jornadas priorizadas no
brief de design, usando exclusivamente componentes e tokens do design system
aprovado, e seguindo os fluxos de UX aprovados por Joana.

## Process

1. Carregar o design system aprovado (componentes, tokens, página "02. Design
   System" do Figma) e os fluxos de UX aprovados — nunca iniciar uma tela sem
   ambos os insumos aprovados.
2. Antes de qualquer chamada à ferramenta `use_figma` para criar telas,
   invocar a skill `figma:figma-use` junto com `figma:figma-generate-design`
   (esta última ensina como traduzir um fluxo do app em telas Figma usando
   componentes e tokens já existentes, em vez de redesenhar do zero).
3. Organizar o arquivo Figma em páginas por fluxo (ex.: "03. Onboarding", "04.
   Fluxo de Denúncia", "05. Modo Discreto e Saída Rápida", "06. Rede de
   Apoio") — nunca misturar todas as telas em uma única página desorganizada.
4. Para cada tela, usar EXCLUSIVAMENTE componentes e tokens já definidos no
   design system. Se uma necessidade visual nova aparecer, sinalizar
   explicitamente como lacuna em vez de criar estilo ad-hoc.
5. Seguir o fluxo de UX exatamente como documentado, incluindo pontos de
   confirmação, estados de erro e a posição consistente do botão de saída
   rápida/ajuda em todas as telas (WCAG 3.2.6).
6. Verificar em cada tela: touch target mínimo 24x24px, contraste conforme
   tokens semânticos, foco visível não obscurecido (WCAG 2.4.11). Documentar o
   resultado em `output/telas-prototipo.md`.

## Output Format

```yaml
telas_alta_fidelidade:
  - pagina_figma: "string"
    frame: "string"
    fluxo_origem: "string — referência ao documento de Joana"
    componentes_usados: ["string"]
    verificacao_acessibilidade:
      touch_target_min: "24x24px confirmado | violação encontrada"
      contraste: "string"
      foco_visivel: "OK | obscurecido em [elemento]"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
TELA DE ALTA FIDELIDADE — AÇÃO DE EMERGÊNCIA
Página Figma: "04. Fluxo de Denúncia" / Frame: "Emergência - Confirmação"
Fluxo de origem: definir-padroes-seguranca-discrecao.md (Joana), Estado 2
Componentes usados: Button/Emergency/Large, Alert-Banner, App-Header — todos
do design system aprovado, nenhum estilo novo.

Layout (mobile, 390x844pt, grid de 16px de margem):
  - App-Header: botão de saída rápida no canto superior direito (posição
    idêntica nas 18 telas do fluxo, WCAG 3.2.6).
  - Título "heading": "Pedir ajuda agora" (tom direto, sem linguagem de pânico).
  - Alert-Banner (color-action-emergency = jade-700, não vermelho): "Isso vai
    notificar seus 3 contatos de confiança e compartilhar sua localização."
  - Button/Emergency/Large: "Confirmar e enviar" — touch target 56x56px,
    contraste 8.1:1.
  - Link "ghost": "Cancelar" — touch target 44x44px.

Estado de confirmação (prevenção de erro, Nielsen): existe para que o toque no
botão de emergência da Tela Início não dispare a ação imediatamente.

Verificação de acessibilidade: contraste, touch target e posição do botão de
saída rápida confirmados conforme checklist de qualidade.
```

## Quality Criteria

- [ ] 100% dos elementos visuais correspondem a um token ou componente do
      design system aprovado — zero estilo ad-hoc.
- [ ] O botão de saída rápida aparece na posição idêntica em todas as telas
      criadas nesta task.
- [ ] Todo elemento interativo tem touch target mínimo de 24x24px confirmado.

## Veto Conditions

Reject and redo if ANY are true:
1. Alguma tela usa um estilo visual (cor, fonte, espaçamento) que não existe
   no design system aprovado, sem sinalizar como lacuna.
2. O botão de saída rápida está ausente ou em posição diferente em qualquer
   tela criada.
