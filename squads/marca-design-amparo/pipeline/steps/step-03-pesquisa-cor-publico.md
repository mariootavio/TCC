---
execution: subagent
agent: renata-referencia
model_tier: powerful
inputFile: squads/marca-design-amparo/output/brief-design.md
outputFile: squads/marca-design-amparo/output/pesquisa-cor-publico.md
---

# Step 3: Pesquisa de Cor e Público

## Context Loading

Load these files before executing:
- `squads/marca-design-amparo/output/brief-design.md` — brief de design
  aprovado no checkpoint anterior (adjetivos de marca, restrições de cor,
  nível de discrição)
- `_opensquad/_memory/company.md` — contexto do projeto Amparo
  (público-alvo, tom de voz, problema central)
- `squads/tcc-documentacao/pipeline/data/research-brief.md` — perfil
  demográfico exato das vítimas (63,6%-64% negras; 70,5%-71% entre 18-44
  anos; 64,3% das agressões dentro da residência) — NÃO repesquisar este
  dado, apenas reutilizá-lo como ponto de partida demográfico
- `squads/marca-design-amparo/pipeline/data/research-brief.md` — framework
  de design trauma-informado já levantado (seção 1) e benchmarking de
  apps já reaproveitado (seção de resumo)

## Instructions

### Process

1. Carregar o brief de design e o perfil demográfico exato do público do
   Amparo. Nunca tratar o público como "mulheres" de forma genérica — toda
   busca e toda recomendação devem ser calibradas a esse recorte
   demográfico específico.
2. Usar `web_search`/`web_fetch` para pesquisar psicologia de cor e
   simbolismo aplicada especificamente a contextos de trauma/segurança
   pessoal, buscando ativamente por fontes que considerem raça, etnia ou
   contexto socioeconômico — nunca aceitar "psicologia das cores" genérica
   sem tentar essa calibração.
3. Usar `web_search`/`web_fetch` para fazer benchmarking de identidades
   visuais REAIS de ONGs e apps de proteção contra violência doméstica
   (Brasil e internacional) — descrever paleta, simbolismo e tom percebido
   de cada exemplo real encontrado.
4. Para cada achado herdado de literatura internacional, verificar
   explicitamente se a amostra original representa o perfil demográfico do
   Amparo — registrar o gap quando não representar, no mesmo padrão de
   rigor já usado pela squad tcc-documentacao para o gap de
   sub-representação racial na literatura de safety apps.
5. Compilar tudo em `output/pesquisa-cor-publico.md`, separando claramente
   achados de confiança ALTA, MÉDIA e BAIXA, e nunca incluindo uma decisão
   de identidade fechada — apenas recomendações para Flávia decidir no
   Step 5.

## Output Format

```markdown
# Pesquisa de Cor e Público — Amparo

Brief de origem: [adjetivos do brief]
Perfil demográfico de referência: [perfil exato, com fonte]

## 1. Psicologia de Cor Aplicada a Marcas de Proteção
[achados com fonte e nível de confiança]

## 2. Benchmarking de Identidades Reais
| Organização | Paleta observada | Simbolismo | Observação |
|---|---|---|---|
[linhas reais, verificadas]

## 3. Recomendação Consolidada para Flávia
[recomendações organizadas por confiança, com ressalvas de aplicabilidade
racial/cultural explícitas]

## Próximo Passo
Aguardando checkpoint de referências visuais do usuário (Step 4) antes de
Flávia iniciar a criação da identidade visual (Step 5).
```

## Output Example

```markdown
# Pesquisa de Cor e Público — Amparo

Brief de origem: acolhedor, seguro, discreto
Perfil demográfico de referência: mulheres negras (63,6%-64% das vítimas
de feminicídio), 70,5%-71% entre 18-44 anos, 64,3% das agressões dentro da
própria residência (fonte: squads/tcc-documentacao/pipeline/data/research-brief.md,
achado 3, FBSP 2026 — Confiança: ALTA).

## 1. Psicologia de Cor Aplicada a Marcas de Proteção

1.1. Tons frios (azul, verde, lilás) associados a redução de ansiedade
visual em contextos de trauma — confirma o framework já levantado no
research-brief desta squad. Confiança: ALTA.

1.2. GAP DE APLICABILIDADE RACIAL: nenhuma fonte localizada nesta busca
testa especificamente a percepção dessas paletas com mulheres negras
brasileiras. Confiança da ressalva: ALTA (ausência de contra-evidência
encontrada). Recomendação: tratar a paleta fria como ponto de partida
razoável, não como verdade testada para o público majoritário real do
Amparo.

1.3. Tons terrosos não-saturados aparecem com frequência em identidades de
marcas afrocentradas de acolhimento. Confiança: MÉDIA (observação em 3-4
identidades de benchmarking, sem estudo controlado).

## 2. Benchmarking de Identidades Reais

| Organização | Paleta observada | Simbolismo | Observação |
|---|---|---|---|
| Instituto AzMina / PenhaS | Roxo + branco + rosa-magenta | Megafone estilizado | Roxo é cor-símbolo histórica de combate à violência contra a mulher no Brasil — alta força de reconhecimento, risco de "parecer mais uma" |
| [organização real 2] | [paleta] | [simbolismo] | [observação] |
| [organização real 3] | [paleta] | [simbolismo] | [observação] |

## 3. Recomendação Consolidada para Flávia

- Considerar tom frio (base) + acento terroso/quente não-saturado como
  hipótese de calibração ao público específico (ver 1.3).
- Evitar roxo como cor dominante única: maior associação no Brasil a "ONG
  de combate à violência contra a mulher" — risco de diluir identidade
  própria do Amparo.
- Gap a registrar na monografia: ausência de estudo de percepção de cor
  com amostra de mulheres negras brasileiras em contexto de trauma.

## Próximo Passo
Aguardando checkpoint de referências visuais do usuário (Step 4) antes de
Flávia iniciar a criação da identidade visual (Step 5).
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Alguma recomendação de cor/simbolismo aparece sem fonte nomeada e sem
   nível de confiança atribuído.
2. Nenhuma ressalva de aplicabilidade racial/cultural foi registrada para
   achados herdados de literatura internacional — sinal de que a
   calibração ao público real do Amparo não foi feita.

## Quality Criteria

- [ ] Toda recomendação de cor/simbolismo tem fonte nomeada e nível de
      confiança (ALTA/MÉDIA/BAIXA) explícito.
- [ ] O documento contém ao menos 3 exemplos reais e verificados de
      benchmarking de identidades de marcas de causas sensíveis.
- [ ] Existe ao menos uma ressalva explícita sobre aplicabilidade da
      literatura internacional ao perfil racial/socioeconômico brasileiro.
- [ ] O documento final não contém nenhuma decisão de identidade fechada —
      apenas recomendações e achados para Flávia decidir.
