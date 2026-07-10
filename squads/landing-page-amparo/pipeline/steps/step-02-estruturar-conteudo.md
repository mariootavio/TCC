---
execution: inline
agent: camila-conteudo
inputFile: squads/landing-page-amparo/output/inputs-e-referencias.md
outputFile: squads/landing-page-amparo/output/estrutura-conteudo.md
---

# Step 2: Estruturar Conteúdo

## Context Loading

Load these files before executing:
- `squads/landing-page-amparo/output/inputs-e-referencias.md` — modo de
  execução (nova construção ou ajuste), rodada do backlog confirmada e
  referências opcionais (Step 1).
- Backlog confirmado de `squads/brainstorm-amparo/output/.../ideias-brainstorm.md`
  (ou revisão mais recente) — ancoragem obrigatória de toda funcionalidade
  citada no copy.
- `_opensquad/_memory/company.md` — tom de voz, público, produto.
- `pipeline/data/research-brief.md` (seção 1) — framework de estrutura e
  anti-padrões de landing page de causa social.
- `pipeline/data/output-examples.md` (Exemplos 1-3) — referência de
  qualidade para hero, funcionalidades e prova social.

## Instructions

### Process

1. Ler o backlog confirmado por completo e extrair as funcionalidades
   priorizadas (RF-CORE + ideias com score RICE) que sustentam a seção de
   Funcionalidades — nenhuma funcionalidade entra no copy sem essa ancoragem.
2. Definir a arquitetura de seções (Hero, Problema/Solução, Funcionalidades,
   Como Funciona, Prova Social Institucional, Sobre o Projeto/TCC,
   Contato+CTA final), ajustando conforme o que o backlog realmente sustenta.
3. Para o Hero, redigir 3 hooks com gatilhos psicológicos distintos
   (seguindo `copywriting.md`), escolher o mais alinhado ao tom acolhedor de
   `company.md`, e só então escrever subheadline, CTA primário e microcopy.
4. Escrever o copy das demais seções usando PAS/AIDA conforme a seção,
   endereçando explicitamente os 3 públicos (vítima/rede de apoio,
   ONGs/parceiros, banca acadêmica) em seções ou CTAs distintos, sem diluir
   o CTA primário.
5. Se o modo de execução (Step 1) for "ajuste em Figma existente", focar a
   revisão apenas no escopo indicado pelo usuário, mantendo o restante da
   estrutura/copy já aprovada em execuções anteriores.
6. Compilar `estrutura-conteudo.md` com a arquitetura completa, o copy de
   cada seção, e uma lista explícita de pendências (funcionalidades sem
   backlog confirmado, referências ainda não fornecidas, etc.).

## Output Format

```text
ARQUITETURA DE SEÇÕES
1. {nome da seção}
...

SEÇÃO: {NOME}
Hook A/B/C (se aplicável, apenas Hero): {texto} — Rationale: {gatilho psicológico}
Copy final:
  Headline/Heading: {texto}
  Corpo: {texto}
  CTA: {texto, primário ou secundário}
Ancoragem ao backlog: {RF-CORE-XX / ideia, ou "institucional, sem ancoragem necessária"}

PENDÊNCIAS
- {item pendente e por quê}
```

## Output Example

Ver `pipeline/data/output-examples.md`, Exemplos 1, 2 e 3 — hero completo,
bloco de funcionalidade ancorado, e prova social institucional. O output
real desta etapa segue o mesmo nível de detalhe e especificidade desses
exemplos, cobrindo as 7 seções da arquitetura.

## Veto Conditions

Reject and redo if ANY of these are true:
1. Alguma funcionalidade aparece no copy sem ancoragem ao backlog real de `brainstorm-amparo`.
2. Há mais de um CTA primário concorrendo na mesma seção.

## Quality Criteria

- [ ] Todo CTA primário aparece sozinho por seção
- [ ] Os 3 públicos têm seção ou CTA dedicado, sem diluir o CTA primário
- [ ] Zero depoimento nominal de vítima real
- [ ] Pendências (backlog ausente, referências não fornecidas) registradas explicitamente, nunca preenchidas por invenção
