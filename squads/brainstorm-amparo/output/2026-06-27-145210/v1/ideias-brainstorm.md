BACKLOG DE IDEIAS — BRAINSTORM AMPARO
Foco desta rodada: Brainstorm geral — sem recorte específico, novas funcionalidades e fluxos em geral.
Baseado no brief de conhecimento de Sofia Sabedoria (2026-06-27)

Nota de escopo: os 5 requisitos centrais (RF-CORE-01 a RF-CORE-05) já são conhecimento interno consolidado pelo product owner e NÃO aparecem como ideias novas neste backlog. Todas as ideias abaixo complementam uma RF-CORE específica (quando aplicável) ou atacam um gap de mercado que nenhuma RF-CORE cobre.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. VERIFICAÇÃO DE BEM-ESTAR PERIÓDICA (CHECK-IN ATIVO)
   Descrição: em situações de risco elevado (definidas pela própria usuária), o app pergunta periodicamente "Tudo bem?" com uma janela curta de resposta; se não houver resposta, escala automaticamente um alerta discreto para a rede de guardiões, sem exigir que a usuária acione o botão de emergência.
   Dor/gap que resolve: Gap 1 (dependência de acionamento manual) — complementa o RF-CORE-01, que cobre o acionamento manual, mas não resolve a ausência de alerta proativo quando a usuária está impossibilitada de agir.
   MoSCoW: Should have
   Kano: Performance
   Diferenciação: nenhum app revisado (PenhaS, SP Mulher, Juntas, bSafe, Circle of 6) tem escalonamento automático por ausência de resposta — não é commodity de mercado.

2. DETECÇÃO DE PADRÃO DE RISCO EM SEGUNDO PLANO
   Descrição: monitoramento opcional, com consentimento explícito, de sinais indiretos no próprio celular (ex.: queda abrupta da localização compartilhada, desligamento incomum do app) que sugere à usuária, de forma discreta, revisar seu plano de segurança — sem acionar terceiros automaticamente.
   Dor/gap que resolve: Gap 1 (ausência de alerta automático/proativo) — complementa o RF-CORE-01 num cenário diferente do item 1 (sinal indireto, não ausência de resposta a um check-in).
   MoSCoW: Could have
   Kano: Encantadora (delighter)
   Diferenciação: nenhum dos 9 apps de benchmarking usa sinais comportamentais para sugerir ação preventiva.

3. BACKUP CRIPTOGRAFADO AUTOMÁTICO EM NUVEM PARA EVIDÊNCIAS
   Descrição: as evidências registradas via RF-CORE-04 (texto, foto, áudio, vídeo) são automaticamente replicadas, ainda criptografadas, para armazenamento remoto, com remoção opcional da cópia local mais antiga após confirmação de sincronização — para que a apreensão física do celular pelo agressor não elimine a prova.
   Dor/gap que resolve: Gap 2 (vulnerabilidade de armazenamento local de provas) — fecha integralmente o gap que o RF-CORE-04, por si só, deixa parcialmente aberto.
   MoSCoW: Must have
   Kano: Básica (esperada uma vez que a funcionalidade de registro de provas já existe)
   Diferenciação: nenhum app revisado documenta backup remoto criptografado nativo — PenhaS e Juntas registram evidências mas sem essa garantia explícita.

4. INDICADOR DE INTEGRIDADE DA PROVA (HASH + SELO DE TEMPO)
   Descrição: cada evidência registrada recebe um hash criptográfico e um selo de tempo (timestamp) verificável, exibido à usuária e exportável junto com a prova, permitindo demonstrar que o arquivo não foi alterado desde o registro.
   Dor/gap que resolve: Gap 2 (vulnerabilidade de provas) — reforça o RF-CORE-04 com cadeia de custódia técnica, relevante diante da Lei 15.380/2026 (formalização da manifestação da vítima).
   MoSCoW: Should have
   Kano: Performance
   Diferenciação: nenhum app de benchmarking menciona mecanismo de verificação de integridade da prova.

