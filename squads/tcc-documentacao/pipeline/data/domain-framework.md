# Domain Framework — Squad Documentação TCC (Amparo)

> Frameworks operacionais consolidados a partir dos `artifacts.operational_framework`
> de cada agente definido em `design.yaml`. Cada agente também mantém sua própria
> cópia destes processos nos arquivos de task correspondentes
> (`agents/{agent-id}/tasks/*.md`) — este arquivo é a referência central e
> consolidada para consulta cruzada.

## Beatriz Bibliografia — Pesquisa Acadêmica e de Dados Públicos

1. Carregar o foco de pesquisa definido no checkpoint anterior (tema do dia +
   recorte temporal, se aplicável) e o contexto do projeto Amparo (company.md).
2. Mapear o panorama de fontes antes de buscar: dados/estatísticas → fontes
   oficiais (FBSP, Senado/DataSenado, Ministério da Justiça, IPEA, ONU
   Mulheres); legislação → Planalto, Câmara, Senado, tribunais; benchmarking →
   lojas de apps, imprensa especializada, literatura acadêmica (PMC, MDPI,
   Scielo).
3. Executar buscas focadas por subtema (dados, legislação, benchmarking)
   coletando 2-3 fontes de qualidade por subtema.
4. Cruzar cada dado-chave contra pelo menos uma segunda fonte independente.
   Atribuir nível de confiança: ALTA (3+ fontes concordam), MÉDIA (2 fontes),
   BAIXA (fonte única ou dados conflitantes).
5. Para legislação, verificar se a norma citada está vigente (checar alterações
   posteriores).
6. Para benchmarking, documentar funcionalidades, diferenciais e gaps/críticas
   conhecidas de cada solução.
7. Registrar data de acesso de cada fonte e URL completa.
8. Sinalizar contradições entre fontes explicitamente, em vez de escolher um
   lado silenciosamente.
9. Compilar o research brief no formato padrão: Key Findings, Legislação
   Aplicável, Benchmarking, Sources, Gaps, Recomendações.
10. Revisar o brief final contra o checklist de qualidade antes de entregá-lo ao
    checkpoint de aprovação.

## Diana Defesa — Estratégia de Argumentação e Defesa Acadêmica

1. Carregar o relatório estruturado (Helena Hipótese) e o research-brief.md
   (Beatriz Bibliografia) como insumos primários.
2. Identificar a cadeia lógica central: problema de pesquisa → objetivo →
   contribuição/solução (Amparo) → evidência de suporte.
3. Formular 3-5 teses argumentativas centrais, cada uma defensável com dados
   concretos.
4. Para cada tese, identificar o contra-argumento mais provável da banca e
   preparar a resposta com evidência de suporte.
5. Compilar 10-15 perguntas frequentes de banca com resposta preparada de 2-4
   frases cada.
6. Estruturar o roteiro do slide deck na proporção de 1 slide por minuto de
   fala (apresentação de 20-30 min).
7. Para cada slide, especificar título, conteúdo-chave e nota de fala sugerida.
8. Revisar se a sequência do deck conta uma história coerente e se a conclusão
   recupera a promessa da introdução.
9. Verificar que toda tese e resposta cita a fonte de evidência de origem.
10. Entregar o pacote de argumentação para revisão de Renata Referência.

## Helena Hipótese — Redação de Monografia e Relatórios Acadêmicos

1. Carregar o research-brief.md aprovado e o contexto do projeto Amparo
   (company.md) antes de redigir qualquer parágrafo.
2. Construir o outline seguindo a estrutura ABNT (NBR 14724:2024): introdução →
   desenvolvimento → considerações finais. Compartilhar o outline antes da
   redação completa.
3. No referencial teórico, organizar achados por subtema e atribuir cada
   afirmação a uma fonte usando o sistema autor-data (NBR 10520:2023).
4. Redigir o problema de pesquisa com recortes específicos e verificáveis.
5. Redigir objetivos com verbos de ação mensuráveis (desenvolver, avaliar,
   comparar, propor).
6. Verificar correspondência direta entre cada objetivo específico e uma seção
   dos resultados/discussão.
7. Usar citação direta apenas quando a formulação exata for relevante; preferir
   paráfrase para a maior parte do referencial teórico.
8. Redigir as considerações finais retomando o problema e os objetivos, sem
   introduzir conteúdo novo.
9. Revisar o rascunho: jargão definido na primeira menção, parágrafos com no
   máximo 4-5 frases, subtítulos a cada 200-300 palavras.
10. Compilar a lista de referências no formato NBR 6023:2025, com
    correspondência 1:1 entre citações e referências.
11. Após aprovação final (checkpoint), consolidar relatorio-tcc.md +
    argumentacao-defesa.md em um documento Markdown final único e exportar
    para DOCX e PDF via pandoc (com fallback de instalação via Homebrew e
    fallback de entrega parcial se a geração de PDF falhar).

## Renata Referência — Revisão de Qualidade Acadêmica e Normas ABNT

1. Carregar critérios de qualidade (quality-criteria.md), o research brief
   original e os outputs de Helena e Diana antes de iniciar a leitura.
2. Ler o relatório estruturado completo do início ao fim sem pontuar durante a
   leitura.
3. Ler o pacote de argumentação e verificar consistência cruzada: toda tese
   deve corresponder a um trecho do relatório e a uma fonte do research brief.
4. Pontuar cada critério individualmente (1-10) com justificativa escrita:
   conformidade ABNT, alinhamento problema-objetivos-resultados, solidez das
   evidências, qualidade da argumentação, clareza/legibilidade.
5. Para cada nota não-10, identificar a passagem exata responsável pela perda
   de pontos.
6. Aplicar regra de decisão: APROVAR (média >= 7 e nenhum critério < 4);
   REJEITAR (média < 7 ou qualquer critério < 4); APROVAÇÃO CONDICIONAL (média
   >= 7 mas critérios não-críticos entre 4-6).
7. Para toda rejeição, fornecer correção específica e acionável.
8. Separar "Mudança obrigatória" de "Sugestão (não-bloqueante)".
9. Reconhecer pelo menos um ponto forte explícito, mesmo em rejeição.
10. Compilar o veredito estruturado final e entregar ao checkpoint de aprovação.

## Decisão de Roteamento entre Agentes

- **Pesquisa → Redação**: Beatriz entrega o research brief aprovado (checkpoint
  Step 3) antes que Helena inicie a redação do relatório (Step 4).
- **Redação → Argumentação**: Diana só constrói teses depois que o relatório de
  Helena existe (Step 5 depende do output de Step 4).
- **Revisão → Rejeição**: se Renata rejeitar (Step 6), o pipeline retorna ao
  Step 4 (`on_reject: 4`) para Helena revisar o relatório — a argumentação de
  Diana é refeita na sequência natural do pipeline.
- **Aprovação final → Exportação**: a consolidação e exportação para DOCX/PDF
  (Step 8, Helena Hipótese) só ocorre após o checkpoint de aprovação final
  (Step 7) — nunca exportar conteúdo não aprovado.
