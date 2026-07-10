---
type: checkpoint
outputFile: squads/landing-page-amparo/output/inputs-e-referencias.md
---

# Step 1: Checkpoint — Coletar Referências e Inputs

Este é o primeiro checkpoint do pipeline da squad Landing Page — Amparo.
Antes de iniciar qualquer trabalho de conteúdo, design ou construção no
Figma, explique brevemente o contexto ao usuário: esta squad constrói uma
landing page premium do projeto Amparo inteiramente no Figma (copy +
design + protótipo navegável com assets), baseada no backlog de
funcionalidades da squad `brainstorm-amparo` e na identidade visual
já finalizada em `brand/design-system.md`.

Este checkpoint resolve três decisões antes de Camila Conteúdo começar:

## Instructions

1. **Nova construção ou ajuste em Figma existente**: verificar se
   `squads/landing-page-amparo/_memory/memories.md` já registra um arquivo
   Figma de uma execução anterior desta squad. Se sim, perguntar ao
   usuário se esta execução é (a) uma construção nova do zero, ou (b) um
   ajuste/refinamento no arquivo Figma já existente — nesse caso, também
   perguntar o que especificamente precisa mudar, para que Camila e
   Vitória saibam se revisam tudo ou só a parte relevante. Se não houver
   registro anterior, seguir direto como primeira construção.
2. **Backlog de funcionalidades**: procurar a pasta de output mais recente
   de `squads/brainstorm-amparo/output/` (ordenar por timestamp do nome da
   pasta) e, dentro dela, a versão mais alta disponível contendo um
   arquivo de ideias/backlog. Se encontrada, sugerir essa rodada/versão
   como padrão ao usuário. Se nenhuma rodada existir, avisar
   explicitamente: "A squad brainstorm-amparo ainda não rodou — não há
   backlog de funcionalidades disponível." e perguntar se o usuário quer
   (a) abortar e rodar `brainstorm-amparo` primeiro (recomendado), ou (b)
   continuar mesmo assim, avisando que Camila Conteúdo ficaria sem fonte
   real de funcionalidades para o copy (apenas a proposta geral do app,
   sem detalhes específicos).
3. **Referências opcionais**: perguntar se o usuário quer compartilhar
   agora (a) URLs de landing pages de referência que admira, e/ou (b) URLs
   de perfis sociais (Instagram/YouTube/Twitter/LinkedIn) de apps
   similares para inspiração de tom de voz. Se o usuário preferir pular,
   seguir sem referências — isso é opcional, não bloqueia o pipeline.
4. **Identidade visual**: informar ao usuário que a identidade visual do
   Amparo já está finalizada e travada em `brand/design-system.md` e
   `brand/LogoAmparo.svg` — Vitória Visual vai usar esses arquivos como
   fonte única, sem exceção. Não há mais cenário de "identidade pendente".
5. Registrar todas as respostas (novo build ou ajuste + arquivo Figma
   existente se aplicável, rodada do backlog confirmada ou decisão de
   continuar sem ela, e referências fornecidas ou "nenhuma") em
   `squads/landing-page-amparo/output/inputs-e-referencias.md`.

## Output Format

```
MODO DE EXECUÇÃO: {nova construção | ajuste em arquivo Figma existente}
Arquivo Figma existente (se ajuste): {link/nome registrado em memories.md, ou "N/A"}
Escopo do ajuste (se aplicável): {o que precisa mudar}

BACKLOG (brainstorm-amparo):
Rodada/versão usada: {pasta + versão, ou "nenhuma — usuário optou por continuar sem backlog"}

IDENTIDADE VISUAL: brand/design-system.md e brand/LogoAmparo.svg (fonte única, sempre disponível)

REFERÊNCIAS:
Sites de landing page: {lista de URLs, ou "nenhuma"}
Perfis sociais: {lista de URLs, ou "nenhuma"}
```

## Output Example

```
MODO DE EXECUÇÃO: nova construção
Arquivo Figma existente (se ajuste): N/A

BACKLOG (brainstorm-amparo):
Rodada/versão usada: squads/brainstorm-amparo/output/2026-06-28-235345/v3/ideias-brainstorm.md

IDENTIDADE VISUAL: brand/design-system.md e brand/LogoAmparo.svg (fonte única, sempre disponível)

REFERÊNCIAS:
Sites de landing page: nenhuma — usuário vai compartilhar em uma execução futura
Perfis sociais: nenhuma
```

## Quality Criteria

- [ ] Modo de execução (nova construção vs. ajuste) confirmado explicitamente, verificando `_memory/memories.md` primeiro
- [ ] Rodada do backlog de `brainstorm-amparo` confirmada, ou decisão explícita de continuar sem ela
- [ ] Referências (se fornecidas) registradas com URLs completas
- [ ] Usuário informado de que a identidade visual é fixa e sempre disponível em `brand/`
