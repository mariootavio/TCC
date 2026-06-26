# Research Brief — Squad Documentação TCC (Amparo)

> Documento de referência compilado na fase de Design a partir da pesquisa web da
> Fase B do discovery. Esta é a base inicial de conhecimento da squad — a versão
> definitiva e completa do research brief é gerada por **Beatriz Bibliografia**
> durante a execução real do pipeline (Step 2), com o foco escolhido pelo usuário
> no checkpoint "Foco da Pesquisa" (Step 1), e salva em
> `squads/tcc-documentacao/pipeline/data/research-brief.md` (sobrescrevendo este
> arquivo) ou em `squads/tcc-documentacao/output/` conforme o run em andamento.

## Contexto da Pesquisa

Esta squad apoia a documentação acadêmica (TCC) do projeto **Amparo** — uma
plataforma mobile de denúncia e proteção contra violência doméstica contra
mulheres no Brasil, com funcionalidades de emergência, documentação segura de
evidências, rede de apoio pessoal e acesso a profissionais. A pesquisa cobre
cinco frentes que sustentam a introdução, justificativa, referencial teórico e
argumentação de defesa do trabalho.

## 1. Dados e Estatísticas — Violência Doméstica no Brasil

- Em 2025, **1.568 mulheres** foram vítimas de feminicídio no Brasil — novo
  recorde histórico, alta de **4,7%** em relação a 2024 (1.492 vítimas). Desde a
  tipificação do crime em 2015, ao menos 13.703 mulheres já foram mortas por essa
  razão no país.
  Confiança: ALTA. Fonte: 20º Anuário Brasileiro de Segurança Pública (FBSP, 2026).
- Estudo do Observatório da Mulher contra a Violência (Senado/DataSenado) estima
  **subnotificação de 61%** — 6 em cada 10 mulheres vítimas de violência não
  procuram a delegacia para denunciar.
  Confiança: ALTA. Fonte: DataSenado / Câmara dos Deputados.
- Cerca de **64-66% dos feminicídios** ocorrem dentro da própria residência da
  vítima, e **8 em cada 10** são cometidos por companheiro ou ex-companheiro.
  Confiança: ALTA. Fonte: Nota Técnica FBSP — Dia da Mulher 2026.
- Apenas **24%** das brasileiras afirmam conhecer "muito" a Lei Maria da Penha;
  **75%** dizem conhecer "pouco".
  Confiança: ALTA. Fonte: DataSenado, 2024.

## 2. Legislação Aplicável

- **Lei 11.340/2006 (Lei Maria da Penha)**: cria mecanismos de proteção e as
  medidas protetivas de urgência (MPU). Já sofreu 18+ alterações desde 2006 —
  sempre verificar a redação vigente antes de citar.
- **Lei 14.022/2020**: torna o atendimento a vítimas serviço essencial durante
  calamidade pública; prevê canais de comunicação virtual e prazo de **48h**
  para encaminhamento de denúncias do Ligue 180.
- **Lei 15.125/2025 ("Botão do Pânico")**: permite cumulação de MPU com
  monitoramento eletrônico do agressor e dispositivo de alerta de aproximação —
  geralmente dependente de autorização judicial prévia.
- **PL 1242/24** (em tramitação): prevê que estados disponibilizem app de
  denúncia com recurso de acessibilidade — sinaliza demanda legislativa em curso
  alinhada à proposta do Amparo.

## 3. Benchmarking — Apps e Soluções Similares

| App | Origem | Diferencial | Gap conhecido |
|---|---|---|---|
| PenhaS | Brasil (Instituto AzMina) | Combina tecnologia + curadoria humana (voluntárias) | Depende de acionamento manual da vítima |
| Circle of 6 | EUA | UX de 2 toques, mensagens sociais discretas | Sem integração com legislação brasileira (LMP/MPU) |
| bSafe | Noruega/internacional | Evidência forense (vídeo+geo com timestamp) | Armazenamento local de provas é vulnerável |
| Botão do Pânico estadual (PR, AM) | Brasil (estadual) | Acionamento direto da PM com geolocalização | Depende de liberação judicial prévia |

