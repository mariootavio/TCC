TESES ARGUMENTATIVAS — TCC AMPARO

TESE 1: O agravamento estatístico recente da violência doméstica no Brasil, combinado à concentração de agressões dentro do próprio domicílio, justifica uma solução de proteção centrada no ambiente doméstico, e não apenas em espaços públicos.

Evidência de suporte: 1.450 a 1.492 feminicídios em 2024 (maior número da série histórica desde 2015), com 64,3% dos casos ocorrendo dentro da própria residência da vítima. (Fonte: relatorio-tcc.md, Seção 2.1; research-brief.md, "Key Findings", itens 1, 2 e 5, Confiança: ALTA)

Contra-argumento provável da banca: "Se a maior parte da violência ocorre dentro de casa, como um aplicativo no celular da própria vítima pode ajudar, já que o agressor frequentemente tem acesso físico ao mesmo ambiente e, possivelmente, ao próprio aparelho?"

Resposta preparada: Justamente por isso, o Amparo foi concebido a partir das lacunas documentadas na literatura sobre exposição do dispositivo — daí a centralidade das funcionalidades de discrição visual e de documentação segura de provas, que respondem à vulnerabilidade de armazenamento local identificada por Sumra et al. (2023) em 136 aplicativos similares. O risco de acesso físico ao aparelho pelo agressor é uma premissa de design, não uma lacuna ignorada.

---

TESE 2: O marco legal brasileiro mais recente (2025-2026) está expandindo ativamente o uso de tecnologia de monitoramento e alerta na proteção a mulheres, o que posiciona o Amparo como aderente a uma tendência regulatória, e não como proposta especulativa.

Evidência de suporte: Leis nº 15.125/2025, nº 15.383/2026 e nº 15.384/2026, todas sancionadas entre abril de 2025 e abril de 2026, ampliam o monitoramento eletrônico de agressores e o uso de dispositivos de alerta tipo "botão do pânico". (Fonte: relatorio-tcc.md, Seção 2.2; research-brief.md, "Legislação Aplicável", itens 3-5, Confiança: ALTA — textos oficiais do Planalto/Casa Civil)

Contra-argumento provável da banca: "Essas leis tratam de monitoramento de agressores via tornozeleira eletrônica, decretado pelo Judiciário — não é a mesma coisa que um aplicativo voluntário operado pela própria vítima. Por que equiparar as duas situações?"

Resposta preparada: A equiparação não é entre os mecanismos técnicos, mas entre o princípio regulatório: o legislador está formalizando que o alerta de proximidade e o acionamento assistido fazem parte do arsenal legítimo de proteção, inclusive "em formato de aplicativo de celular", conforme o texto da própria Lei nº 15.125/2025. O Amparo opera no espaço anterior à medida protetiva judicial, ocupando uma lacuna que a legislação reconhece como relevante, ainda que regule formalmente apenas o monitoramento pós-MPU.

---

TESE 3: As soluções tecnológicas similares já existentes no Brasil e no exterior não resolvem de forma integrada três necessidades centrais da vítima — documentação segura, rede de apoio e acionamento de emergência —, o que caracteriza uma lacuna de mercado documentada, e não apenas uma hipótese do autor.

Evidência de suporte: PenhaS oferece documentação e rede de apoio, mas depende de acionamento manual; o Botão do Pânico estadual oferece acionamento direto à polícia, mas exige MPU prévia; bSafe oferece acionamento por voz, mas restringe funcionalidades essenciais à versão paga. (Fonte: relatorio-tcc.md, Seção 2.3; research-brief.md, "Benchmarking — Apps Similares")

Contra-argumento provável da banca: "Por que não integrar essas funcionalidades a uma solução já existente e consolidada, como o PenhaS, em vez de criar um novo aplicativo concorrente?"

Resposta preparada: O PenhaS é mantido por uma organização do terceiro setor (Instituto AzMina) sem integração formal e uniforme com o Judiciário/Segurança Pública em todos os estados, e a literatura aponta baixo conhecimento do aplicativo entre o público-alvo por falta de publicidade. O Amparo não pretende substituir iniciativas existentes, mas testar uma arquitetura alternativa que combine os três pilares de forma nativa, contribuindo como objeto de pesquisa acadêmica independentemente de sua adoção em produção.

