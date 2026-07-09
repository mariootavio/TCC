---
type: checkpoint
inputFile: squads/marca-design-amparo/output/manual-identidade-visual.md
---

# Step 12: Checkpoint — Aprovação Final

## Contexto

Este é o checkpoint final do pipeline. O usuário já aprovou o Projeto 1
como um todo no checkpoint Step 10 (veredito de Marina + identidade +
design system), e só depois disso Helena Manual entregou dois artefatos
(Step 11): o manual técnico completo em
`output/manual-identidade-visual.md` (todas as informações, incluindo as
correções obrigatórias do veredito já aplicadas) E uma apresentação
premium curada, publicada em um SEGUNDO projeto Claude Design próprio
(8-12 slides, pensada para a banca do TCC ou investidores). A squad
produz DOIS projetos Claude Design distintos — propostas diferentes,
organizados separadamente por design:

1. **"Amparo — Marca & Design System"** (Flávia + Tomás) — projeto
   técnico: card de abertura, direções de identidade, mockups de
   aplicação, design system completo (tokens, componentes).
2. **"Amparo — Apresentação do Projeto"** (Helena) — projeto de pitch:
   8-12 slides curados, reaproveitando/recompondo o melhor do projeto 1,
   com direção de arte premium e, quando agregar impacto, imagens
   geradas por IA — feito para ser mostrado a terceiros e editado
   livremente depois pelo usuário direto no Claude Design.

Este checkpoint apresenta o veredito de Marina E os dois entregáveis de
Helena ao usuário para a decisão final, e formaliza a entrega — que serve
de insumo direto da squad `fluxos-uxui-amparo` para reconstruir tudo
dentro do Figma.

## Instruções

1. Recapitular em 1-2 frases que o Projeto 1 já foi aprovado pelo
   usuário no checkpoint Step 10 (veredito de Marina + identidade + design
   system) — não é preciso reapresentar a tabela completa de novo, só
   confirmar que este checkpoint foca no que Helena entregou depois
   dessa aprovação: o manual técnico e a apresentação premium.
2. Carregar e apresentar um resumo estruturado do manual técnico
   (`output/manual-identidade-visual.md`) — os 4 blocos (Diagnóstico,
   Arquitetura, Conteúdo página por página, Checklists + Próximos passos
   + Prompts de montagem + registro da apresentação premium),
   sinalizando explicitamente qualquer seção marcada "⚠️ PENDENTE DE
   CORREÇÃO" por Helena.
3. Apresentar o que foi selecionado para o projeto "Amparo —
   Apresentação do Projeto" (quais slides, quais mockups reaproveitados,
   se alguma imagem foi gerada por IA e qual prompt) — registrado no
   Bloco 4 do manual.
4. Informar explicitamente ao usuário os nomes dos DOIS projetos Claude
   Design ("Amparo — Marca & Design System" e "Amparo — Apresentação do
   Projeto") e orientar que ele pode abrir os dois diretamente em
   claude.ai/design — o segundo já pronto para ele editar livremente —,
   além do arquivo `output/manual-identidade-visual.md` para o manual
   técnico completo em texto.
5. Explicar que este trabalho — os dois projetos Claude Design mais o
   manual documental completo — é o insumo direto que a squad
   `fluxos-uxui-amparo` vai usar para reconstruir tudo dentro do Figma
   (a partir do projeto técnico, não do projeto de apresentação).
6. Perguntar ao usuário se ele aprova a entrega final como concluída
   (manual técnico + apresentação premium de Helena, em cima do Projeto
   1 já aprovado), ou se deseja alguma correção adicional antes de
   considerar este pipeline encerrado.
7. Se aprovado: registrar a aprovação final e encerrar o pipeline,
   recomendando o próximo passo (acionar a squad `fluxos-uxui-amparo`).
   Se não aprovado: registrar o feedback e direcionar de volta ao step
   relevante — Step 5 para identidade, Step 7 para design system/mockups
   (o que reabre o Step 10 de novo antes de Helena refazer o Step 11), ou
   direto ao Step 11 se a correção for apenas de redação/estrutura do
   manual ou de curadoria da apresentação (sem alterar nenhuma decisão
   de marca já
   aprovada).

## Output Format

Não há `outputFile` formal de novo conteúdo neste checkpoint — ele
consolida e encerra o pipeline. Registrar a decisão final do usuário de
forma clara na conversa.

## Output Example

```
CHECKPOINT — Aprovação Final

Veredito de Marina Marca: APROVAR COM RESSALVAS (média 7.8/10). Correção
obrigatória já aplicada por Tomás antes deste checkpoint: ajuste do token
color-action-emergency para terracotta-600 (contraste WCAG AA corrigido
para 4.6:1) — confirmado por Helena no Bloco 3 do manual, sem seções
pendentes de correção.

Manual Técnico: output/manual-identidade-visual.md — 4 blocos completos
(Diagnóstico, Arquitetura de 30 páginas, Conteúdo página a página,
Checklists incluindo item de discrição visual + Próximos passos + Prompts
de montagem + registro da apresentação premium).

Projeto Claude Design 1 — "Amparo — Marca & Design System"
(https://claude.ai/design/... — abertura, identidade, mockups de
aplicação, design system completo).

Projeto Claude Design 2 — "Amparo — Apresentação do Projeto"
(https://claude.ai/design/... — 9 slides: Capa, O Projeto, A Marca,
Logotipo, Paleta & Tipografia, Design System em Ação, Aplicações Reais
[mockups de app icon + Instagram reaproveitados e recompostos], Fechamento.
1 imagem gerada por IA na capa — mulher usando celular, segura e no
controle, seguindo `direcao-imagens-ia.md` — testada em `--mode test`
antes da versão final. Pronto para o usuário editar livremente.)

Próximo passo recomendado: acionar a squad `fluxos-uxui-amparo`, que vai
ler o Projeto 1 (Claude Design) e o manual para reconstruir fielmente a
identidade e o design system dentro do Figma, antes de desenhar fluxos de
UX e telas de alta fidelidade.

Decisão do usuário: Aprovado. Pipeline marca-design-amparo encerrado com
sucesso.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O veredito completo de Marina não foi apresentado ao usuário antes da
   pergunta de aprovação final.
2. O manual de Helena não foi apresentado, ou foi apresentado sem
   sinalizar seções "⚠️ PENDENTE DE CORREÇÃO" que ainda existam nele.
3. A apresentação premium não foi apresentada ao usuário como projeto
   Claude Design distinto do projeto técnico.
4. Os nomes/links dos DOIS projetos Claude Design e o caminho do manual
   não foram informados explicitamente ao usuário como parte da entrega.

## Quality Criteria

- [ ] O usuário viu o veredito completo de Marina (tabela de pontuação e
      feedback detalhado), não um resumo reduzido.
- [ ] O usuário viu um resumo estruturado dos 4 blocos do manual, com
      qualquer pendência de correção sinalizada explicitamente.
- [ ] O usuário viu o que foi selecionado para a apresentação premium
      (slides, mockups, imagem de IA se houver).
- [ ] Os nomes dos DOIS projetos Claude Design e o caminho do manual
      estão registrados como parte da entrega final, com indicação de
      que são o insumo da squad `fluxos-uxui-amparo` (a partir do
      Projeto 1, técnico).
- [ ] A decisão final do usuário (aprovado / correção adicional
      solicitada) está registrada de forma inequívoca.
