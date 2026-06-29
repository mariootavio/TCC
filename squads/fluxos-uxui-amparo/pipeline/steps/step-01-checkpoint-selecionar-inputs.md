---
type: checkpoint
outputFile: squads/fluxos-uxui-amparo/output/inputs-selecionados.md
---

# Step 1: Checkpoint — Selecionar Inputs

Este é o primeiro checkpoint do pipeline da squad Fluxos & UI/Protótipo —
Amparo. Antes de iniciar qualquer trabalho de design, explique brevemente o
contexto ao usuário: esta squad transforma em Figma (telas reais + protótipo
navegável) o que duas outras squads já produziram — o backlog priorizado de
funcionalidades da squad `brainstorm-amparo`, e o design system/identidade
visual publicado pela squad `marca-design-amparo` no Claude Design.

Esta squad nunca repesquisa ou reinventa esse conteúdo — ela lê e usa o que já
foi produzido. Por isso, antes de avançar, é preciso confirmar exatamente
quais rodadas/versões dessas duas squads devem ser usadas como fonte.

## Instructions

1. Procurar a pasta de output mais recente de
   `squads/brainstorm-amparo/output/` (ordenar por timestamp do nome da
   pasta) e, dentro dela, a versão mais alta disponível (`v1`, `v2`, ...)
   contendo `ideias-brainstorm.md`. Se encontrada, sugerir essa rodada/versão
   como padrão ao usuário. Se nenhuma rodada existir, avisar explicitamente:
   "A squad brainstorm-amparo ainda não rodou — não há backlog de ideias
   disponível." e perguntar se o usuário quer (a) abortar e rodar
   `brainstorm-amparo` primeiro (recomendado), ou (b) continuar mesmo assim,
   avisando que isso obrigaria os agentes seguintes a trabalhar sem uma fonte
   real de backlog.
2. Procurar o projeto mais recente publicado pela squad `marca-design-amparo`
   no Claude Design, e/ou a documentação em markdown que ela gera
   (`identidade-visual.md`, `design-system.md`, tipicamente em
   `squads/marca-design-amparo/output/`). Se encontrado, sugerir essa
   rodada/projeto como padrão. Se nenhuma rodada existir, avisar
   explicitamente: "A squad marca-design-amparo ainda não rodou — não há
   design system publicado no Claude Design disponível." e perguntar se o
   usuário quer (a) abortar e rodar `marca-design-amparo` primeiro
   (recomendado), ou (b) continuar mesmo assim, avisando que Caio
   Componentes (Step 2) ficaria sem fonte de verdade para reconstruir o
   design system no Figma.
3. Perguntar ao usuário explicitamente:
   - Qual rodada/pasta de output de `brainstorm-amparo` deve ser usada como
     backlog de ideias desta squad?
   - Qual rodada/projeto Claude Design de `marca-design-amparo` deve ser
     usada como identidade visual/design system desta squad?
4. Registrar a resposta (incluindo os caminhos exatos confirmados, ou a
   decisão explícita de continuar sem uma das fontes) em
   `squads/fluxos-uxui-amparo/output/inputs-selecionados.md`.

Se nenhuma das duas squads tiver rodado ainda, recomende fortemente abortar
este pipeline e rodar `brainstorm-amparo` e `marca-design-amparo` primeiro —
prosseguir sem essas fontes contraria o propósito desta squad, que é
reconstruir e usar conteúdo real já produzido, nunca inventar.