---

TESE 4: As lacunas técnicas documentadas na literatura internacional sobre aplicativos de proteção (acionamento manual exclusivo, armazenamento local vulnerável, ausência de IA e de modo offline) constituem evidência científica, não intuição do autor, para as escolhas de arquitetura do Amparo.

Evidência de suporte: Revisão sistemática de 136 aplicativos (Sumra et al., 2023) constatou ausência de detecção automática de risco, de uso de IA e de modo offline em toda a amostra. (Fonte: relatorio-tcc.md, Seção 2.3 e 4.2; research-brief.md, "Gaps Identificados na Literatura", itens 1-3, Confiança: ALTA)

Contra-argumento provável da banca: "O Amparo efetivamente implementa essas funcionalidades (detecção automática, modo offline) ou elas permanecem apenas como justificativa teórica no referencial?"

Resposta preparada: O Amparo implementa criptografia das evidências coletadas, com armazenamento em nuvem em vez de apenas na memória local do dispositivo, respondendo diretamente à vulnerabilidade de armazenamento documentada por Sumra et al. (2023). A detecção automática de risco e o modo offline, também identificados como lacunas na mesma revisão sistemática, ainda não estão implementados nesta fase do projeto e são assumidos explicitamente como trabalho futuro, não como funcionalidade já entregue.

---

TESE 5: A sub-representação de mulheres negras nas amostras de estudos internacionais sobre aplicativos de proteção, em contraste com o perfil real das vítimas de feminicídio no Brasil, reforça a necessidade de uma solução nacional desenhada para esse perfil demográfico.

Evidência de suporte: Doria et al. (2021) constataram amostras predominantemente brancas nos estudos da área, enquanto 63,6% das vítimas de feminicídio no Brasil em 2024 eram mulheres negras (FBSP, 2026). (Fonte: relatorio-tcc.md, Seção 2.3 e 4.2; research-brief.md, "Gaps Identificados na Literatura", item 5, Confiança: MÉDIA)

Contra-argumento provável da banca: "Como o desenho do Amparo concretamente incorpora essa preocupação com representatividade racial, além de mencioná-la no referencial teórico?"

Resposta preparada: Esta é uma limitação real e reconhecida do projeto nesta fase: a preocupação com representatividade racial está presente como intenção declarada e como justificativa fundamentada no referencial teórico, mas ainda não foi traduzida em pesquisa de usuária formal com esse recorte demográfico específico. O trabalho assume essa lacuna explicitamente como direção de pesquisa futura, em vez de afirmar uma validação que não ocorreu.

PERGUNTAS ANTECIPADAS DA BANCA

[Categoria: Metodologia]

P1: "A metodologia deste trabalho é de revisão documental e bibliográfica. Por que não foi feita uma pesquisa de campo ou entrevista com vítimas reais?"
R1: A pesquisa de campo com vítimas de violência doméstica exigiria protocolo ético específico para população em situação de vulnerabilidade, com aprovação de comitê de ética, o que está fora do escopo temporal deste TCC. A metodologia documental permite, ainda assim, fundamentar as escolhas de design em evidência científica publicada e em dados oficiais, sendo a validação direta com usuárias indicada como trabalho futuro.

P2: "Os dados estatísticos usados têm divergência entre fontes — por exemplo, o número de feminicídios em 2024 varia entre 1.450 e 1.492 conforme a fonte. Como o trabalho lida com isso?"
R2: Essa divergência está documentada explicitamente no research brief e no relatório, na forma de uma faixa (1.450-1.492), em vez de uma escolha arbitrária de uma das fontes. A divergência decorre de bases de dados e metodologias distintas entre o Fórum Brasileiro de Segurança Pública e o Ministério das Mulheres, ambas oficiais, e essa transparência metodológica é tratada como boa prática acadêmica, não como fragilidade a esconder.

P3: "Por que o recorte temporal da pesquisa não definiu um período fixo, usando 'dados mais recentes disponíveis' como critério?"
R3: O tema envolve legislação em rápida transformação — três leis relevantes foram sancionadas somente entre 2025 e 2026 — de modo que um recorte temporal fixo poderia excluir informação legal vigente crítica para o argumento central do trabalho. Priorizar a fonte mais recente disponível, com data de acesso registrada, mantém o trabalho atualizado sem comprometer a rastreabilidade.

