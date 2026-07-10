---
execution: inline
agent: diego-assets
inputFile: squads/landing-page-amparo/output/especificacao-visual.md
outputFile: squads/landing-page-amparo/output/implementacao-figma.md
---

# Step 6: Construir no Figma + Gerar e Aplicar Assets

## Context Loading

Load these files before executing:
- `squads/landing-page-amparo/output/especificacao-visual.md` (Vitória) —
  design system e especificação de cada seção (layout, imagery, motion),
  aprovados no Step 5.
- `squads/landing-page-amparo/output/estrutura-conteudo.md` (Camila) —
  copy de cada seção.
- `squads/landing-page-amparo/output/inputs-e-referencias.md` (Step 1) —
  modo de execução (nova construção ou ajuste em Figma existente).
- `squads/landing-page-amparo/_memory/memories.md` — link do arquivo
  Figma de uma execução anterior, se existir.
- `pipeline/data/direcao-imagens-ia.md` — direção de imagery para geração
  de imagens.

## Instructions

### Process

1. Confirmar o modo de execução em `inputs-e-referencias.md`. Se for
   ajuste em arquivo existente, abrir o arquivo Figma registrado em
   `_memory/memories.md` e localizar as seções relevantes ao escopo do
   ajuste. Se for nova construção, carregar a skill `figma-use` (sempre
   antes de qualquer chamada a `use_figma`) e criar um novo arquivo Figma
   com nome discreto.
2. Carregar `figma-generate-library` e configurar/confirmar as variáveis
   de cor, tipografia e espaçamento espelhando `brand/design-system.md` —
   antes de construir qualquer seção.
3. Carregar `figma-generate-design` e construir cada uma das 7 seções
   definidas por Camila/Vitória, uma por vez, aplicando o copy exato e os
   valores exatos da especificação visual. Criar frames responsivos
   (desktop 1440px, tablet 768px, mobile 375px) para cada seção.
4. Para cada direção de imagery da especificação de Vitória, gerar a
   imagem via `image-ai-generator` seguindo `direcao-imagens-ia.md`
   (`--mode test` primeiro, `--mode production` após validação própria) e
   inserir no frame correto. Se `OPENROUTER_API_KEY` não estiver
   configurada, registrar a pendência e seguir com composição/tipografia
   apenas, sem bloquear a entrega.
5. Carregar `figma-use-motion` e aplicar as direções de motion
   especificadas por Vitória (entradas, micro-interações, transições)
   diretamente no protótipo — sempre com propósito declarado.
6. Compilar `implementacao-figma.md`: localização do arquivo Figma
   (nome/link), página/frames criados por seção, variáveis usadas,
   imagens geradas (com prompt), motion aplicado, e pendências técnicas.

## Output Format

```text
ARQUIVO FIGMA: {nome/link}
MODO: {nova construção | ajuste}

SEÇÃO: {NOME}
Frames: {desktop/tablet/mobile — nomes}
Variáveis usadas: {lista}
Imagem gerada: {prompt usado, ou "não aplicável"}
Motion aplicado: {descrição, ou "nenhum"}

PENDÊNCIAS TÉCNICAS
- {item, se houver}
```

## Output Example

Ver `pipeline/data/output-examples.md`, Exemplo 6 (implementação de seção
com asset gerado) e Exemplo 7 (execução de ajuste em arquivo já existente)
— o output real desta etapa cobre as 7 seções no mesmo nível de detalhe.

## Veto Conditions

Reject and redo if ANY of these are true:
1. Um valor de cor/fonte/espaçamento aplicado no Figma diverge de
   `brand/design-system.md`.
2. Um arquivo Figma novo foi criado quando já existia um registrado em
   `_memory/memories.md`, sem confirmação explícita do usuário.
3. Alguma seção especificada por Camila/Vitória não foi construída, sem
   justificativa registrada.
4. Uma imagem gerada contém imagética literal de violência/vítima.

## Quality Criteria

- [ ] Todas as seções especificadas foram construídas no Figma
- [ ] Cores/tipografia aplicadas via variáveis Figma, nunca valores soltos
- [ ] Toda imagem gerada cita o prompt exato e segue `direcao-imagens-ia.md`
- [ ] Motion aplicado apenas onde especificado, com propósito declarado
- [ ] Frames responsivos presentes para cada seção
