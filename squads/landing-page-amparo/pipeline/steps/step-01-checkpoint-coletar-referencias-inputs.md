---
type: checkpoint
outputFile: squads/landing-page-amparo/output/inputs-e-referencias.md
---

# Step 1: Checkpoint — Coletar Referências e Inputs

Este é o primeiro checkpoint do pipeline da squad Landing Page — Amparo. Antes
de iniciar qualquer trabalho de conteúdo, design ou código, explique
brevemente o contexto ao usuário: esta squad constrói uma landing page real
(código React/Next.js) para o projeto Amparo, baseada no backlog de
funcionalidades da squad `brainstorm-amparo` e — quando existir — na
identidade visual publicada pela squad `marca-design-amparo`.

Este checkpoint resolve três decisões antes de Camila Conteúdo começar:

## Instructions

1. **Caminho do projeto (OBRIGATÓRIO, pergunta sempre)**: perguntar ao
   usuário o caminho absoluto de um diretório FORA deste repositório onde o
   projeto Next.js real deve ser criado (ex.: `/Users/nome/Projects/landing-page-amparo`).
   Esta squad nunca cria o código dentro da pasta do TCC — decisão explícita
   do usuário para não sobrecarregar o projeto acadêmico com node_modules e
   build de um app Next.js. Se o usuário não souber ainda, perguntar
   novamente antes de prosseguir — este campo não tem valor padrão.
2. **Backlog de funcionalidades**: procurar a pasta de output mais recente de
   `squads/brainstorm-amparo/output/` (ordenar por timestamp do nome da pasta)
   e, dentro dela, a versão mais alta disponível contendo um arquivo de
   ideias/backlog. Se encontrada, sugerir essa rodada/versão como padrão ao
   usuário. Se nenhuma rodada existir, avisar explicitamente: "A squad
   brainstorm-amparo ainda não rodou — não há backlog de funcionalidades
   disponível." e perguntar se o usuário quer (a) abortar e rodar
   `brainstorm-amparo` primeiro (recomendado), ou (b) continuar mesmo assim,
   avisando que Camila Conteúdo ficaria sem fonte real de funcionalidades
   para o copy (apenas a proposta geral do app, sem detalhes específicos).
3. **Identidade visual da marca**: procurar o projeto/documentação mais
   recente publicado pela squad `marca-design-amparo` (Claude Design e/ou
   markdown em `squads/marca-design-amparo/output/`). Se encontrado, sugerir
   como fonte de design system. Se não existir, avisar explicitamente: "A
   squad marca-design-amparo ainda não rodou — não há identidade visual
   publicada." e informar que Vitória Visual vai usar uma paleta provisória,
   claramente marcada como pendência, até a marca publicar.
4. **Referências opcionais**: perguntar se o usuário quer compartilhar agora
   (a) URLs de landing pages de referência que admira, e/ou (b) URLs de
   perfis sociais (Instagram/YouTube/Twitter/LinkedIn) de apps similares para
   inspiração de tom de voz. Se o usuário preferir pular, seguir sem
   referências — isso é opcional, não bloqueia o pipeline.
5. Registrar todas as respostas (caminho do projeto, rodada do backlog
   confirmada ou decisão de continuar sem ela, fonte de identidade visual
   confirmada ou decisão de usar paleta provisória, e referências fornecidas
   ou "nenhuma") em `squads/landing-page-amparo/output/inputs-e-referencias.md`.

## Output Format

```
CAMINHO DO PROJETO (fora do repositório TCC): {caminho absoluto confirmado}

BACKLOG (brainstorm-amparo):
Rodada/versão usada: {pasta + versão, ou "nenhuma — usuário optou por continuar sem backlog"}

IDENTIDADE VISUAL (marca-design-amparo):
Fonte usada: {projeto/arquivo, ou "PENDENTE — marca-design-amparo ainda não publicou, Vitória usará paleta provisória"}

REFERÊNCIAS:
Sites de landing page: {lista de URLs, ou "nenhuma"}
Perfis sociais: {lista de URLs, ou "nenhuma"}
```

## Output Example

```
CAMINHO DO PROJETO (fora do repositório TCC): /Users/mariootavio/Projects/landing-page-amparo

BACKLOG (brainstorm-amparo):
Rodada/versão usada: squads/brainstorm-amparo/output/2026-06-28-235345/v3/ideias-brainstorm.md

IDENTIDADE VISUAL (marca-design-amparo):
Fonte usada: PENDENTE — marca-design-amparo ainda não publicou nenhuma rodada.
Vitória Visual usará paleta provisória, marcada como pendência, no Step 4.

REFERÊNCIAS:
Sites de landing page: nenhuma — usuário vai compartilhar em uma execução futura
Perfis sociais: nenhuma
```

## Quality Criteria

- [ ] Caminho absoluto do diretório externo foi confirmado explicitamente — nunca assumido ou deixado em branco
- [ ] Rodada do backlog de `brainstorm-amparo` confirmada, ou decisão explícita de continuar sem ela
- [ ] Fonte de identidade visual confirmada, ou pendência registrada claramente
- [ ] Referências (se fornecidas) registradas com URLs completas
