---
type: checkpoint
inputFile: squads/marca-design-amparo/output/design-system.md
---

# Step 8: Checkpoint — Aprovar Design System

## Contexto

Tomás Tokens construiu o design system completo (tokens primitivos e
semânticos, componentes na hierarquia atômica) no Step 7, publicando tudo
no mesmo projeto Claude Design já usado por Flávia. Este checkpoint
bloqueia o Step 9 (revisão de Marina Marca) até que o usuário confirme que
o design system está alinhado ao que esperava — evitando que Marina revise
algo que o próprio usuário já identificaria como incompleto ou incorreto.

## Instruções

1. Carregar e mostrar ao usuário o conteúdo completo de
   `squads/marca-design-amparo/output/design-system.md` — tokens
   primitivos, tokens semânticos, contraste verificado e a hierarquia de
   componentes (átomos, moléculas, organismos), na íntegra. Informar o
   nome do projeto Claude Design onde tudo foi publicado.
2. Perguntar explicitamente ao usuário:
   - O conjunto de tokens e componentes cobre o que ele espera para o
     Amparo, ou falta algum componente específico?
   - Há algum ajuste pontual necessário antes de seguir para a revisão
     formal de Marina Marca?
3. Se o usuário aprovar (com ou sem ajustes menores): registrar a decisão
   e liberar o pipeline para o Step 9.
4. Se o usuário rejeitar ou pedir ajustes substanciais: retornar ao Step 7
   para Tomás incorporar o feedback antes de seguir.

## Output Format

Não há `outputFile` formal para este checkpoint. Registrar a decisão do
usuário de forma clara na conversa, e quando aplicável, anotar qualquer
ajuste pontual solicitado para Tomás incorporar antes da próxima etapa.

## Output Example

```
CHECKPOINT — Aprovar Design System

Design system apresentado: tokens primitivos e semânticos de cor,
tipografia e espaçamento; componentes Atoms/Button, Atoms/Input,
Atoms/Icon, Atoms/Tag; Molecules/Form-Field, Molecules/List-Item,
Molecules/Alert-Banner; Organisms/App-Header, Organisms/Bottom-Nav,
Organisms/Card. Publicado no projeto Claude Design "Amparo — Marca &
Design System" (grupo "Design System").

Decisão do usuário: Aprovado, com uma observação — pedir que Tomás
adicione também um componente de Avatar (átomo) para a futura tela de
perfil, que a squad fluxos-uxui-amparo vai precisar.

Pipeline segue para Step 9: Marina Marca revisa a identidade visual e o
design system juntos, já considerando o componente Avatar adicionado.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O conteúdo de `design-system.md` não foi mostrado ao usuário antes de
   solicitar a aprovação.
2. O pipeline avança para o Step 9 sem uma decisão explícita de aprovação
   registrada.

## Quality Criteria

- [ ] O usuário viu a tabela completa de tokens e a hierarquia completa de
      componentes antes de decidir.
- [ ] A decisão final (aprovado / aprovado com ajuste / rejeitado) está
      registrada de forma inequívoca.
- [ ] Qualquer ajuste solicitado pelo usuário está documentado para a
      próxima etapa incorporar.
