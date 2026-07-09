# Quality Criteria — Extensão de Marca & Design System Amparo

> Compilação dos `Quality Criteria` de cada agente desta squad
> reformulada. Usado por Marina Marca como rubrica de auditoria e por todos
> os agentes como critério de autoavaliação antes de apresentar qualquer
> artefato a um checkpoint.

## Critério Transversal Bloqueante — Fidelidade ao Design System Aprovado

Toda cor (hex), fonte, valor de espaçamento/radius, logotipo ou ícone
usado por qualquer agente desta squad deve ser **idêntico** ao documentado
em `brand/design-system.md` e `brand/LogoAmparo.svg`. Qualquer proposta de
valor diferente — mesmo apresentado como "alternativa" ou "melhoria" — é
FALHA CRÍTICA e gatilho de rejeição automática na auditoria de Marina.

## Critério Transversal Bloqueante — Integridade do que Já Existe

Nada que já existia antes do ciclo atual — componente, token, página do
manual, frame do Figma — pode ter sido alterado, movido ou apagado.
Qualquer violação é FALHA CRÍTICA e gatilho de rejeição automática, no
mesmo nível de severidade do critério de fidelidade acima.

## Flávia Fonte — Especificação de Conceito & Prompts

- Toda cor/fonte/espaçamento/radius citado é rastreável a uma seção
  específica de `brand/design-system.md`.
- A verificação de duplicidade foi feita e documentada explicitamente
  antes de propor qualquer componente/tela/página nova.
- Todo prompt de imagem segue 100% as regras trauma-informadas de
  `pipeline/data/direcao-imagens-ia.md`.
- O roteamento do output (só prompt vs. segue para Figma) está explícito.
- Todo componente/tela nova tem nomenclatura atômica consistente com o
  padrão já usado no design system.

## Tomás Tokens — Implementação em Figma (MCP)

- Todo valor visual usado na implementação é rastreável a um
  token/variável Figma existente ou a um valor literal de
  `brand/design-system.md` — nenhum valor novo.
- Nenhum componente/frame pré-existente foi editado, movido ou apagado.
- O arquivo/página Figma usado foi confirmado (não assumido) antes da
  implementação.
- A skill `figma-use` foi carregada antes de qualquer chamada a
  `use_figma`.
- Nomenclatura atômica do novo componente é consistente com o padrão já
  usado no arquivo.
- Quando o roteamento não pedia implementação, o step foi marcado
  corretamente como "não aplicável", sem trabalho inventado.

## Marina Marca — Auditoria de Fidelidade

- Toda nota atribuída tem justificativa escrita de ao menos uma frase.
- A fidelidade de cada valor visual foi verificada de forma independente,
  não apenas copiada do que Flávia/Tomás documentaram.
- A integridade do que já existia (nada alterado) foi confirmada
  explicitamente, comparando antes/depois quando houve implementação no
  Figma.
- Toda correção obrigatória aponta a localização exata (arquivo, seção do
  design system, ou frame/página do Figma).
- O veredito final é consistente com a regra de decisão.
- Existe ao menos um "Ponto forte:" explícito, mesmo em rejeição.

## Helena Manual — Documentação de Extensões

- Nenhuma entrada documenta como definitivo algo que Marina reprovou ou
  marcou como pendente de correção sem confirmação.
- Toda entrada é executável sem interpretação (hex, fonte, valor numérico,
  localização exata).
- Toda entrada é datada e cita o pedido original e o veredito de Marina.
- `brand/manual-amparo.pdf` e `brand/design-system.md` permanecem
  inalterados — toda documentação nova vive em
  `output/manual-extensoes.md`.
- A entrada foi anexada ao final do apêndice, sem remover ou reescrever
  entradas anteriores.

## Tabela de Decisão de Veredito (Marina Marca)

| Condição | Veredito |
|---|---|
| Média geral ≥ 7/10 e nenhum critério < 4/10 e nenhum gatilho de fidelidade/integridade/discrição violado | APROVAR |
| Média geral ≥ 7/10 e algum critério não-crítico entre 4-6/10 | APROVAR COM RESSALVAS |
| Média geral < 7/10 | REJEITAR |
| Qualquer critério < 4/10 | REJEITAR (gatilho automático) |
| Qualquer gatilho de fidelidade, integridade ou discrição/trauma-informado violado | REJEITAR (gatilho automático, independente da média) |

## Critérios Transversais (aplicam-se a toda a squad)

- Toda escolha visual é rastreável a `brand/design-system.md` — nunca
  apresentada como preferência estética sem essa origem.
- Nenhum artefato é apresentado a um checkpoint sem que o agente
  responsável tenha verificado seus próprios quality criteria primeiro.
- Todo ciclo desta squad é extensão (algo novo) ou documentação/prompt
  (texto) — nunca alteração do que já existe em `brand/`.
