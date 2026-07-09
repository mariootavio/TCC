---
type: checkpoint
outputFile: squads/marca-design-amparo/output/pedido.md
---

# Step 1: Checkpoint — Captura do Pedido

Este é o primeiro checkpoint do pipeline reformulado da squad Marca &
Design System — Amparo. Antes de perguntar qualquer coisa, explique
brevemente ao usuário: a identidade visual e o design system do Amparo já
estão **finalizados e travados** em `brand/design-system.md`,
`brand/LogoAmparo.svg` e `brand/manual-amparo.pdf`. Esta squad não cria
marca nova — ela ajuda a **estender** o que já existe (novos componentes,
telas, páginas, prompts de imagem, documentação), sempre fielmente
derivado desses três arquivos, sem nunca alterar o que já está lá.

Pergunte explicitamente ao usuário:

1. **O que você precisa neste ciclo?** (texto livre — exemplos: "um
   componente novo de card para X", "uma tela do app para o fluxo Y", "uma
   página nova da landing page", "um prompt de imagem para Z", "documentar
   uma decisão de design que ainda não está no manual").
2. **Para onde é isso?** App mobile do Amparo, landing page, ou
   documentação/manual (não vinculado a uma tela específica).
3. **Você quer só o prompt/especificação em texto, ou quer que isso seja
   implementado de verdade no Figma?** Se for implementação no Figma,
   perguntar também se o usuário já tem o arquivo Figma do Amparo aberto/
   identificado (o mesmo construído pela squad `fluxos-uxui-amparo`) —
   Tomás Tokens (Step 4) vai precisar dessa confirmação antes de criar
   qualquer coisa lá.
4. **Alguma referência ou restrição adicional** (ex.: "tem que caber em
   telas pequenas", "é para o fluxo de emergência, discrição é crítica")?

Registre todas as respostas em `squads/marca-design-amparo/output/pedido.md`.
Se o usuário não souber se quer implementação no Figma, sugira o padrão:
"só o prompt/especificação por enquanto" — é sempre possível pedir a
implementação depois, em outro ciclo, reaproveitando a especificação já
aprovada.

## Output Format

```
PEDIDO: {descrição livre do que o usuário precisa}
DESTINO: {app mobile | landing page | documentação/manual}
ROTEAMENTO: {só prompt/especificação | implementação real no Figma}
ARQUIVO FIGMA (se roteamento = implementação): {confirmado pelo usuário | "a confirmar no Step 4"}
RESTRIÇÕES/REFERÊNCIAS ADICIONAIS: {texto livre, ou "nenhuma"}
```

## Quality Criteria

- [ ] O pedido está descrito de forma específica o suficiente para Flávia
      Fonte (Step 2) trabalhar sem precisar adivinhar.
- [ ] O roteamento (só prompt vs. implementação no Figma) está registrado
      de forma explícita, nunca deixado implícito.
- [ ] Se o roteamento pede implementação, o contexto do arquivo Figma foi
      perguntado (mesmo que a resposta seja "a confirmar no Step 4").