Gaps identificados na literatura (revisão sistemática MDPI/PMC, 2023 — 621 apps
mapeados, 136 revisados em profundidade):
- Falta de automação: alertas dependem de acionamento manual.
- Dependência de conectividade: falham sem internet/sinal.
- Armazenamento local de provas é vulnerável caso o agressor acesse o celular.
- Medo de o agressor descobrir o app é barreira de adoção citada amplamente.

## 4. Normas ABNT Vigentes

- **NBR 14724:2024** — estrutura de trabalhos acadêmicos.
- **NBR 10520:2023** — citações (atualizada).
- **NBR 6023:2025** — referências (atualizada em maio/2025).
- Erros comuns a evitar: problema de pesquisa vago, verbos intangíveis nos
  objetivos, desalinhamento problema-objetivo-resultados, citação de normas
  desatualizadas (NBR 10520:2002, NBR 6023:2018).

## 5. Defesa de TCC — Boas Práticas

- Apresentação típica de 20-30 minutos, proporção de ~1 slide por minuto.
- Estrutura recomendada: introdução/problema → objetivos → metodologia →
  resultados/contribuição → considerações finais.
- Perguntas de banca mais frequentes: metodologia, limitações do estudo,
  comparação com soluções existentes, viabilidade técnica/jurídica.
- Erros comuns: discrepância entre texto escrito e fala na defesa, slides
  sobrecarregados de texto corrido, falta de ensaio cronometrado, respostas
  defensivas/evasivas a críticas da banca.

## Fontes Consultadas (Fase de Design)

| # | Fonte | Tipo | Relevância |
|---|---|---|---|
| 1 | 20º Anuário Brasileiro de Segurança Pública (FBSP, 2026) | Oficial/Institucional | 9/10 |
| 2 | DataSenado / Câmara dos Deputados | Oficial | 9/10 |
| 3 | Lei 11.340/2006 (Planalto) | Legal | 10/10 |
| 4 | Lei 14.022/2020 (Planalto) | Legal | 9/10 |
| 5 | Lei 15.125/2025 (MPPB/TJAM) | Legal | 9/10 |
| 6 | Revisão sistemática MDPI/PMC (2023) | Acadêmico | 8/10 |
| 7 | TechTudo — PenhaS | Imprensa especializada | 6/10 |
| 8 | PL 1242/24 — Câmara dos Deputados | Legislativo (em tramitação) | 7/10 |

## Gaps de Pesquisa Identificados

- Não há série estatística oficial brasileira consolidada sobre
  efetividade/adoção de apps de denúncia — lacuna a citar explicitamente no TCC
  como contribuição original do trabalho.
- Dados de uso real do PenhaS (número de usuárias ativas, taxa de conversão de
  alerta em atendimento) não são publicamente divulgados pelo Instituto AzMina.
- Não foi encontrada jurisprudência consolidada sobre validade jurídica de
  provas coletadas via apps de terceiros (não estatais) em processos de
  violência doméstica.

## Recomendações para a Argumentação do TCC

1. Usar a subnotificação de 61% como argumento central da justificativa — não é
   falta de violência, é falta de canal acessível de denúncia.
2. Posicionar o Amparo na lacuna entre apps institucionais (dependentes de ordem
   judicial) e apps de ONG (sem integração jurídica formal).
3. Usar os gaps da revisão MDPI 2023 (falta de automação, armazenamento local
   vulnerável) como justificativa técnica para escolhas de arquitetura do Amparo.

---

*Nota: este arquivo serve como ponto de partida em `pipeline/data/`. A execução
real do pipeline (Step 2, Beatriz Bibliografia) produz a versão definitiva e
completa do research brief, com o recorte temático escolhido pelo usuário no
checkpoint "Foco da Pesquisa".*
