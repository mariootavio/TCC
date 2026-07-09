---
execution: inline
agent: flavia-fonte
inputFile: squads/marca-design-amparo/output/pedido.md
outputFile: squads/marca-design-amparo/output/especificacao.md
---

# Step 2: Especificar Prompt/Componente

## Context Loading

Load these files before executing:
- `squads/marca-design-amparo/output/pedido.md` — pedido do usuário, destino
  (app/landing/documentação) e roteamento (só prompt vs. implementação no
  Figma), coletados no Step 1.
- `brand/design-system.md` — especificação completa e travada: paleta hex,
  tipografia, espaçamento, radius, componentes, ícones, linguagem
  fotográfica, princípios de segurança (por completo, seções 1-14).
- `brand/LogoAmparo.svg` e `brand/manual-amparo.pdf` — logotipo oficial e
  manual completo, para checar duplicidade e regras de uso do logotipo.
- `pipeline/data/direcao-imagens-ia.md` — diretriz obrigatória para
  qualquer prompt de imagem.
- `_opensquad/_memory/company.md` — perfil do Amparo, público, tom de voz.

## Instructions

### Process

1. Ler o pedido por completo e carregar `brand/design-system.md`,
   `brand/LogoAmparo.svg` e `brand/manual-amparo.pdf` — nunca especificar
   nada sem ter carregado a fonte travada primeiro.
2. Verificar duplicidade: o pedido já está coberto por algo existente no
   design system ou no manual? Se sim, documentar isso em vez de criar algo
   redundante.
3. Classificar o pedido: (a) prompt de imagem, (b) especificação de
   componente novo, ou (c) especificação de tela/página que combina
   componentes existentes e, se necessário, um componente novo.
4. Especificar seguindo exatamente `brand/design-system.md` — toda cor,
   fonte, espaçamento ou radius citado precisa ser rastreável a uma seção
   específica. Para prompt de imagem, seguir
   `pipeline/data/direcao-imagens-ia.md` e a seção 10 (Linguagem
   Fotográfica) à risca.
5. Decidir e registrar o roteamento com base no que o usuário indicou no
   Step 1: "entrega final deste ciclo" (só prompt/especificação) ou "segue
   para Tomás Tokens (Step 4)" (implementação real no Figma).
6. Salvar a especificação completa em
   `squads/marca-design-amparo/output/especificacao.md`.

## Output Format

```
PEDIDO ORIGINAL: {pedido do Step 1}
VERIFICAÇÃO DE DUPLICIDADE: {"não existe equivalente" | "já existe em [seção/página] — ver nota abaixo"}
TIPO DE ENTREGA: {prompt de imagem | especificação de componente | especificação de tela/página}
ROTEAMENTO: {entrega final deste ciclo | segue para implementação no Figma}

{especificação completa — anatomia/tokens usados com origem exata, ou prompt de imagem completo}
```

## Output Example

Ver `pipeline/data/output-examples.md` (Exemplos 1 e 2 de Flávia Fonte) —
especificação de componente novo e prompt de imagem, respectivamente, com o
mesmo nível de rastreabilidade e detalhe esperado aqui.

## Veto Conditions

Reject and redo if ANY of these are true:
1. Alguma cor, fonte, espaçamento, radius ou uso do logotipo citado não é
   idêntico a um valor documentado em `brand/design-system.md`/
   `brand/LogoAmparo.svg`.
2. A verificação de duplicidade não foi feita ou não está documentada.
3. O roteamento (só prompt vs. implementação no Figma) não está explícito.
4. Um prompt de imagem viola qualquer regra trauma-informada inegociável de
   `pipeline/data/direcao-imagens-ia.md`.

## Quality Criteria

- [ ] Toda cor/fonte/espaçamento citado é rastreável a uma seção específica
      de `brand/design-system.md`.
- [ ] A verificação de duplicidade está documentada explicitamente.
- [ ] O roteamento do output está registrado sem ambiguidade.
- [ ] Componentes/telas novos têm nomenclatura atômica consistente com o
      padrão já usado no design system.
