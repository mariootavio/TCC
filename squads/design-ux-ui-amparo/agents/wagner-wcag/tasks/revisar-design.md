---
task: "Revisar Design"
order: 1
input: |
  - telas_prototipo: Telas de alta fidelidade e protótipo navegável entregues por Telma — squads/design-ux-ui-amparo/output/telas-prototipo.md
  - design_system: Design system aprovado — squads/design-ux-ui-amparo/output/design-system.md
  - fluxos_ux: Fluxos de UX aprovados — squads/design-ux-ui-amparo/output/fluxos-ux.md
  - quality_criteria: Critérios de qualidade da squad — squads/design-ux-ui-amparo/pipeline/data/quality-criteria.md
output: |
  - revisao_design: Veredito estruturado (scoring table + feedback + caminho de aprovação) — squads/design-ux-ui-amparo/output/revisao-design.md
---

# Revisar Design

Revisão completa e estruturada das telas de alta fidelidade e do protótipo
navegável contra os critérios de design system, acessibilidade, usabilidade e
marca, produzindo scoring table e veredito de APROVAR/REJEITAR/APROVAR COM
RESSALVAS.

## Process

1. Carregar todos os critérios de referência antes de revisar qualquer tela: o
   design system aprovado, os fluxos de UX aprovados, o brief de marca e
   `pipeline/data/quality-criteria.md` — entender o que é "bom" antes de avaliar.
   Para inspecionar o Figma diretamente (`get_design_context`, `get_screenshot`),
   essas ferramentas de leitura não exigem a skill `figma-use` (que é só para
   escrita via `use_figma`).
2. Percorrer TODAS as telas e o protótipo completo do início ao fim pelo menos
   uma vez antes de pontuar qualquer critério — nunca avaliar por amostragem.
3. Pontuar cada critério individualmente em escala 1-10 com justificativa
   escrita: (a) Consistência com design system, (b) Acessibilidade WCAG 2.2 AA,
   (c) Heurísticas de Nielsen, (d) Aderência à marca e tom acolhedor/discreto,
   (e) Integridade do protótipo navegável, (f) Padrões de segurança/discrição.
4. Tratar qualquer violação dos requisitos de segurança/discrição como gatilho
   de rejeição automática, independente da média geral das outras notas.
5. Calcular o veredito conforme a tabela de decisão (média ≥7 sem critério <4 e
   sem gatilho violado = APROVAR; caso contrário REJEITAR ou APROVAR COM
   RESSALVAS conforme a regra aplicável).
6. Para toda rejeição, identificar a tela/componente exato (frame, página) e
   fornecer a correção específica. Reconhecer pelo menos um "Ponto forte:" com
   exemplo concreto, mesmo em veredito de rejeição. Registrar o número da
   revisão atual e entregar o veredito em `output/revisao-design.md`.

## Output Format

```yaml
revisao_design:
  revisao_numero: "X de 3"
  data: "YYYY-MM-DD"
  scoring:
    - criterio: "string"
      nota: 0
      resumo: "string — com 'porque'"
  media_geral: 0.0
  gatilho_seguranca_violado: true | false
  veredito: "APROVAR | REJEITAR | APROVAR COM RESSALVAS"
  pontos_fortes: ["string"]
  correcoes_obrigatorias:
    - frame: "string"
      pagina: "string"
      problema: "string"
      correcao: "string"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
==============================
 VEREDITO DA REVISÃO: REJEITAR
==============================
Revisão: 1 de 3

| Critério                          | Nota  | Resumo |
|------------------------------------|-------|--------|
| Consistência com design system     | 8/10  | 1 cor hardcoded detectada |
| Acessibilidade WCAG 2.2 AA          | 6/10  | 3 botões abaixo do touch target |
| Padrões de segurança/discrição      | 3/10  | Saída rápida ausente em 4 das 22 telas |
MÉDIA GERAL: 6.5/10

GATILHO DE REJEIÇÃO AUTOMÁTICA: Padrões de segurança/discrição pontuou 3/10 —
rejeição obrigatória independente da média geral.

Correção obrigatória: o botão de saída rápida está ausente nos frames
"Modal-Captura" e "Modal-Confirmação-Denúncia" (página "04. Fluxo de
Denúncia"). Adicionar o componente App-Header a esses frames.

Ponto forte: a Tela Neutra de saída rápida está bem executada nas telas em
que o botão está presente — o disfarce é convincente.

CAMINHO PARA APROVAÇÃO: 1) Adicionar saída rápida aos frames listados. 2)
Ajustar touch target dos botões afetados. 3) Resubmeter como Revisão 2.

VEREDITO: REJEITAR — gatilho de segurança automático.
```

## Quality Criteria

- [ ] Toda nota tem justificativa escrita com "porque".
- [ ] Toda correção obrigatória aponta o frame/página exato e a correção
      específica.
- [ ] O veredito é consistente com as regras de decisão (média ≥7 sem critério
      <4 e sem gatilho = APROVAR; qualquer um violado = REJEITAR).
- [ ] A revisão contém ao menos um "Ponto forte:" mesmo em veredito de rejeição.

## Veto Conditions

Reject and redo if ANY are true:
1. A revisão foi produzida sem percorrer 100% das telas e do protótipo
   completo (avaliação por amostragem).
2. Uma violação de padrão de segurança/discrição recebeu veredito APROVAR
   apenas por "compensação" da média geral.
