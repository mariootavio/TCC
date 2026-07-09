---
execution: inline
agent: helena-manual
inputFile: squads/marca-design-amparo/output/revisao-marca.md
outputFile: squads/marca-design-amparo/output/manual-identidade-visual.md
---

# Step 11: Criar Manual Técnico + Apresentação Premium

## Context Loading

Load these files before executing:
- `squads/marca-design-amparo/output/identidade-visual.md` — identidade
  visual aprovada (Flávia, checkpoint Step 6)
- `squads/marca-design-amparo/output/design-system.md` — design system e
  mockups de aplicação aprovados (Tomás, checkpoint Step 8)
- `squads/marca-design-amparo/output/revisao-marca.md` — veredito de
  revisão (Marina, Step 9), incluindo qualquer correção obrigatória
- `squads/marca-design-amparo/output/brief-design.md` — brief de marca
  original
- `_opensquad/_memory/company.md` — contexto do projeto Amparo (público,
  tom de voz, uso pretendido)
- `squads/marca-design-amparo/pipeline/data/anti-patterns.md` —
  anti-padrões trauma-informados a preservar em ambos os entregáveis
- `squads/marca-design-amparo/pipeline/data/direcao-imagens-ia.md` —
  diretriz obrigatória para qualquer imagem gerada por IA nesta etapa
  (sujeito preferencial, tom, regras trauma-informadas, disciplina de
  geração)

Nota: este step só começa DEPOIS do checkpoint Step 10 (usuário aprovou o
Projeto 1 inteiro — identidade + design system + mockups). Depende de
três ferramentas/skills nativas do ambiente, não do catálogo Opensquad —
o skill `manual-identidade-visual-premium` (via Skill tool) e a
ferramenta `DesignSync`, usada aqui em DOIS modos: leitura do projeto
"Amparo — Marca & Design System" (Flávia/Tomás, para reaproveitar logo/
mockups como base) e escrita num SEGUNDO projeto próprio, "Amparo —
Apresentação do Projeto" (`create_project` se ainda não existir — nunca
escrever dentro do primeiro projeto). Também usa uma skill do catálogo
Opensquad, `image-ai-generator` (já declarada em `squad.yaml`), com
moderação, para no máximo 1-2 imagens de alto impacto (nunca um lote
automático).

## Instructions

### Process — Parte A: Manual Técnico Completo (`output/manual-identidade-visual.md`)

1. Carregar identidade visual, design system (com mockups), veredito de
   Marina, brief e contexto da empresa.
2. Verificar, item a item, se toda "Correção obrigatória" do veredito de
   Marina já foi aplicada. Se pendente, marcar a seção correspondente do
   manual como "⚠️ PENDENTE DE CORREÇÃO".
3. Invocar o skill `manual-identidade-visual-premium` via Skill tool e
   seguir suas 7 etapas na íntegra, usando: `arquitetura-50-paginas.md`
   (Etapa 3), `estrutura-manual-premium.md` como esqueleto a copiar
   (Etapa 4), `direcao-de-layout.md` para toda direção de layout,
   `aplicacoes-detalhadas.md` + `exemplos-de-aplicacoes.md` como piso de
   qualidade (Etapa 5), `vocabulario-design.md` para terminologia e
   "Palavras a evitar", `checklist-auditoria.md` + `checklist-
   identidade-visual.md` para os checklists (Etapa 6).
4. Cobrir os 8 blocos obrigatórios (abertura, marca, logotipo, cromática,
   tipografia, elementos visuais, aplicações, operacional), fechando em
   versão enxuta de 25-35 páginas.
