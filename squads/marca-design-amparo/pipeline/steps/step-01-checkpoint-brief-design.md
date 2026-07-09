---
type: checkpoint
outputFile: squads/marca-design-amparo/output/brief-design.md
---

# Step 1: Checkpoint — Brief de Design

## Contexto

Este é o checkpoint inicial do pipeline. Antes que Renata Referência possa
pesquisar cor/público e Flávia Fonte possa criar qualquer identidade
visual, a squad precisa de um brief de design aprovado pelo usuário: os
adjetivos de personalidade de marca, restrições de cor (se houver) e o
nível de discrição exigido. Este brief é o mesmo tipo de insumo já usado
pela squad-irmã design-ux-ui-amparo (agora sendo descontinuada/dividida),
mantendo o formato para preservar consistência entre as duas linhas de
trabalho de design do projeto Amparo.

## Instruções

1. Apresentar ao usuário um resumo do contexto do projeto Amparo (lido de
   `_opensquad/_memory/company.md`): público-alvo, tom de voz, problema
   central que o app resolve, e explicar que esta squad trabalha
   inteiramente via Claude Design (claude.ai/design), sem usar Figma — o
   Figma é responsabilidade de uma squad separada que lê este trabalho
   depois.
2. Perguntar ao usuário, de forma objetiva:
   - Quais 3-5 adjetivos descrevem a personalidade de marca desejada (ex.:
     acolhedor, seguro, discreto, sério, esperançoso)?
   - Existe alguma restrição de cor já definida (ex.: cor já usada em
     outro material do projeto) ou alguma cor a evitar explicitamente?
   - Algum nível de discrição visual específico já é exigido (ex.: o ícone
     do app NÃO pode de forma alguma sugerir o tema do app)?
3. Compilar a resposta do usuário em um documento estruturado e salvar em
   `squads/marca-design-amparo/output/brief-design.md` antes de prosseguir
   para o Step 3.

## Output Format

```markdown
# Brief de Design — Amparo

## Adjetivos de Personalidade de Marca
- [adjetivo 1]
- [adjetivo 2]
- [adjetivo 3]

## Restrições de Cor
[cores a evitar ou já definidas, ou "nenhuma restrição declarada"]

## Nível de Discrição Exigido
[resposta do usuário sobre exigências de discrição visual]

## Observações Adicionais
[qualquer contexto extra fornecido pelo usuário]
```

## Output Example

```markdown
# Brief de Design — Amparo

## Adjetivos de Personalidade de Marca
- Acolhedor
- Seguro
- Discreto

## Restrições de Cor
Evitar vermelho e laranja saturados — associam o app a "alarme" ou "pânico"
institucional, o que contradiz o tom acolhedor desejado.

## Nível de Discrição Exigido
O ícone do app na tela inicial do celular não pode, em nenhuma hipótese,
sugerir visualmente o tema de violência doméstica ou socorro. Nome do app
no ícone deve ser configurável/neutro.

## Observações Adicionais
Projeto é um TCC — justificativas de design devem ser citáveis e
rastreáveis para a banca avaliadora. Toda a identidade e o design system
serão publicados no Claude Design (claude.ai/design), não no Figma.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O usuário não forneceu nenhum adjetivo de personalidade de marca — não
   há brief mínimo viável para Renata pesquisar e Flávia criar a partir
   dele.
2. O documento salvo em `output/brief-design.md` está vazio ou não captura
   as respostas reais do usuário (placeholder não substituído).

## Quality Criteria

- [ ] O brief contém pelo menos 3 adjetivos de personalidade de marca.
- [ ] Restrições de cor e nível de discrição exigido estão explicitamente
      registrados, mesmo que a resposta seja "nenhuma restrição".
- [ ] O arquivo é salvo em `output/brief-design.md` antes de o Step 3
      iniciar.