5. ENCAMINHAMENTO INSTITUCIONAL AUTOMÁTICO PÓS-CONFIRMAÇÃO DOS GUARDIÕES
   Descrição: quando um guardião confirma uma emergência real via RF-CORE-05, o app oferece um encaminhamento de um toque para o canal institucional mais próximo (Delegacia da Mulher, Ligue 180, CRAS), com os dados básicos da ocorrência pré-preenchidos.
   Dor/gap que resolve: Gap 7 (fragmentação entre rede pessoal e institucional) — complementa o RF-CORE-05, que cobre só o lado pessoal da rede de apoio.
   MoSCoW: Should have
   Kano: Performance
   Diferenciação: SP Mulher Segura unifica BO virtual e rede de apoio, mas só em SP e via integração estadual; esta ideia é nacional e não depende de integração institucional para funcionar (o encaminhamento é um link/contato direto, não uma integração de sistemas).

6. PERFIS DE DEPENDENTES NA REDE DE APOIO
   Descrição: a usuária pode cadastrar dependentes (filhos, familiares sob sua guarda) como perfis protegidos dentro da rede de guardiões, recebendo orientações e alertas específicos sobre a segurança deles em caso de emergência.
   Dor/gap que resolve: Gap 7 (rede de apoio não cobre extensão a dependentes) — complementa o RF-CORE-05, alinhado à Lei 15.384/2026 (violência vicária).
   MoSCoW: Should have
   Kano: Encantadora (delighter)
   Diferenciação: nenhum app revisado trata explicitamente de dependentes como parte da rede de apoio — gap de mercado direto.

7. MODO OFFLINE COMPLETO COM SINCRONIZAÇÃO POSTERIOR
   Descrição: as funcionalidades centrais (plano de segurança, lista de guardiões, registro de evidências, rota de fuga) continuam acessíveis sem conexão à internet; dados pendentes são sincronizados de forma criptografada quando a conectividade retorna.
   Dor/gap que resolve: Gap 3 (ausência de modo offline) — gap prioritário desta rodada, não coberto por nenhuma RF-CORE.
   MoSCoW: Must have
   Kano: Encantadora (delighter)
   Diferenciação: apenas 15% dos 178 apps revisados (JMIR 2025) oferecem funcionalidade offline — nenhum dos apps de benchmarking diretos (PenhaS, bSafe, Circle of 6, Juntas) documenta suporte offline completo.

8. SOS SEM CONEXÃO DE DADOS, COM ACIONAMENTO SEM RASTRO VISÍVEL (Revisão 2)
   Descrição: se não houver internet disponível, o acionamento de emergência cai automaticamente para um canal alternativo que não depende de dados móveis ou Wi-Fi, em duas camadas: (1) por padrão, o app envia o alerta via SMS programático e o remove imediatamente da conversa nativa de mensagens do celular assim que a operadora confirma a entrega, não deixando histórico visível no app de SMS padrão; (2) em aparelhos/operadoras onde a remoção do SMS não for tecnicamente possível (restrição do sistema operacional), o app usa como alternativa um canal de dados mínimo (USSD ou pacote de dados de baixíssimo consumo) que não grava nenhuma mensagem na interface padrão do telefone.
   Dor/gap que resolve: Gap 3 (80% dos apps revisados dependem de GPS/dados móveis) — ataca diretamente a falha estrutural de conectividade documentada por Sofia, agora sem o risco de exposição identificado por Carla Critério na Revisão 1 (rastro visível no app de mensagens nativo).
   MoSCoW: Must have
   Kano: Básica (segurança mínima esperada em contexto de baixa conectividade no Brasil)
   Diferenciação: nenhum app de benchmarking documenta fallback sem conexão de dados, e nenhum documenta remoção automática de rastro de envio — diferencial de segurança direto sobre a versão original da ideia.

