# Quality Criteria — Marca & Design System Amparo

> Compilação dos `Quality Criteria` de cada agente desta squad. Usado por
> Marina Marca como rubrica de revisão e por todos os agentes como critério
> de autoavaliação antes de apresentar qualquer artefato a um checkpoint.

## Renata Referência — Pesquisa de Cor e Público

- Toda recomendação de cor/simbolismo tem fonte nomeada e nível de
  confiança (ALTA/MÉDIA/BAIXA) explícito.
- O documento contém ao menos 3 exemplos reais e verificados de
  benchmarking de identidades de marcas de causas sensíveis.
- Existe ao menos uma ressalva explícita sobre aplicabilidade da
  literatura internacional ao perfil racial/socioeconômico brasileiro.
- O documento final não contém nenhuma decisão de identidade fechada —
  apenas recomendações e achados para Flávia decidir.

## Flávia Fonte — Identidade Visual

- O logo e o ícone do app não contêm nenhum símbolo literal de violência,
  socorro óbvio ou imagem que exponha o propósito do app a quem vê a tela
  de relance.
- No mínimo 2-3 direções de identidade apresentadas, cada uma com paleta
  (hex), tipografia, lógica de símbolo e justificativa.
- Toda direção tem um símbolo/ícone próprio e chamativo — nenhuma é
  apenas o nome "Amparo" estilizado sem elemento gráfico (exigência
  explícita do usuário, não opcional).
- Toda combinação de cor de texto/fundo na paleta recomendada atinge no
  mínimo 4.5:1 (texto normal) ou 3:1 (texto grande), verificado e
  documentado.
- O projeto Claude Design "Amparo — Marca & Design System" foi localizado
  via `list_projects` antes de qualquer `create_project`, e os arquivos
  HTML publicados têm o comentário `<!-- @dsCard group="Abertura" -->` ou
  `group="Identidade"` na primeira linha.
- O framework estratégico do brandkit foi aplicado explicitamente ao
  Amparo, sem uso direto de um visual mode pré-definido sem adaptação.

## Tomás Tokens — Design System

- Todo token semântico referencia exatamente um token primitivo nomeado —
  nenhum valor bruto direto em um componente.
- Cada par semântico relevante de cor texto/fundo tem contraste verificado
  e documentado contra o mínimo WCAG AA aplicável.
- Componentes seguem nomenclatura atômica consistente (ex.:
  `Atoms/Button/Primary`), sem nome genérico.
- O projeto Claude Design usado é o mesmo já criado por Flávia (confirmado
  via `list_projects`/`get_project`, nunca um novo `create_project`).
- A paleta final usa no máximo 5-6 cores-base, com escalas derivadas via
  tokens.

## Marina Marca — Revisão Estruturada

- Toda nota atribuída tem justificativa escrita de ao menos uma frase com
  "porque".
- O contraste WCAG AA de cada par relevante foi recalculado de forma
  independente, não apenas copiado do valor de Tomás.
- Toda correção obrigatória aponta a localização exata (frame, seção ou
  página do projeto Claude Design) e descreve a correção específica a
  aplicar.
- O veredito final (APROVAR/REJEITAR/APROVAR COM RESSALVAS) é consistente
  com as regras de decisão: média ≥7 sem critério <4 e sem gatilho de
  discrição/trauma-informado violado = APROVAR; qualquer um violado =
  REJEITAR.
- A revisão contém ao menos um "Ponto forte:" com exemplo concreto, mesmo
  em veredito de rejeição.
- Toda frase genérica não-quantificada em `identidade-visual.md` ou
  `design-system.md` (checada contra a seção "Palavras a evitar" de
  `.agents/skills/manual-identidade-visual-premium/references/
  vocabulario-design.md`) é apontada como correção obrigatória de
  linguagem, citando o trecho exato.

## Helena Manual — Manual Técnico + Apresentação Premium

Manual técnico (`output/manual-identidade-visual.md`):
- Nenhuma seção documenta como final um valor/token que o veredito de
  Marina reprovou sem a correção confirmada como aplicada.
- Toda regra de uso é executável sem interpretação (número, hex, nome de
  fonte real, unidade de medida) — sem frase genérica proibida.
- A discrição visual aparece como regra explícita e auditável em pelo
  menos um checklist.
- Os 8 blocos da arquitetura padrão do skill `manual-identidade-visual-
  premium` estão todos presentes, adaptados ao porte do Amparo.
- O manual passou 100% da autoavaliação de qualidade do próprio skill.

Apresentação premium (SEGUNDO projeto Claude Design, próprio — "Amparo —
Apresentação do Projeto"):
- Tem entre 8-12 slides curados a partir do manual e do Projeto 1 —
  nunca um dump 1:1 de todo o manual.
- Todo slide usa exclusivamente tokens/logo/mockups já aprovados por
  Flávia/Tomás — nenhuma cor, fonte ou símbolo novo.
- Qualquer imagem gerada por `image-ai-generator` foi validada em
  `--mode test` antes de `--mode production`, e não contém imagética de
  violência doméstica, alarme, ou exposição do propósito do app.
- Publicada num projeto Claude Design SEPARADO do de Flávia/Tomás
  (localizado via `list_projects` antes de `create_project` — nunca
  dentro do Projeto 1, nunca um terceiro projeto duplicado).

## Tabela de Decisão de Veredito (Marina Marca)

| Condição | Veredito |
|---|---|
| Média geral ≥ 7/10 e nenhum critério < 4/10 e nenhum gatilho de discrição/trauma-informado violado | APROVAR |
| Média geral ≥ 7/10 e algum critério não-crítico entre 4-6/10 | APROVAR COM RESSALVAS |
| Média geral < 7/10 | REJEITAR |
| Qualquer critério < 4/10 | REJEITAR (gatilho automático) |
| Qualquer gatilho de discrição/trauma-informado violado | REJEITAR (gatilho automático, independente da média) |

## Critérios Transversais (aplicam-se a toda a squad)

- Toda escolha visual é justificada e rastreável ao brief de marca, à
  pesquisa de Renata, ou ao requisito de discrição/segurança — nunca
  apresentada como preferência estética sem critério.
- Nenhum artefato é apresentado a um checkpoint de aprovação sem que o
  agente responsável tenha verificado seus próprios quality criteria
  primeiro.
- Toda publicação no Claude Design via `DesignSync` usa o projeto correto
  da squad ("Amparo — Marca & Design System"), localizado via
  `list_projects` antes de qualquer `create_project`.