[Categoria: Limitações]

P4: "O trabalho não localizou um percentual nacional consolidado de subnotificação de violência doméstica. Isso não é uma limitação grave, já que a subnotificação é citada como argumento central?"
R4: É uma limitação reconhecida explicitamente nas Considerações Finais do relatório. O Atlas da Violência confirma qualitativamente a existência e a relevância do fenômeno, mas não fornece um percentual nacional único; por isso, o trabalho evita citar qualquer número específico de subnotificação sem fonte direta, tratando essa ausência como gap de pesquisa para trabalhos futuros junto ao Ministério da Saúde (Sinan) ou ao CNJ.

P5: "O trabalho não encontrou nenhuma revisão sistemática acadêmica focada especificamente em aplicativos brasileiros de proteção. Como isso afeta a solidez do referencial teórico?"
R5: De fato, as revisões sistemáticas mais robustas localizadas (Sumra et al., 2023; Doria et al., 2021) tratam majoritariamente de aplicativos norte-americanos e europeus. Essa ausência está documentada como gap de pesquisa, e o referencial teórico sobre apps brasileiros (PenhaS, Botão do Pânico) baseia-se em fontes institucionais e de imprensa especializada, não em revisão acadêmica sistemática nacional — uma oportunidade clara de pesquisa futura.

P6: "O trabalho não validou a solução com usuárias reais em situação de violência doméstica. Isso não compromete a conclusão de que o Amparo resolve as lacunas identificadas?"
R6: Sim, essa é uma limitação reconhecida explicitamente. O trabalho demonstra que o Amparo é fundamentado em lacunas documentadas cientificamente, mas não demonstra, neste estágio, que a solução proposta efetivamente as resolve na prática — essa validação empírica é indicada como direção de pesquisa futura, condicionada a aprovação ética para pesquisa com população vulnerável.

[Categoria: Comparação com soluções existentes]

P7: "Por que não usar uma solução já existente e institucionalizada, como o Botão do Pânico estadual, em vez de desenvolver um novo aplicativo?"
R7: O Botão do Pânico estadual exige que a vítima já tenha obtido uma medida protetiva de urgência — pressupõe denúncia formal já realizada. O Amparo atua antes desse ponto, no momento em que a vítima ainda está documentando provas e buscando apoio, complementando a solução estatal em vez de competir com ela.

P8: "O PenhaS já atende a necessidade de documentação e rede de apoio. O que o Amparo oferece que o PenhaS não oferece?"
R8: O PenhaS depende de acionamento manual da vítima e é mantido por uma organização do terceiro setor, sem integração jurídica formal uniforme em todo o país, além de ter baixa divulgação documentada entre o público-alvo. O Amparo busca testar uma arquitetura alternativa baseada nas lacunas técnicas (acionamento, armazenamento, ausência de IA) documentadas na literatura internacional, com aderência explícita ao marco legal brasileiro mais recente.

P9: "Aplicativos internacionais como o bSafe já têm anos de mercado e investimento. Por que uma solução acadêmica brasileira conseguiria superá-los?"
R9: O objetivo deste TCC não é superar comercialmente soluções internacionais consolidadas, mas demonstrar, academicamente, que essas soluções não foram desenhadas para o marco legal e o perfil demográfico brasileiro — por exemplo, o bSafe restringe funcionalidades essenciais à versão paga, criando barreira de acesso incompatível com a população em maior vulnerabilidade socioeconômica no Brasil.

[Categoria: Viabilidade técnica e jurídica]

P10: "Como o Amparo garante que o armazenamento de provas não cria um novo risco de exposição de dados sensíveis da vítima?"
R10: As provas coletadas pelo Amparo são criptografadas e armazenadas em nuvem, em vez de apenas na memória local do dispositivo — a escolha de arquitetura responde diretamente à vulnerabilidade de armazenamento local documentada por Sumra et al. (2023) em 136 aplicativos analisados. O risco de exposição em caso de acesso físico ao aparelho pelo agressor é mitigado por essa decisão de não depender do armazenamento local como única camada de proteção.

