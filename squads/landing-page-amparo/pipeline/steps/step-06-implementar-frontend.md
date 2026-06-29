---
execution: inline
agent: fabio-frontend
inputFile: squads/landing-page-amparo/output/especificacao-visual.md
outputFile: squads/landing-page-amparo/output/implementacao-frontend.md
---

# Step 6: Implementar Front-end

## Context Loading

Load these files before executing:
- `squads/landing-page-amparo/output/especificacao-visual.md` (Vitória) —
  design system e especificação de cada seção, aprovados no Step 5.
- `squads/landing-page-amparo/output/estrutura-conteudo.md` (Camila) —
  copy de cada seção e especificação funcional da Saída Rápida.
- `squads/landing-page-amparo/output/inputs-e-referencias.md` (Step 1) —
  caminho absoluto do diretório externo onde o projeto deve ser criado.

## Instructions

### Process

1. Confirmar o caminho absoluto do diretório externo em
   `inputs-e-referencias.md`. Este projeto NUNCA é criado dentro do
   repositório do TCC.
2. Carregar as skills `shadcn`, `vercel-react-best-practices`,
   `vercel-composition-patterns`, `design-taste-frontend` e
   `full-output-enforcement` antes de escrever qualquer arquivo.
3. Criar (ou atualizar, se já existir) o projeto Next.js (App Router) +
   TypeScript + Tailwind CSS no caminho confirmado; inicializar shadcn/ui via
   sua CLI; configurar `next/font` com a tipografia especificada por Vitória.
4. Configurar `app/layout.tsx` com metadata global discreta (`<title>`, meta
   description, Open Graph neutros, sem termos explícitos sobre violência
   doméstica).
5. Implementar e testar o componente de Saída Rápida ANTES de qualquer outra
   seção: fixo no layout raiz, `window.location.replace()` no clique,
   listener global de `keydown` para Esc-Esc (duplo em até 1s), `z-index`
   acima de qualquer overlay, zero animação.
6. Implementar cada uma das 7 seções como componente, seguindo exatamente os
   valores da especificação visual de Vitória (cores, tipografia, grid,
   breakpoints) e o copy de Camila, com responsividade mobile-first e
   acessibilidade (foco visível, ARIA, contraste).
7. Compilar `implementacao-frontend.md`: estrutura de pastas/componentes,
   comandos para rodar o projeto localmente, confirmação explícita de que a
   Saída Rápida foi testada (clique + atalho Esc-Esc), e pendências técnicas.

## Output Format

```
PROJETO CRIADO EM: {caminho absoluto}
COMANDOS PARA RODAR LOCALMENTE: {ex.: cd {caminho} && npm install && npm run dev}

ESTRUTURA DE COMPONENTES
- app/layout.tsx — metadata global + Saída Rápida
- components/quick-exit-button.tsx
- components/{secao}.tsx (uma por seção)

SAÍDA RÁPIDA — VERIFICAÇÃO
Clique: {testado/não testado, resultado}
Atalho Esc-Esc: {testado/não testado, resultado}

PENDÊNCIAS TÉCNICAS
- {item, se houver}
```

## Output Example

Ver `pipeline/data/output-examples.md`, Exemplo 6 (componente de Saída Rápida
completo) e Exemplo 7 (metadata global discreta) — o output real desta etapa
inclui o projeto completo com todas as 7 seções implementadas no mesmo nível
de rigor.

## Veto Conditions

Reject and redo if ANY of these are true:
1. O componente de Saída Rápida usa `window.location.href` em vez de `.replace()`, tem qualquer animação, ou exige confirmação antes de redirecionar.
2. O projeto foi criado dentro do repositório do TCC em vez do diretório externo confirmado no Step 1.
3. `<title>`, meta description ou Open Graph contêm termos explícitos sobre violência doméstica.

## Quality Criteria

- [ ] Zero erros de console / zero warnings de hydration mismatch
- [ ] 100% dos elementos interativos navegáveis por teclado com foco visível
- [ ] Implementação fiel aos valores exatos da especificação visual de Vitória
- [ ] Comandos de setup documentados e reproduzíveis
