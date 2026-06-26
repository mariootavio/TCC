---
execution: inline
agent: diana-defesa
inputFile: squads/tcc-documentacao/output/relatorio-tcc.md
outputFile: squads/tcc-documentacao/output/argumentacao-defesa.md
---

# Step 5: Construção da Argumentação de Defesa

## Context Loading

Load these files before executing:
- `squads/tcc-documentacao/output/relatorio-tcc.md` — relatório estruturado
  produzido por Helena Hipótese no Step 4; fonte primária das teses
  argumentativas.
- `squads/tcc-documentacao/pipeline/data/research-brief.md` — research
  brief original; toda evidência de suporte das teses deve remeter a este
  documento.
- `squads/tcc-documentacao/pipeline/data/domain-framework.md` — framework
  operacional de Diana Defesa (cadeia lógica problema-objetivo-contribuição,
  proporção de slides por tempo).
- `squads/tcc-documentacao/pipeline/data/quality-criteria.md` — critérios de
  qualidade do pacote de argumentação.

## Instructions

### Process

1. Executar a task `construir-teses-argumentativas.md`: formular 3-5 teses
   centrais a partir do relatório e do research brief, cada uma com
   contra-argumento provável e resposta preparada.
2. Executar a task `antecipar-perguntas-banca.md`: compilar 10-15 perguntas
   frequentes de banca com resposta preparada de 2-4 frases cada, garantindo
   que toda limitação mencionada no relatório também apareça aqui.
3. Executar a task `estruturar-slide-deck.md`: produzir o roteiro de slides
   na proporção de ~1 slide por minuto, com título, conteúdo-chave e nota de
   fala por slide.
4. Consolidar os três outputs (teses, perguntas, roteiro de slides) em um
   único documento e salvar em
   `squads/tcc-documentacao/output/argumentacao-defesa.md`.

## Output Format

The output MUST follow this exact structure:
```
TESES ARGUMENTATIVAS — TCC AMPARO

TESE 1: {enunciado}
Evidência de suporte: {dado + fonte + seção}
Contra-argumento provável da banca: {pergunta crítica}
Resposta preparada: {resposta com evidência}

---
{repetir para cada tese, 3-5 total}

PERGUNTAS ANTECIPADAS DA BANCA

[Categoria: {metodologia | limitações | comparação | viabilidade}]
P: {pergunta}
R: {resposta de 2-4 frases}
{repetir até 10-15 perguntas}

ROTEIRO DE SLIDE DECK — DEFESA TCC AMPARO
Duração estimada: {N} minutos | {M} slides

SLIDE 1 — {título}
Conteúdo: {bullets ou visual}
Nota de fala: {o que dizer}
{repetir para cada slide}
```

## Output Example

```
TESES ARGUMENTATIVAS — TCC AMPARO

TESE 1: A subnotificação, não a ausência de violência, é a barreira
central a ser endereçada.

Evidência de suporte: Estudo do Observatório da Mulher contra a Violência
(Senado, DataSenado) estima subnotificação de 61%. (Fonte: research-brief.md,
Seção "Dados e Estatísticas", Confiança: ALTA)

Contra-argumento provável da banca: "Se a vítima não denuncia por medo do
agressor, um app não resolve esse medo — por que a solução tecnológica
endereçaria a causa raiz?"

Resposta preparada: O Amparo não substitui o enfrentamento do medo, mas
reduz a fricção e o risco do primeiro passo: documentação segura de provas
sem exposição imediata, rede de apoio pessoal antes da denúncia formal.

---

PERGUNTAS ANTECIPADAS DA BANCA

[Categoria: Comparação com soluções existentes]
P: "Por que não usar uma solução já existente, como o Botão do Pânico
estadual?"
R: O Botão do Pânico estadual exige medida protetiva prévia — pressupõe
denúncia já formalizada. O Amparo atua antes desse ponto, complementando a
solução estatal.

ROTEIRO DE SLIDE DECK — DEFESA TCC AMPARO
Duração estimada: 20 minutos | 18 slides (~1,1 min/slide)

SLIDE 1 — Capa
Conteúdo: Título do TCC, autor, orientador, instituição, data.
Nota de fala: Apresentação protocolar, 15 segundos.

SLIDE 2 — O problema em um dado
Conteúdo: "61% das mulheres vítimas de violência doméstica no Brasil não
denunciam" (DataSenado).
Nota de fala: Abrir com o dado de subnotificação como gancho.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Alguma tese é formulada sem evidência rastreável citada explicitamente.
2. O roteiro de slides excede significativamente a proporção de 1
   slide/minuto para a duração estimada.

## Quality Criteria

- [ ] Existem entre 3 e 5 teses, cada uma com contra-argumento e resposta.
- [ ] Existem entre 10 e 15 perguntas de banca antecipadas com resposta.
- [ ] O slide final de contribuição recupera os objetivos apresentados nos
      primeiros slides.