P11: "As provas coletadas pelo Amparo (ex.: gravação de áudio) têm validade jurídica garantida em todos os tribunais brasileiros?"
R11: A literatura indica que mesmo o PenhaS, aplicativo mais estabelecido no Brasil, tem parcerias pontuais com Defensorias Públicas (NUDEMs) e recomendação formal apenas em unidades específicas, sem validade jurídica nacional uniforme confirmada. O Amparo segue a mesma lógica documentada no campo: a prova digital serve como elemento de apoio à denúncia, e sua admissibilidade formal depende de avaliação caso a caso pelo Judiciário, o que é reconhecido como limitação do campo como um todo, não exclusiva do Amparo.

P12: "O Amparo entra em conflito ou se sobrepõe ao Projeto de Lei nº 1242/2024, que prevê um aplicativo único estatal de denúncia?"
R12: Não necessariamente. O PL 1242/2024 ainda está em tramitação e prevê uma solução estatal voltada à fase de denúncia formal e encaminhamento às autoridades. O Amparo atua, em parte, em um momento anterior — documentação e apoio antes da decisão de denunciar — podendo ser complementar a uma futura solução estatal, e não concorrente direto.

P13: "Que garantias existem de que o Amparo continuará disponível e mantido no longo prazo, diferentemente de iniciativas que desaparecem?"
R13: Nenhuma, nesta fase: o Amparo é um protótipo/MVP de caráter acadêmico, desenvolvido no âmbito deste TCC, sem plano formal de manutenção ou produção contínua definido até o momento. Essa é uma limitação reconhecida explicitamente, não uma garantia que o trabalho pretende sustentar — a literatura internacional aponta justamente a descontinuidade como problema recorrente do campo, o que reforça que a sustentabilidade de longo prazo é uma questão aberta também para o Amparo, a ser endereçada apenas em eventual continuidade do projeto fora do escopo deste TCC.

[Categoria: Contribuição e originalidade]

P14: "Qual é, de forma objetiva, a contribuição original deste trabalho frente à literatura e às soluções já existentes?"
R14: A contribuição original está na síntese e aplicação, ao contexto legal e demográfico brasileiro mais recente (2025-2026), de lacunas técnicas documentadas pela literatura internacional, propondo uma arquitetura de produto que endereça simultaneamente documentação segura, rede de apoio pré-denúncia e acionamento de emergência — combinação não encontrada de forma integrada em nenhuma das soluções comparadas neste trabalho.

ROTEIRO DE SLIDE DECK — DEFESA TCC AMPARO
Duração estimada: 20 minutos | 19 slides (~1,05 min/slide)

SLIDE 1 — Capa
Conteúdo: Título do TCC, nome do autor, orientador(a), instituição, data.
Nota de fala: Apresentação protocolar, 15 segundos.

SLIDE 2 — O problema em um dado
Conteúdo: "Até 1.492 feminicídios no Brasil em 2024 — o maior número da série histórica" (FBSP, 2026). Visual: número grande, sem texto corrido.
Nota de fala: Abrir com o dado de feminicídio como gancho — é o número que justifica a urgência do tema.

SLIDE 3 — Onde a violência acontece
Conteúdo: "64,3% dos feminicídios ocorrem dentro da própria residência da vítima" (FBSP, 2026).
Nota de fala: Mostrar que o ambiente doméstico, não a rua, é o espaço de maior risco — fundamenta a escolha de uma solução centrada na vítima, não em espaços públicos.

SLIDE 4 — Justificativa
Conteúdo: 3 bullets — agravamento estatístico; expansão recente do marco legal (2025-2026); lacunas técnicas documentadas na literatura internacional.
Nota de fala: Conectar os três pilares que justificam o trabalho, cada um detalhado nos slides seguintes.

SLIDE 5 — Problema de pesquisa
Conteúdo: Enunciado único do problema de pesquisa (slide de texto centralizado, frase única).
Nota de fala: Ler o problema de pesquisa pausadamente — é o eixo de toda a apresentação.

SLIDE 6 — Objetivos
Conteúdo: Objetivo geral + 3 objetivos específicos (a, b, c), em bullets.
Nota de fala: Apresentar os objetivos como o "contrato" que será cumprido ao longo da apresentação — referenciar que cada um será retomado no final.

