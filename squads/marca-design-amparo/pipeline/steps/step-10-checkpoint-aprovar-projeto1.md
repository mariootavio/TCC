---
type: checkpoint
inputFile: squads/marca-design-amparo/output/revisao-marca.md
---

# Step 10: Checkpoint — Aprovar Projeto 1 (Marca & Design System)

## Contexto

Marina Marca acabou de produzir o veredito estruturado (Step 9) sobre TUDO
que compõe o Projeto 1 no Claude Design — "Amparo — Marca & Design
System": o card de abertura e as direções de identidade de Flávia (Step
4), os mockups de aplicação e o design system completo de Tomás (Step 7).

Este checkpoint existe para **economizar retrabalho**: Helena Manual só
começa a construir o Projeto 2 (o segundo projeto Claude Design, com o
manual técnico e a apresentação premium para banca/investidores) DEPOIS
que o usuário aprovar explicitamente o Projeto 1 como um todo. Se o
Projeto 2 fosse construído antes dessa aprovação, qualquer correção no
Projeto 1 obrigaria a refazer trabalho de curadoria/apresentação já feito
em cima de uma base que mudou.

## Instruções

1. Apresentar ao usuário o veredito completo de Marina
   (`squads/marca-design-amparo/output/revisao-marca.md`) — tabela de
   pontuação, gatilhos de rejeição (se houver), feedback detalhado,
   veredito final — na íntegra, não resumido.
2. Informar o nome do projeto Claude Design 1 ("Amparo — Marca & Design
   System") e orientar que o usuário pode abrir diretamente em
   claude.ai/design para revisar visualmente: card de abertura, direções
   de identidade, mockups de aplicação e design system completo.
3. Explicar que a aprovação aqui é a última chance de pedir ajuste ao
   Projeto 1 ANTES de a squad começar a construir o Projeto 2 (manual +
   apresentação) em cima dele — evita retrabalho.
4. Perguntar ao usuário se ele aprova o Projeto 1 como está, ou se quer
   alguma correção antes de seguir para o Projeto 2.
5. Se aprovado: registrar a aprovação e avançar para o Step 11 (Helena
   Manual constrói o Projeto 2). Se não aprovado: registrar o feedback e
   direcionar de volta ao step relevante — Step 5 para identidade, Step 7
   para design system/mockups — sem avançar para o Step 11 até a nova
   aprovação.

## Output Format

Não há `outputFile` formal de novo conteúdo neste checkpoint. Registrar a
decisão do usuário de forma clara na conversa.

## Output Example

```
CHECKPOINT — Aprovação do Projeto 1 (Marca & Design System)

Veredito de Marina Marca: APROVAR COM RESSALVAS (média 7.8/10). Correção
obrigatória: ajuste do token color-action-emergency para terracotta-600
(contraste WCAG AA corrigido para 4.6:1) — já aplicado por Tomás.

Projeto Claude Design 1: "Amparo — Marca & Design System"
(https://claude.ai/design/... — card de abertura, 3 direções de
identidade, 3 mockups de aplicação, design system completo).

Antes de seguirmos para o Projeto 2 (manual + apresentação premium),
você aprova o Projeto 1 como está?

Decisão do usuário: Aprovado. Seguindo para o Step 11 — Helena Manual vai
construir o Projeto 2 em cima desta base aprovada.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O veredito completo de Marina não foi apresentado ao usuário antes da
   pergunta de aprovação.
2. O Step 11 (Helena, Projeto 2) foi iniciado sem uma aprovação explícita
   do usuário registrada neste checkpoint.

## Quality Criteria

- [ ] O usuário viu o veredito completo de Marina, não um resumo
      reduzido.
- [ ] O nome do projeto Claude Design 1 foi informado explicitamente.
- [ ] A decisão do usuário (aprovado / correção solicitada) está
      registrada de forma inequívoca antes de qualquer trabalho do
      Step 11 começar.
