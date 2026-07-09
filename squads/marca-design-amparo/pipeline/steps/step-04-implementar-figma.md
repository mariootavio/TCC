---
execution: inline
agent: tomas-tokens
inputFile: squads/marca-design-amparo/output/especificacao.md
outputFile: squads/marca-design-amparo/output/implementacao-figma.md
---

# Step 4: Implementar no Figma (MCP)

## Context Loading

Load these files before executing:
- `squads/marca-design-amparo/output/especificacao.md` — especificação
  aprovada de Flávia Fonte (Step 3), incluindo o roteamento decidido.
- `squads/marca-design-amparo/output/pedido.md` — contexto do arquivo
  Figma informado (ou não) pelo usuário no Step 1.
- `brand/design-system.md` e `brand/LogoAmparo.svg` — fonte travada de
  todo valor visual usado na implementação.

## Instructions

### Process

1. Verificar o roteamento registrado na especificação de Flávia. Se for
   "entrega final deste ciclo" (só prompt/especificação, sem implementação
   no Figma), NÃO executar nenhuma ação de Figma — registrar
   `implementacao-figma.md` como "Não aplicável neste ciclo — entrega foi
   a especificação/prompt do Step 2" e parar aqui.
2. Se o roteamento pedir implementação, carregar a skill `figma-use`
   (obrigatório antes de qualquer chamada a `use_figma`) e, conforme o
   tipo de entrega, também `figma-generate-library` (componente com
   variantes/tokens) ou `figma-generate-design` (tela/página composta).
3. Confirmar com o usuário qual arquivo/página do Figma usar, se não
   estiver claro pelo Step 1 — nunca assumir ou criar um arquivo novo sem
   essa confirmação explícita.
4. Implementar exclusivamente com tokens/variáveis/estilos já existentes
   no arquivo Figma, ou os valores literais de `brand/design-system.md` na
   ausência de uma variável equivalente — nunca criar um token/estilo novo.
5. Nomear o novo componente/frame com nomenclatura atômica consistente com
   o padrão já usado no arquivo Figma. Adicionar como elemento novo, nunca
   editar, mover ou apagar algo que já existia.
6. Registrar o resultado completo (localização no Figma, tokens usados e
   origem) em `squads/marca-design-amparo/output/implementacao-figma.md`.

## Output Format

```
ROTEAMENTO CONFIRMADO: {"não aplicável — entrega já foi o prompt/especificação" | "implementação executada"}

(se implementação executada:)
ARQUIVO FIGMA: {nome do arquivo/projeto}
PÁGINA/FRAME: {localização exata}
COMPONENTE(S) CRIADO(S): {nome com nomenclatura atômica}
TOKENS/VALORES USADOS: {lista, cada um com origem em brand/design-system.md ou variável Figma existente}
CONFIRMAÇÃO: nenhum componente/token pré-existente foi alterado, movido ou apagado.
```

## Output Example

Ver `pipeline/data/output-examples.md` (Exemplos 1 e 2 de Tomás Tokens) —
implementação de componente novo e registro de step "não aplicável",
respectivamente.

## Veto Conditions

Reject and redo if ANY of these are true:
1. `use_figma` foi chamado sem antes carregar a skill `figma-use`.
2. Algum valor visual usado na implementação não é rastreável a um
   token/variável Figma existente ou a `brand/design-system.md`.
3. Um componente/frame pré-existente foi editado, movido ou apagado.
4. Uma implementação foi executada mesmo quando o roteamento indicava "só
   prompt/especificação".

## Quality Criteria

- [ ] O roteamento foi verificado antes de qualquer ação de Figma.
- [ ] Todo valor visual é rastreável a um token/variável existente ou a
      `brand/design-system.md` — nenhum valor novo.
- [ ] Nenhum elemento pré-existente do arquivo Figma foi alterado.
- [ ] Nomenclatura atômica do novo componente é consistente com o padrão
      já usado no arquivo.