SLIDE 7 — O marco legal em expansão
Conteúdo: Linha do tempo simples: Lei 11.340/2006 → Lei 14.022/2020 → Leis 15.125/2025, 15.383/2026, 15.384/2026.
Nota de fala: Mostrar que três leis relevantes foram sancionadas em menos de 24 meses — o tema não é especulativo, é regulatoriamente atual.

SLIDE 8 — Soluções existentes (Brasil)
Conteúdo: PenhaS e Botão do Pânico estadual — 1 diferencial + 1 gap de cada, em tabela simples.
Nota de fala: Apresentar com respeito o que cada solução já faz bem antes de apontar a lacuna.

SLIDE 9 — Soluções existentes (internacional)
Conteúdo: Circle of 6 e bSafe — 1 diferencial + 1 gap de cada.
Nota de fala: Mesma lógica do slide anterior, agora para o cenário internacional.

SLIDE 10 — A lacuna identificada
Conteúdo: Diagrama simples — "Antes da denúncia formal" vs. "Depois da denúncia formal", com o Amparo posicionado no meio, entre apoio inicial e acionamento estatal.
Nota de fala: Este é o slide-chave da tese central do TCC — fixar visualmente onde o Amparo se posiciona frente às soluções existentes.

SLIDE 11 — Lacunas técnicas documentadas na literatura
Conteúdo: 3 bullets — acionamento manual exclusivo; armazenamento local vulnerável; ausência de IA e modo offline (Sumra et al., 2023).
Nota de fala: Enfatizar que essas lacunas vêm de revisão sistemática com 136 apps analisados — evidência científica, não intuição.

SLIDE 12 — Metodologia
Conteúdo: 3 bullets — pesquisa documental/bibliográfica; fontes oficiais e acadêmicas; cruzamento de dados-chave entre fontes independentes.
Nota de fala: Explicar brevemente como o research brief foi construído e por que o recorte temporal foi "dados mais recentes" em vez de período fixo.

SLIDE 13 — O Amparo: visão geral
Conteúdo: 4 funcionalidades centrais em bullets — emergência, documentação segura, rede de apoio, acesso a profissionais.
Nota de fala: Apresentar o produto de forma direta antes de conectar cada funcionalidade à lacuna que ela resolve.

SLIDE 14 — Funcionalidade × lacuna (documentação e armazenamento)
Conteúdo: Lacuna (armazenamento local vulnerável) → resposta do Amparo (documentação segura).
Nota de fala: Mostrar a correspondência direta entre lacuna documentada e escolha de design.

SLIDE 15 — Funcionalidade × lacuna (rede de apoio pré-denúncia)
Conteúdo: Lacuna (soluções existentes exigem denúncia/MPU prévia) → resposta do Amparo (rede de apoio ativável antes da denúncia formal).
Nota de fala: Reforçar o posicionamento já estabelecido no slide 10.

SLIDE 16 — Aderência ao marco legal
Conteúdo: Conexão direta entre Leis 15.125/2025 e 15.383/2026 e as funcionalidades de emergência/alerta do Amparo.
Nota de fala: Fechar o argumento de que o Amparo não é especulativo, mas alinhado a uma tendência regulatória ativa.

SLIDE 17 — Limitações do estudo
Conteúdo: 5 bullets — ausência de validação com usuárias reais; detecção automática de risco e modo offline ainda não implementados (trabalho futuro); pesquisa de usuária formal sobre representatividade racial ainda não realizada; sem plano formal de manutenção pós-TCC (protótipo acadêmico); ausência de percentual nacional consolidado de subnotificação.
Nota de fala: Apresentar as limitações com confiança, como agenda de pesquisa futura — antecipa e neutraliza perguntas da banca sobre o tema, mostrando que cada lacuna já foi identificada e endereçada com transparência, não escondida.

SLIDE 18 — Contribuição e trabalhos futuros
Conteúdo: Síntese da contribuição original (combinação integrada de documentação, rede de apoio e emergência, ancorada no marco legal 2025-2026) + 2 sugestões de continuidade (validação com usuárias, revisão sistemática nacional).
Nota de fala: Recuperar explicitamente a promessa feita no slide 6 (objetivos) e mostrar que cada objetivo específico foi cumprido.

SLIDE 19 — Encerramento
Conteúdo: Agradecimentos + abertura para perguntas.
Nota de fala: Transição direta para a arguição, sem prolongar.
