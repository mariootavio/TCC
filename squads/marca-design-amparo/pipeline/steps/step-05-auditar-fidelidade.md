---
execution: inline
agent: marina-marca
inputFile: squads/marca-design-amparo/output/implementacao-figma.md
outputFile: squads/marca-design-amparo/output/auditoria.md
---

# Step 5: Auditar Fidelidade

## Context Loading

Load these files before executing:
- `brand/design-system.md` e `brand/LogoAmparo.svg` — fonte travada contra
  a qual tudo é auditado.
- `squads/marca-design-amparo/output/especificacao.md` — especificação de
  Flávia Fonte (Step 2/3).
- `squads/marca-design-amparo/output/implementacao-figma.md` —
  implementação (ou registro de "não aplicável") de Tomás Tokens (Step 4).
- `pipeline/data/quality-criteria.md` — critérios completos de auditoria.

## Instructions

### Process

1. Ler a especificação e a implementação (ou o registro de "não
   aplicável") por completo antes de pontuar qualquer critério — nunca
   avaliar por amostragem.
2. Auditar fidelidade: cada valor visual (cor, fonte, espaçamento, radius,
   uso do logotipo) usado precisa ser idêntico a um valor documentado em
   `brand/design-system.md`/`brand/LogoAmparo.svg`.
3. Auditar integridade: se houve implementação no Figma, confirmar de
   forma independente que nenhum componente/token/frame pré-existente foi
   alterado, movido ou apagado — comparar o que Tomás documentou contra o
   que deveria ter permanecido intocado.
4. Verificar duplicidade de forma independente: o que foi criado preenche
   mesmo uma lacuna real?
5. Verificar conformidade trauma-informada: nenhuma imagética literal de
   violência, cores funcionais (`Alerta SOS`/`Confirmação Guardião`)
   usadas só no contexto restrito já definido, nenhuma exposição do
   propósito do app.
6. Pontuar cada critério (1-10) com justificativa escrita, calcular o
   veredito conforme a regra de decisão, incluir ao menos um "Ponto
   forte:", e salvar em `squads/marca-design-amparo/output/auditoria.md`.

## Output Format

Ver `pipeline/data/output-examples.md` (Exemplos 1 e 2 de Marina Marca) —
formato de veredito com tabela de pontuação, gatilho de rejeição
automática (se houver), pontos fortes e correções obrigatórias com
localização exata.

## Output Example

Ver `pipeline/data/output-examples.md` (Exemplos 1 e 2 de Marina Marca).

## Veto Conditions

Reject and redo if ANY of these are true:
1. Menos de 100% do material do ciclo foi revisado.
2. Algum critério recebeu nota sem justificativa escrita.
3. O contraste/fidelidade de token não foi verificado de forma
   independente (apenas copiado do que Flávia/Tomás documentaram).
4. O veredito final não é consistente com a tabela de pontuação e as
   regras de decisão.

## Quality Criteria

- [ ] 100% do material do ciclo foi revisado, nunca por amostragem.
- [ ] Fidelidade de tokens/logo verificada de forma independente.
- [ ] Integridade do que já existia (nada alterado) confirmada
      explicitamente quando houve implementação no Figma.
- [ ] Toda correção obrigatória aponta localização exata.
- [ ] Existe ao menos um "Ponto forte:" explícito, mesmo em rejeição.