9. ASSISTENTE CONVERSACIONAL DE TRIAGEM DE RISCO (IA LEVE, ON-DEVICE)
   Descrição: um assistente conversacional simples, executado localmente no aparelho (sem depender de internet para a inferência básica), guia a usuária por perguntas para ajudá-la a reconhecer sinais de risco crescente e sugerir o próximo passo adequado.
   Dor/gap que resolve: Gap 3 (ausência de IA) — nenhum dos 136-178 apps revisados na literatura usa IA para apoiar a usuária.
   MoSCoW: Could have
   Kano: Encantadora (delighter)
   Diferenciação: nenhum app de benchmarking usa IA conversacional; é gap de mercado documentado tanto por Sumra et al. (2023) quanto pelo JMIR (2025).

10. AVALIAÇÃO DE RISCO ESTRUTURADA ADAPTADA AO BRASIL (DECISION AID NACIONAL)
    Descrição: questionário estruturado e não julgador, inspirado no modelo de Danger Assessment usado pelo myPlan, mas adaptado ao marco legal brasileiro (Lei Maria da Penha e leis recentes) e ao perfil demográfico real das vítimas no país, que recomenda próximos passos concretos (ex.: ativar botão de emergência, buscar MPU, contatar Ligue 180).
    Dor/gap que resolve: Gap 8 (ausência de decision aid validado no Brasil) — gap prioritário desta rodada, não coberto por nenhuma RF-CORE.
    MoSCoW: Must have
    Kano: Encantadora (delighter)
    Diferenciação: o único benchmark com avaliação de risco estruturada e testada cientificamente (myPlan) é americano, com adaptação a países de baixa/média renda ainda em fase de protocolo de pesquisa — não há versão validada para o Brasil.

11. BIBLIOTECA DE DIREITOS E LEGISLAÇÃO SIMPLIFICADA
    Descrição: explicador em linguagem acessível das leis aplicáveis (Lei Maria da Penha e atualizações recentes: 15.125/2025, 15.383/2026, 15.384/2026, 15.380/2026), acionado de forma contextual a partir do resultado da avaliação de risco (item 10) — por exemplo, se a monitoração eletrônica do agressor for aplicável, o app explica o que isso significa na prática para a usuária.
    Dor/gap que resolve: Gap 8 (decision aid) e conhecimento interno (tom de voz "sem jargão técnico") — torna a base legal já levantada por Sofia acionável para a usuária final, não apenas argumento de TCC.
    MoSCoW: Should have
    Kano: Básica
    Diferenciação: nenhum app de benchmarking expõe a legislação de forma simplificada e contextual à situação da usuária.

12. PESQUISA DE ACOMPANHAMENTO PÓS-USO (FOLLOW-UP ESTRUTURADO E ANONIMIZADO)
    Descrição: após o uso de uma funcionalidade de segurança (ex.: botão de emergência, avaliação de risco), o app oferece, de forma opcional e anônima, uma pesquisa curta sobre o desfecho (ex.: "Você conseguiu ajuda?", "Sentiu-se mais segura?").
    Dor/gap que resolve: Gap 4 (falta de evidência robusta de eficácia) — nenhum app revisado (incluindo myPlan) mede desfecho de segurança real, apenas uso/percepção parcial.
    MoSCoW: Could have
    Kano: Performance
    Diferenciação: nem Sumra et al. (2023) nem Doria et al. (2021) encontraram apps com instrumentação de desfecho — esta ideia cria a base de dados que o próprio TCC pode usar como contribuição acadêmica.

13. PAINEL DE INDICADORES DE SEGURANÇA AGREGADOS
    Descrição: painel interno (não voltado à usuária final) que agrega, de forma anonimizada, os dados das pesquisas de acompanhamento (item 12) e métricas de uso, para permitir validação futura da eficácia do Amparo.
    Dor/gap que resolve: Gap 4 (falta de evidência de eficácia) — complementa o item 12, fechando o ciclo de coleta e análise.
    MoSCoW: Could have
    Kano: Performance
    Diferenciação: nenhum app revisado disponibiliza instrumentação voltada à própria validação científica.

