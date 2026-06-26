# Quality Criteria — Squad Documentação TCC (Amparo)

> Critérios de qualidade consolidados a partir de `artifacts.quality_criteria`
> de cada agente em `design.yaml`. Renata Referência usa este arquivo como
> rubrica central na task `revisar-relatorio-e-argumentacao`.

## Beatriz Bibliografia — Research Brief

- [ ] Todo achado-chave (Key Finding) tem URL de fonte e data de acesso
      registradas.
- [ ] Todo achado tem nível de confiança (alta/média/baixa) explícito com
      justificativa.
- [ ] Pelo menos 2 fontes independentes corroboram cada achado de confiança
      alta.
- [ ] A seção de legislação cita a norma vigente, não uma redação
      desatualizada.
- [ ] A seção de Gaps está preenchida, mesmo que com 1-2 itens.
- [ ] O brief segue a estrutura padrão: Key Findings, Legislação Aplicável,
      Benchmarking, Sources, Gaps, Recomendações — nenhuma seção ausente.

## Diana Defesa — Pacote de Argumentação

- [ ] Cada tese argumentativa cita a seção exata do research brief ou
      relatório de onde vem a evidência.
- [ ] Existem ao menos 10 perguntas de banca antecipadas, cada uma com resposta
      preparada de 2-4 frases.
- [ ] O roteiro de slides mantém a proporção de aproximadamente 1 slide por
      minuto de apresentação.
- [ ] Toda limitação do estudo mencionada no relatório aparece também no
      roteiro de slides e tem resposta preparada associada.
- [ ] A conclusão do roteiro de slides recupera explicitamente o objetivo geral
      apresentado nos primeiros slides.

## Helena Hipótese — Relatório e Documento Final

- [ ] O outline foi estruturado e está alinhado à NBR 14724:2024 antes da
      redação do texto completo.
- [ ] Todo objetivo específico usa verbo de ação mensurável e tem
      correspondência com uma seção dos resultados.
- [ ] Toda afirmação factual no referencial teórico tem atribuição autor-data
      conforme NBR 10520:2023.
- [ ] A lista de referências segue NBR 6023:2025 e tem correspondência 1:1 com
      as citações no corpo do texto.
- [ ] Nenhum parágrafo excede 5 frases; nenhuma seção excede 300 palavras sem
      subtítulo.
- [ ] As considerações finais retomam explicitamente o problema de pesquisa e
      cada objetivo específico, sem introduzir conteúdo novo.
- [ ] O documento final exportado (DOCX e/ou PDF) existe, tem tamanho > 0, e
      contém tanto o relatório quanto o pacote de argumentação/slides.

## Renata Referência — Critérios da Revisão

- [ ] Toda nota atribuída (1-10) vem acompanhada de justificativa escrita de
      pelo menos uma frase.
- [ ] Toda mudança obrigatória aponta a localização exata
      (capítulo/seção/parágrafo/slide) e a correção específica.
- [ ] O veredito final é consistente com as notas atribuídas, seguindo a regra:
      média >= 7 e nenhum critério < 4 = APROVAR; média < 7 ou qualquer
      critério < 4 = REJEITAR; caso intermediário = APROVAÇÃO CONDICIONAL.
- [ ] Toda divergência factual entre o conteúdo revisado e o research-brief.md
      é identificada e tratada como gatilho de rejeição automática.
- [ ] Existe ao menos um "Ponto forte" explícito mesmo em revisões de rejeição.
- [ ] O número da revisão atual e o limite de 3 ciclos antes de escalar para o
      usuário estão registrados no cabeçalho da revisão.

## Regra de Decisão Geral (Aplicada por Renata Referência)

| Resultado | Condição |
|---|---|
| **APROVAR** | Média geral >= 7/10 E nenhum critério individual < 4/10 |
| **APROVAÇÃO CONDICIONAL** | Média geral >= 7/10 MAS algum critério não-crítico entre 4-6/10 |
| **REJEITAR** | Média geral < 7/10 OU qualquer critério individual < 4/10 |

## Limite de Ciclos de Revisão

- Máximo de 3 ciclos de revisão (rejeição → correção → reenvio) antes de
  escalar a decisão para o usuário no checkpoint.
- O pipeline usa `on_reject: 4` no Step 6 (revisão de qualidade) — uma
  rejeição retorna o fluxo a Helena Hipótese (Step 4) para correção do
  relatório.
