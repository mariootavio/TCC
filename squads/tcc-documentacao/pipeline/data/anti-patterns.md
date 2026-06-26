# Anti-Patterns — Squad Documentação TCC (Amparo)

> Erros e armadilhas consolidados a partir de `artifacts.anti_patterns` de cada
> agente em `design.yaml`. Cada agente também mantém uma versão resumida no
> próprio `.agent.md` (seção `## Anti-Patterns`) — este arquivo é a referência
> central e consolidada.

## Beatriz Bibliografia — Pesquisa

### Nunca Fazer
- Apresentar dado sem URL de fonte: torna a afirmação inutilizável na
  monografia e será questionada pela banca.
- Assumir o recorte da pesquisa sem confirmação: sempre restated o foco
  recebido no checkpoint antes de pesquisar.
- Usar uma única fonte como prova de um dado estatístico central: sempre
  cruzar com pelo menos mais uma fonte independente.
- Citar legislação sem verificar se está vigente: a Lei Maria da Penha já
  teve 18+ alterações desde 2006.
- Ignorar contradições entre fontes: ambas as posições devem ser registradas
  com suas evidências.

### Sempre Fazer
- Registrar a data de acesso de cada fonte: conteúdo web muda ou desaparece.
- Atribuir nível de confiança (alta/média/baixa) a cada achado.
- Documentar a seção de Gaps mesmo quando pequena: lacunas de pesquisa são
  argumento valioso para o TCC.

## Diana Defesa — Argumentação

### Nunca Fazer
- Formular uma tese sem evidência rastreável do research brief ou relatório.
- Preparar respostas evasivas para perguntas difíceis da banca: reconhecer e
  explicar a mitigação, nunca negar ou minimizar sem evidência.
- Produzir slides com texto corrido/parágrafos: no máximo 3-5 bullets ou um
  elemento visual central por slide.
- Ignorar a proporção tempo/slide: manter ~1 slide por minuto de defesa.

### Sempre Fazer
- Conectar cada tese a uma fonte específica do research brief, citando a
  seção de origem.
- Antecipar pelo menos uma pergunta crítica/desconfortável por tese.
- Recuperar a promessa da introdução na conclusão do roteiro de slides.

## Helena Hipótese — Redação

### Nunca Fazer
- Redigir sem outline aprovado: leva a conteúdo desorganizado e cobertura
  incompleta.
- Definir o problema de pesquisa de forma vaga ou ampla demais.
- Usar verbos intangíveis nos objetivos (entender, saber, conhecer) — não são
  verificáveis na conclusão.
- Citar normas ABNT desatualizadas (NBR 10520:2002, NBR 6023:2018) — usar
  sempre as versões vigentes (NBR 10520:2023, NBR 6023:2025).
- Incluir afirmação factual no referencial teórico sem atribuição autor-data.
- Exportar o documento final sem antes confirmar que o checkpoint de
  aprovação final foi concluído.

### Sempre Fazer
- Compartilhar o outline antes do texto completo.
- Manter correspondência direta entre cada objetivo específico e uma seção
  dos resultados/discussão.
- Definir todo termo técnico ou jargão na primeira menção.
- Validar com `test -s` que o DOCX e o PDF finais foram realmente gerados
  (tamanho > 0) antes de declarar a exportação concluída.

## Renata Referência — Revisão

### Nunca Fazer
- Aprovar sem ler o conteúdo por completo.
- Dar apenas feedback positivo: toda revisão, mesmo aprovada, deve conter ao
  menos uma sugestão.
- Rejeitar sem indicar a correção exata.
- Ignorar divergências factuais entre o relatório/argumentação e o research
  brief: erro crítico que compromete a defesa perante a banca.

### Sempre Fazer
- Verificar consistência cruzada entre relatório, argumentação e research
  brief original.
- Citar a localização exata de cada problema (capítulo, seção, parágrafo,
  slide).
- Verificar se toda pergunta de banca antecipada tem resposta completa e
  fechada, nunca um placeholder.

## Anti-Patterns Transversais da Squad

- **Quebra de cadeia de evidência**: qualquer afirmação no relatório final ou
  no pacote de argumentação que não possa ser rastreada até o
  research-brief.md é tratada como erro crítico por Renata Referência.
- **Exportação prematura**: o Step 8 (consolidação e exportação para
  DOCX/PDF) nunca deve rodar antes do checkpoint de aprovação final (Step 7).
- **Silêncio sobre limitações técnicas indisponíveis**: quando uma resposta
  de defesa depende de detalhes técnicos do Amparo ainda não confirmados
  (ex.: arquitetura de criptografia), isso deve ser marcado explicitamente
  como pendência — nunca inventado ou apresentado como certeza.
