# Domain Framework — Extensão de Marca & Design System Amparo

> Compilação do `Operational Framework` de cada agente desta squad
> reformulada. A squad não cria mais identidade de marca do zero — ela
> estende, sob demanda, o design system e o manual JÁ FINALIZADOS do
> Amparo, e implementa (quando pedido) diretamente no Figma via MCP.

## AVISO CRÍTICO — Identidade e Design System JÁ FINALIZADOS

A identidade visual e o design system completo do Amparo **já foram
criados, aprovados e publicados** fora desta squad. A fonte única da
verdade está em três arquivos, na raiz do projeto:

- `brand/design-system.md` — especificação completa (paleta hex, tipografia,
  espaçamento, radius, componentes, ícones, linguagem fotográfica,
  princípios inegociáveis de segurança).
- `brand/LogoAmparo.svg` (+ `.png`/`.jpg`) — logotipo vetorial oficial.
- `brand/manual-amparo.pdf` — manual de identidade visual completo e
  publicado.

Esses três arquivos estão **travados (locked)**. Nenhum agente desta squad
gera, propõe ou sugere uma cor, fonte, logotipo, espaçamento, ícone ou tom
de voz diferente do documentado ali. O trabalho de cada agente é sempre
**extensão** (criar algo novo que ainda não existe, derivado fielmente do
que já existe) ou **documentação/prompt** (texto), nunca **alteração** do
que já foi fechado.

## Visão Geral do Fluxo Metodológico

```
Checkpoint — Captura do Pedido (o que precisa, para onde, prompt ou Figma)
        ↓
Flávia Fonte      → carrega brand/ por completo, verifica duplicidade,
                     especifica (prompt de imagem OU componente/tela novo),
                     decide o roteamento do output
        ↓ (checkpoint de aprovação da especificação/prompt)
Tomás Tokens      → SE o roteamento pedir implementação: constrói no
                     Figma via MCP, exclusivamente com tokens/logo já
                     existentes. Se não pedir, registra "não aplicável"
        ↓
Marina Marca      → audita fidelidade ao brand/ travado + integridade
                     (nada pré-existente foi alterado) + conformidade
                     trauma-informada
        ↓ (on_reject volta para Flávia Fonte, Step 2)
Helena Manual     → documenta a extensão aprovada como apêndice cronológico
                     em output/manual-extensoes.md (nunca edita o manual
                     original)
        ↓
Checkpoint de Aprovação Final do Usuário
```

A squad é pensada para rodar **um ciclo por pedido** — o usuário pode
rodá-la de novo a qualquer momento para um novo componente, tela, página
ou prompt, sempre partindo do mesmo `brand/` travado.

## 1. Framework de Flávia Fonte (Especificadora de Conceito & Prompts)

1. Carregar o pedido do checkpoint (Step 1) e `brand/design-system.md`,
   `brand/LogoAmparo.svg`, `brand/manual-amparo.pdf` por completo — nunca
   especificar sem ter carregado a fonte travada primeiro.
2. Verificar duplicidade: o pedido já está coberto por algo existente? Se
   sim, apontar isso em vez de recriar.
3. Classificar o pedido: prompt de imagem, especificação de componente
   novo, ou especificação de tela/página (app ou landing).
4. Especificar usando exclusivamente tokens/valores já existentes — toda
   cor/fonte/espaçamento citado precisa ser rastreável a uma seção
   específica de `brand/design-system.md`. Prompts de imagem seguem
   `pipeline/data/direcao-imagens-ia.md` à risca.
5. Decidir e registrar o roteamento do output (só prompt/especificação, ou
   segue para implementação no Figma) com base na resposta do usuário no
   Step 1.

## 2. Framework de Tomás Tokens (Implementador em Figma — MCP)

1. Verificar o roteamento da especificação aprovada de Flávia — se não
   pedir implementação, registrar "não aplicável" e parar, sem forçar
   trabalho de Figma.
2. Se pedir implementação: carregar a skill `figma-use` (pré-requisito
   obrigatório antes de `use_figma`) e, conforme o caso,
   `figma-generate-library` ou `figma-generate-design`.
3. Localizar/confirmar o arquivo Figma correto do Amparo (o mesmo
   construído pela squad `fluxos-uxui-amparo`) — nunca criar um arquivo
   novo sem confirmação explícita do usuário.
4. Implementar exclusivamente com tokens/variáveis/estilos já existentes
   no Figma ou valores literais de `brand/design-system.md` — nunca criar
   um token novo.
5. Adicionar como elemento novo, com nomenclatura atômica consistente —
   nunca editar, mover ou apagar algo que já existia.

## 3. Framework de Marina Marca (Auditora de Fidelidade)

1. Carregar a especificação de Flávia e a implementação (ou "não
   aplicável") de Tomás — entender o ciclo completo antes de pontuar.
2. Percorrer 100% do material, nunca por amostragem.
3. Auditar fidelidade de token/cor/fonte/logo de forma independente contra
   `brand/design-system.md`/`brand/LogoAmparo.svg`.
4. Auditar integridade: nada pré-existente (componente, token, página do
   manual, frame do Figma) pode ter sido alterado — gatilho de rejeição
   automática se violado, no mesmo nível de severidade de uma violação de
   discrição/trauma-informado.
5. Verificar duplicidade de forma independente e conformidade
   trauma-informada.
6. Pontuar cada critério com justificativa, calcular o veredito conforme a
   tabela de decisão, sempre incluindo ao menos um "Ponto forte:".

## 4. Framework de Helena Manual (Documentadora de Extensões)

1. Confirmar que o veredito de Marina foi APROVAR (ou APROVAR COM
   RESSALVAS já corrigido) — nunca documentar algo pendente como
   definitivo.
2. Redigir uma entrada nova, datada, citando o pedido original, os
   tokens/valores usados com origem exata, a localização final, e o
   veredito de Marina.
3. Escrever sem nenhuma frase genérica, seguindo a régua anti-genérico do
   skill `manual-identidade-visual-premium`.
4. Anexar ao final de `output/manual-extensoes.md` — nunca editar
   `brand/manual-amparo.pdf` ou `brand/design-system.md`, nunca reescrever
   entradas anteriores do apêndice.

## Princípio Transversal — Extensão, Nunca Alteração

Toda squad reformulada gira em torno de uma regra única: **`brand/` é
fundação fechada**. Cada agente só tem permissão de ADICIONAR algo novo e
coerente — nunca de mudar, reinterpretar ou "melhorar" o que já foi
aprovado. Isso vale para cor, fonte, espaçamento, logotipo, componente já
existente no Figma, e para o próprio `brand/manual-amparo.pdf`. Quando um
pedido do usuário parecer pedir uma mudança em algo já existente (ex.:
"muda a cor do botão primário"), isso está fora do escopo desta squad —
sinalizar isso explicitamente ao usuário em vez de executar.
