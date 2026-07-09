---
type: checkpoint
---

# Step 7: Checkpoint — Aprovação Final

Apresente ao usuário um resumo completo do ciclo:

- O pedido original (`squads/marca-design-amparo/output/pedido.md`).
- A especificação/prompt final de Flávia Fonte
  (`squads/marca-design-amparo/output/especificacao.md`).
- O que Tomás Tokens implementou no Figma, ou a confirmação de que este
  ciclo era só prompt/especificação
  (`squads/marca-design-amparo/output/implementacao-figma.md`).
- O veredito de Marina Marca
  (`squads/marca-design-amparo/output/auditoria.md`).
- A nova entrada registrada no apêndice do manual
  (`squads/marca-design-amparo/output/manual-extensoes.md`).

Pergunte explicitamente:

- O resultado final atende ao que você pediu no Step 1?
- Se houve implementação no Figma, o componente/tela está posicionado e
  nomeado de um jeito que faz sentido para você continuar trabalhando nele?
- Quer pedir mais alguma coisa agora (um novo ciclo) ou este pedido está
  concluído?

Se o usuário aprovar, este ciclo é encerrado — a especificação, a
implementação (se houve) e a entrada do apêndice ficam disponíveis em
`squads/marca-design-amparo/output/` para consulta ou para alimentar outra
squad (ex.: `fluxos-uxui-amparo`, `landing-page-amparo`).

Se o usuário não aprovar, pergunte se o ajuste é na especificação (volta ao
Step 2, Flávia Fonte) ou só um detalhe da implementação no Figma (volta ao
Step 4, Tomás Tokens).

Este checkpoint é obrigatório antes de finalizar o ciclo — lembre o usuário
de que pode rodar a squad novamente a qualquer momento para um novo pedido,
sempre partindo do mesmo `brand/` travado.