14. CONTEÚDO DE APOIO CULTURALMENTE ADAPTADO AO PERFIL BRASILEIRO DE VÍTIMAS
    Descrição: o conteúdo de apoio psicológico/jurídico dentro do app (linguagem, exemplos, referências) é desenvolvido considerando o perfil real das vítimas no Brasil (63,6%-64% mulheres negras, agressão majoritariamente dentro de casa), em parceria com especialistas locais.
    Dor/gap que resolve: Gap 5 (sub-representação de grupos vulneráveis na pesquisa internacional) — soluções como Circle of 6 e myPlan foram validadas em amostras predominantemente brancas/universitárias.
    MoSCoW: Should have
    Kano: Performance
    Diferenciação: nenhum app de benchmarking documenta adaptação cultural/racial explícita ao contexto brasileiro.

15. RELATOS ANÔNIMOS FILTRADOS POR CONTEXTO
    Descrição: extensão do recurso de relatos anônimos (já presente no PenhaS) para permitir filtrar experiências por contexto semelhante (região, tipo de situação), ajudando a usuária a encontrar relatos mais relevantes ao seu perfil e realidade.
    Dor/gap que resolve: Gap 5 (sub-representação) — ataca o problema pelo lado da relevância do conteúdo gerado por usuárias, não apenas do conteúdo produzido pela equipe do Amparo.
    MoSCoW: Could have
    Kano: Encantadora (delighter)
    Diferenciação: PenhaS tem feed de relatos anônimos, mas sem filtro de contexto — diferenciação clara, não duplicação.

16. CONVITE DISCRETO ENTRE USUÁRIAS (INDICAÇÃO CAMUFLADA)
    Descrição: uma usuária pode compartilhar um convite de instalação do app camuflado como conteúdo neutro (ex.: dica de bem-estar), aproveitando o RF-CORE-02 (modo disfarçado) como inspiração de discrição também na divulgação, não só no uso.
    Dor/gap que resolve: Gap 6 (baixa adoção/divulgação no contexto brasileiro) — SP Mulher Segura, mesmo sendo app estatal completo, teve apenas ~5 mil downloads em 7 meses.
    MoSCoW: Could have
    Kano: Performance
    Diferenciação: nenhum app de benchmarking documenta mecanismo de indicação discreta entre usuárias.

17. ONBOARDING VIA QR CODE EM PONTOS DE ACOLHIMENTO
    Descrição: pontos físicos de acolhimento (DEAMs, CRAS, UBS, ONGs parceiras) disponibilizam um QR code para instalação e configuração inicial rápida do app, aproveitando o momento em que a mulher já está buscando ajuda.
    Dor/gap que resolve: Gap 6 (baixa adoção) — ataca a divulgação no momento de maior receptividade, diferente da indicação entre usuárias (item 16).
    MoSCoW: Could have
    Kano: Básica
    Diferenciação: PenhaS tem mapa de pontos de atendimento, mas não documenta fluxo de onboarding facilitado nesses pontos.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

WON'T HAVE (ESCOPO EXCLUÍDO NESTA RODADA)

- Integração direta com o sistema de monitoração eletrônica do agressor (tornozeleira, Leis 15.125/2025 e 15.383/2026): depende de integração judicial/institucional com o Poder Judiciário e órgãos de segurança pública estaduais, inviável para o escopo de um app de TCC — mesma lógica de viabilidade já registrada por Sofia para o "Mulher Alerta".
- IA preditiva de risco de feminicídio baseada em dados populacionais agregados (fora dos dados da própria usuária): depende de acesso a bases de dados públicas sensíveis e levanta riscos éticos de viés racial, sobreposição com policiamento preditivo — fora do escopo e da missão de proteção individual do Amparo.
- Validação jurídica nacional uniforme das evidências coletadas perante todos os tribunais do país: depende de regulamentação judicial fora do controle do produto — mesmo gap de pesquisa já registrado por Sofia sobre o PenhaS.
