# Domain Framework — Brainstorm Amparo

Framework operacional consolidado para as três etapas da squad: pesquisa de
conhecimento (Sofia Sabedoria), geração de ideias (Bruno Brainstorm) e
avaliação/priorização (Carla Critério). Combina quatro ferramentas:
**MoSCoW**, **Kano**, **RICE** e o **checklist DFV de 7 critérios**.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Visão Geral do Fluxo

```
Sofia (pesquisa)  →  Bruno (gera + classifica MoSCoW/Kano)  →  Carla (filtra DFV + ordena RICE)
     conhecimento          ideação pura                          avaliação + priorização
```

Cada ferramenta tem um papel específico e não deve ser usada fora de sua etapa:
MoSCoW e Kano são lentes de **geração/classificação inicial** (Bruno); o checklist
DFV é o **filtro de aprovação** (Carla); RICE é a **ordenação final** das ideias já
aprovadas (Carla). Nunca aplicar RICE antes do filtro DFV — isso prioriza ideias
que talvez nem devessem estar na lista.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 1. MoSCoW — Filtro Rápido de Escopo

Classificação qualitativa de 4 níveis, aplicada por Bruno a cada ideia gerada:

| Categoria | Significado | Critério de uso |
|---|---|---|
| **Must have** | Essencial — sem isso o produto falha em sua proposta de valor central | A ideia resolve diretamente uma dor crítica documentada por Sofia (ex.: risco de segurança imediato) |
| **Should have** | Importante, mas não bloqueante para o lançamento | Resolve um gap relevante, mas a ausência não compromete a missão central |
| **Could have** | Desejável, baixo impacto se ausente | Diferencial nice-to-have, geralmente ligado a conveniência ou personalização |
| **Won't have (this time)** | Conscientemente fora do escopo desta rodada | Depende de inviabilidade técnica/institucional, ou está fora do recorte do brainstorm |

**Regra de uso**: toda ideia classificada como "Won't have" precisa de uma justificativa explícita registrada — nunca apenas omitir a ideia do backlog. Omitir é como o scope creep silencioso (anti-padrão #7) se infiltra.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 2. Kano Model — Lente de Equilíbrio Essencial/Diferencial

Classificação emocional aplicada por Bruno junto ao MoSCoW, para garantir que o
backlog final não seja só "o básico" nem só "ideias ousadas":

| Categoria | Definição | Sinal de identificação |
|---|---|---|
| **Básica** | Esperada pelo usuário; ausência gera insatisfação imediata | Já é commodity de mercado (ex.: botão de pânico) — Bruno só inclui com nota de diferenciação clara |
| **Performance** | "Quanto mais/melhor, mais satisfação" | Funcionalidades escaláveis em qualidade (ex.: granularidade da rede de apoio) |
| **Encantadora (delighter)** | Inesperada, gera entusiasmo desproporcional | Tipicamente ligada a um gap de mercado identificado por Sofia (ex.: IA comportamental) |

**Regra de equilíbrio**: um backlog saudável tem representação nas três categorias.
Um backlog só de "Básicas" é redundante com o mercado; um backlog só de
"Encantadoras" é arriscado e pode ignorar necessidades fundamentais de segurança.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 3. Checklist DFV — Filtro de Aprovação (7 critérios, 2 bloqueantes)

Aplicado por Carla a cada ideia do backlog de Bruno, antes de qualquer priorização:

| # | Critério | Tipo | Pergunta-chave |
|---|---|---|---|
| 1 | Alinhamento com a missão/público | **BLOQUEANTE** | Atende especificamente mulheres em situação de violência doméstica? |
| 2 | Esforço vs. Impacto | Padrão | Compatível com escopo de TCC, com alto impacto potencial? |
| 3 | Diferenciação vs. benchmarking | Padrão | Agrega algo novo frente ao que já existe nos apps concorrentes? |
| 4 | Risco de segurança da própria funcionalidade | **BLOQUEANTE** | Pode expor a usuária ao agressor (notificação visível, ícone identificável, som audível)? |
| 5 | Validação do problema antes da solução | Padrão | Está ancorada em dor documentada por Sofia ou é especulativa? |
| 6 | Viabilidade técnica realista | Padrão | É implementável no escopo do projeto ou depende de integração institucional inviável? |
| 7 | Ausência de scope creep | Padrão | Está dentro do MoSCoW combinado (Must/Should) definido por Bruno? |

**Regra de decisão**:
- Falha em **qualquer critério bloqueante** (1 ou 4) → **REJEITAR a ideia**, independente da pontuação nos demais 5 critérios.
- Aprovação geral exige **pelo menos 5 dos 7 critérios positivos** (incluindo os 2 bloqueantes).
- Ideias aprovadas, mas com esforço alto/impacto baixo (critério 2 fraco) → **APROVAÇÃO CONDICIONAL**, recomendando mover para "Could have" ou para uma rodada futura.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## 4. RICE — Ordenação Final das Ideias Aprovadas

Aplicado por Carla **somente** às ideias que já passaram pelo filtro DFV.
`Score = (Reach × Impact × Confidence) / Effort`

| Eixo | Escala | Como estimar no contexto Amparo |
|---|---|---|
| **Reach** | Número estimado de usuárias afetadas por mês | Baseado no público-alvo do Amparo e na frequência de uso esperada da funcionalidade |
| **Impact** | 3 (massivo) / 2 (alto) / 1 (médio) / 0,5 (baixo) / 0,25 (mínimo) | Quanto a funcionalidade move a missão central (segurança/apoio) |
| **Confidence** | 100% / 80% / 50% | Penaliza estimativas "no chute" — usar 50% para ideias sem dado de apoio direto |
| **Effort** | Pessoa-mês estimado | Compatível com o escopo de implementação de um TCC |

**Regra de uso**: o ranking RICE serve para ordenar prioridade de desenvolvimento
dentro das ideias já aprovadas — nunca para decidir aprovação/rejeição. Essa decisão
é exclusiva do checklist DFV.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Resumo de Responsabilidades por Agente

| Agente | Ferramenta(s) que aplica | Quando |
|---|---|---|
| Sofia Sabedoria | Nenhuma diretamente — fornece a base factual (gaps, dores, conhecimento interno) que alimenta as classificações | Antes da geração |
| Bruno Brainstorm | MoSCoW + Kano | Durante a geração, ideia por ideia |
| Carla Critério | Checklist DFV (7 critérios) → RICE | Após a geração, em duas etapas sequenciais (filtro, depois ordenação) |