5. Incluir, em pelo menos um checklist, item explícito sobre discrição
   visual (ex.: "o ícone do app não expõe o propósito do aplicativo para
   quem vê de relance").
6. Rodar a autoavaliação de qualidade do skill (hex presentes, tipografia
   nomeada, sem frase genérica, sem placeholder) e corrigir qualquer item
   reprovado.
7. Salvar o manual completo em `output/manual-identidade-visual.md`.

### Process — Parte B: Apresentação Premium (projeto "Amparo — Apresentação do Projeto")

1. Definir o arco narrativo em ~8-12 slides (nunca um dump 1:1 do
   manual): Capa → O Projeto (problema, solução, promessa, público) → A
   Marca (essência, personalidade, conceito) → Logotipo → Paleta &
   Tipografia → Design System em Ação → Aplicações Reais (melhores
   mockups de Tomás) → Fechamento/Visão. É uma apresentação para banca do
   TCC ou investidores — cortar todo bloco técnico que não sirva à
   história.
2. Reaproveitar como base os assets já publicados por Flávia/Tomás (logo,
   paleta, tipografia, 2-3 melhores mockups) — pode recompor o layout do
   slide, nunca alterar cor/fonte/logo.
3. Avaliar, slide a slide, se uma imagem gerada por IA eleva o
   resultado (tipicamente capa, abertura "O Projeto", e Aplicações
   Reais). Se sim: seguir `direcao-imagens-ia.md` à risca — sujeito
   preferencial é mulher real usando celular, com expressão de
   segurança/confiança (refletindo o público real de Renata:
   majoritariamente negras, 18-44 anos), fotografia editorial moderna e
   atrativa. Usar a skill `image-ai-generator`, `--mode test` primeiro,
   `--mode production` só após aprovação visual própria, `--reference`
   no logo quando fizer sentido. Regras trauma-informadas inegociáveis:
   nunca imagética literal de violência doméstica, nunca vermelho/
   laranja de alarme dominante, nunca exposição do propósito do app —
   a mulher retratada está sempre segura e no controle, nunca
   vulnerável. Se `OPENROUTER_API_KEY` não estiver configurada, pular a
   geração e resolver com tipografia/composição/mockups existentes —
   nunca bloquear a entrega por isso.
4. Publicar no SEGUNDO projeto Claude Design via `DesignSync`: (a)
   `list_projects` para checar se "Amparo — Apresentação do Projeto" já
   existe (reexecução do pipeline) — projeto DIFERENTE de "Amparo —
   Marca & Design System", que é só leitura aqui; (b) se não existir,
   `create_project` com o nome "Amparo — Apresentação do Projeto"; (c)
   escrever localmente os HTML dos slides em
   `squads/marca-design-amparo/_claude-design/apresentacao-projeto/`,
   cada um com `<!-- @dsCard group="Apresentação" -->` na primeira
   linha; (d) `finalize_plan` com esses paths; (e) `write_files`.
5. Registrar no Bloco 4 do manual o que foi selecionado para a
   apresentação (slides, mockups escolhidos, prompt de qualquer imagem
   gerada por IA), e parar: o checkpoint Step 12 decide a aprovação
   final.

## Output Format

The output MUST follow the 4-block structure do skill
`manual-identidade-visual-premium`, mais um registro da apresentação:
```markdown
# Manual de Identidade Visual Premium — Amparo

## Bloco 1 — Diagnóstico da Marca
[prosa editorial: leitura estratégica, território semântico, percepção
visual desejada, fundamentado em brief + pesquisa de Renata + identidade
aprovada]

## Bloco 2 — Arquitetura do Manual
[sumário comentado dos 8 blocos, adaptado ao porte do Amparo]
Projeto Claude Design: "Amparo — Marca & Design System" (localizado via
`list_projects`, já existente — criado por Flávia, usado por Tomás)

## Bloco 3 — Conteúdo Página por Página
[cada página: número + título, objetivo, conteúdo textual completo,
direção de layout, elementos visuais recomendados, observações técnicas
com hex/fontes/unidades — sinalizando "⚠️ PENDENTE DE CORREÇÃO" onde
aplicável]

## Bloco 4 — Checklists Finais + Próximos Passos + Prompts de Montagem + Apresentação Premium
[múltiplos checklists por perfil, incluindo item de discrição visual;
próximos passos de produção; prompts de montagem; registro dos slides
selecionados para o projeto "Amparo — Apresentação do Projeto", mockups
escolhidos, e prompt de qualquer imagem gerada por IA]
```

## Output Example

```markdown
# Manual de Identidade Visual Premium — Amparo

## Bloco 1 — Diagnóstico da Marca
O Amparo é uma plataforma de proteção trauma-informada contra violência
doméstica. Fala com mulheres em situação de risco (majoritariamente
negras, 18-44 anos) oferecendo emergência, documentação segura, rede de
apoio e acesso a profissionais. Discrição é requisito de segurança.

## Bloco 2 — Arquitetura do Manual
1. Abertura — Capa, Sumário, Introdução
[...os 8 blocos...]
Projeto Claude Design: "Amparo — Marca & Design System"

## Bloco 3 — Conteúdo Página por Página
### Página 12 — Cor de Ação de Emergência
⚠️ PENDENTE DE CORREÇÃO: Marina (Step 9) reprovou branco sobre
color-action-emergency (#B97A56, 3.9:1) — exigiu ajuste para
terracotta-600. Confirmar aplicação no design-system.md.
[demais páginas seguem o padrão completo]

## Bloco 4 — Checklists Finais + Próximos Passos + Prompts de Montagem + Apresentação Premium
### Checklist de discrição e segurança
- [ ] O ícone do app não expõe o propósito do aplicativo para quem vê de
      relance?

### Apresentação do Projeto (publicada no SEGUNDO projeto Claude Design:
"Amparo — Apresentação do Projeto")
Slides: 01-capa, 02-o-projeto, 03-a-marca, 04-logotipo, 05-paleta-
tipografia, 06-design-system, 07-aplicacoes-reais, 08-fechamento.
Mockups reaproveitados (recompostos, não idênticos) do projeto "Amparo —
Marca & Design System" de Tomás: mockup-app-icon, mockup-instagram-post.
Imagem gerada por IA: 1 imagem para a capa (`--mode production`, prompt:
"editorial photograph of a confident Black woman in her late 20s,
smiling softly while looking at her smartphone, natural window light,
warm neutral background in slate and terracotta tones, modern minimal
composition, contemporary lifestyle photography, hyper realistic, 4K
quality, no visible text or UI on the phone screen, --ar 16:9 --style
raw"), seguindo `direcao-imagens-ia.md` — mulher segura e no controle,
sem imagética de violência/alarme, sem exposição do propósito do app.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O manual documenta como final um token/componente que o veredito de
   Marina reprovou, sem a correção confirmada.
2. O manual contém frase da tabela anti-genérico do skill sem quantificar.
3. Nenhum checklist do manual contém item auditável sobre discrição
   visual.
4. Algum dos 8 blocos do manual está ausente.
5. Este step foi iniciado sem uma aprovação explícita do Projeto 1
   registrada no checkpoint Step 10.
6. Os slides da apresentação foram publicados dentro do projeto "Amparo
   — Marca & Design System" em vez de num segundo projeto próprio, OU um
   terceiro projeto foi criado quando "Amparo — Apresentação do Projeto"
   já existia.
7. A apresentação tem mais de ~12 slides ou é essencialmente um dump 1:1
   do manual, em vez de uma seleção curada.
8. Alguma imagem gerada por IA contém imagética de violência doméstica,
   alarme, ou expõe o propósito do app, ou não segue a direção de
   `direcao-imagens-ia.md` (sujeito preferencial: mulher segura usando
   celular).
9. Imagem foi gerada em `--mode production` sem antes validar em
   `--mode test`.

## Quality Criteria

- [ ] Toda cor mencionada inclui hex; toda tipografia traz o nome real da
      fonte.
- [ ] Nenhuma seção documenta como final um valor pendente de correção do
      veredito de Marina.
- [ ] Há pelo menos 3 checklists distintos por perfil no Bloco 4,
      incluindo o item de discrição visual.
- [ ] O manual passou pela autoavaliação de qualidade do skill sem item
      reprovado.
- [ ] Os 8 blocos da arquitetura padrão estão presentes, adaptados ao
      porte do Amparo.
- [ ] A apresentação premium tem 8-12 slides curados, publicados num
      SEGUNDO projeto Claude Design próprio ("Amparo — Apresentação do
      Projeto", localizado via `list_projects` antes de `create_project`),
      usando exclusivamente tokens/logo/mockups já aprovados no primeiro
      projeto.
- [ ] Qualquer imagem gerada por IA foi testada antes da versão final,
      segue `direcao-imagens-ia.md` (mulher segura usando celular,
      representando o público real de Renata) e não viola as regras
      trauma-informadas.
- [ ] Este step só começou depois da aprovação explícita do Projeto 1 no
      checkpoint Step 10.
