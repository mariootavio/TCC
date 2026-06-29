BACKLOG DE IDEIAS — BRAINSTORM AMPARO
Foco desta rodada: Interface disfarçada/camuflada ("modo app fantasma") — implementação e extensão do RF-CORE-02 (já decidido como conhecimento interno). Esta rodada NÃO propõe "criar" o modo disfarçado — apenas como implementá-lo: tipos de disfarce, mecanismos de gatilho/destrave e hardening contra os riscos documentados na literatura de vault/stalkerware apps.
Baseado no brief de conhecimento de Sofia Sabedoria (2026-06-29)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. BIBLIOTECA DE DISFARCES TOTALMENTE FUNCIONAIS
   Descrição: em vez de uma tela estática que só finge ser outro app, oferecer 4-6 disfarces (calculadora, bloco de notas, previsão do tempo, outros) que funcionam de verdade — a calculadora faz contas reais, o bloco de notas salva notas reais — para que uma inspeção rápida pelo agressor não revele inconsistência.
   Dor/gap que resolve: Gap 9 do brief (NNEDV/Safety Net Project: "qualquer pessoa que abra o app vai perceber imediatamente que ele não é o que finge ser, caso o destrave não seja convincente").
   MoSCoW: Must have
   Kano: Básica
   Diferenciação: nenhum app de violência doméstica revisado (incluindo Aspire News App) documenta publicamente se o disfarce é funcionalmente completo ou apenas uma fachada visual — Amparo se diferencia ao tratar isso como requisito, não detalhe estético.
   Nota de viabilidade: no iOS, troca de ícone para uma imagem livremente definida pela usuária tem restrições de plataforma (ver item correspondente em WON'T HAVE) — a biblioteca de disfarces precisa ser um conjunto pré-definido de opções, não upload livre de ícone.

2. DESTRAVE POR CÓDIGO NUMÉRICO DISFARÇADO DE OPERAÇÃO MATEMÁTICA
   Descrição: no disfarce de calculadora, a usuária digita uma sequência numérica definida por ela (ex.: "1207=") como se estivesse fazendo uma conta comum; ao reconhecer o código, o app abre a interface real do Amparo em vez de mostrar o resultado.
   Dor/gap que resolve: Gap 11 do brief (ausência de padrão testado/comparado de gatilho/destrave) — usa a calculadora real como disfarce do próprio mecanismo de destrave, não apenas da tela.
   MoSCoW: Must have
   Kano: Encantadora (delighter)
   Diferenciação: o Aspire News App usa 3 toques numa barra; nenhuma fonte consultada documenta destrave por sequência matemática disfarçada de operação — mecanismo não testado na literatura, espaço de ideação real do Gap 11.

3. DESTRAVE POR PALAVRA-CHAVE EM NOTA OU CAMPO DE BUSCA
   Descrição: no disfarce de bloco de notas (ou em um campo de busca/título de nota), digitar uma palavra-chave escolhida pela usuária destrava a interface real — a "nota" com a palavra-chave permanece indistinguível de qualquer outra nota até ser digitada.
   Dor/gap que resolve: Gap 11 do brief.
   MoSCoW: Should have
   Kano: Performance
   Diferenciação: nenhuma fonte consultada (Aspire News App, NNEDV/Safety Net Project, calculator vault apps) documenta esse mecanismo para disfarce de bloco de notas — alternativa não coberta pela literatura.

4. GESTO DE DESTRAVE COMO ALTERNATIVA SEM DIGITAÇÃO
   Descrição: gesto específico configurável (ex.: deslizar em um padrão simples sobre a tela do disfarce, ou pressão longa em um ponto específico do ícone falso) como via alternativa de destrave, mais rápida que digitar PIN/palavra-chave em situação de pânico.
   Dor/gap que resolve: Gap 11 do brief + tom de voz do company.md (usabilidade sob estresse, evitar mecanismos que a usuária possa esquecer em pânico).
   MoSCoW: Could have
   Kano: Performance
   Diferenciação: nenhuma fonte consultada compara gestos a PIN/palavra-chave para este caso de uso — Amparo testaria essa hipótese de design sem "melhor prática" estabelecida a contrariar.

5. FALHA SILENCIOSA NO DESTRAVE (SEM MENSAGEM DE ERRO VISÍVEL)
   Descrição: ao digitar um código/palavra-chave errado, o disfarce permanece neutro — sem "senha incorreta", sem vibração diferenciada, sem qualquer sinal de que existe algo a ser destravado. O disfarce simplesmente continua funcionando como o app que finge ser.
   Dor/gap que resolve: Gap 9 do brief (vestígios técnicos que denunciam a existência do disfarce).
   MoSCoW: Must have
   Kano: Básica
   Diferenciação: nenhum app revisado (incluindo os de benchmarking de vault apps) documenta tratamento explícito de feedback de erro como vetor de vazamento do disfarce.

6. NOTIFICAÇÕES SEMPRE DISFARÇADAS, NUNCA COM CONTEÚDO REAL
   Descrição: toda notificação do Amparo (confirmação de guardião, alerta) é exibida com texto genérico vinculado ao disfarce ativo (ex.: "Nota salva" se o disfarce for bloco de notas) — o conteúdo real nunca aparece na tela de bloqueio nem na central de notificações, independentemente da configuração de privacidade do sistema.
   Dor/gap que resolve: Gap 9 do brief (achado EFF, 2026: notificações push expõem conteúdo sensível na tela de bloqueio e "rompem completamente a eficácia de um disfarce de ícone/tela").
   MoSCoW: Must have
   Kano: Básica
   Diferenciação: nenhuma fonte consultada sobre apps de violência doméstica trata esse vetor publicamente — é o gap mais crítico e mais diretamente acionável identificado por Sofia.

7. LIMPEZA DO SNAPSHOT NA LISTA DE APPS RECENTES/MULTITAREFA
   Descrição: ao a usuária saltar para fora da interface real (botão home, troca de app), o Amparo força a substituição do thumbnail exibido na tela de apps recentes pela imagem do disfarce — nunca deixando visível uma captura da tela real do Amparo nessa lista.
   Dor/gap que resolve: Gap 9 do brief (Ruffin et al., WPES 2022: maioria dos vault apps comerciais não trata vestígios de multitarefa).
   MoSCoW: Must have
   Kano: Performance
   Diferenciação: o mesmo estudo mostra que a maioria das implementações de mercado falha nesse ponto — Amparo se diferencia tratando isso como requisito obrigatório de lançamento, não melhoria futura.

8. CRIPTOGRAFIA REAL DOS DADOS, INDEPENDENTE DO DISFARCE VISUAL
   Descrição: todos os dados sensíveis do Amparo ficam criptografados no armazenamento do dispositivo desde a primeira gravação — a proteção não depende do disfarce de UI estar ativo; extração direta do armazenamento do app (ex.: por ferramenta forense) não expõe conteúdo legível sem a chave/destrave da usuária.
   Dor/gap que resolve: Gap 9 do brief (achado central de Ruffin et al., WPES 2022: a maioria dos vault apps analisados não criptografa de fato os dados por trás do disfarce de UI).
   MoSCoW: Must have
   Kano: Básica
   Diferenciação: o estudo mostra que essa é justamente a falha mais comum do mercado de vault apps — Amparo se diferencia ao não repetir o erro documentado cientificamente.

9. NOME E FICHA DA LOJA DE APPS DESVINCULADOS DA MARCA "AMPARO"
   Descrição: o app é publicado na loja sob um nome neutro coerente com algum disfarce (ex.: associado a "notas" ou "utilidades"), sem menção a "Amparo" ou a violência doméstica na ficha pública da loja, reduzindo o risco de que uma busca pelo nome real do app na loja exponha a usuária.
   Dor/gap que resolve: Gap 9 do brief (NNEDV/Safety Net Project: "o nome real do app pode aparecer na busca da loja mesmo que o ícone seja outro").
   MoSCoW: Should have
   Kano: Performance
   Diferenciação: nenhum app de benchmarking trata isso publicamente como estratégia deliberada de publicação — é decisão de distribuição, não apenas de UI.
   Nota de risco: a mesma fonte (NNEDV/Safety Net Project) documenta que a Apple App Store pode exigir que a descrição pública revele a função real do app, o que limitaria essa ideia na App Store iOS — avaliação de política de loja é pré-requisito antes de implementação (ver também WON'T HAVE).

10. ORIENTAÇÃO NO ONBOARDING PARA REDUZIR RISCO DE RECONHECIMENTO DO PADRÃO
   Descrição: durante a configuração inicial do modo disfarçado (não na tela do disfarce em si), o Amparo orienta a usuária a escolher um disfarce coerente com seu padrão real de uso do celular (ex.: evitar instalar uma segunda calculadora se já existe uma nativa) e oferece um lembrete periódico discreto para reavaliar se o disfarce escolhido ainda faz sentido.
   Dor/gap que resolve: Gap 10 do brief (risco de reconhecimento do padrão de disfarce por agressor já familiarizado com apps dual-use/stalkerware, conforme Freed et al., CHI 2018).
   MoSCoW: Should have
   Kano: Performance
   Diferenciação: nenhuma fonte consultada propõe mitigação para esse risco específico de reconhecimento cruzado — ideação original a partir do gap identificado por Sofia, sem prática de mercado a copiar.

11. SUGESTÃO ADAPTATIVA DE DISFARCE COM BASE NO USO REAL DO APARELHO
   Descrição: o Amparo sugere periodicamente um disfarce diferente do atual caso identifique que ele duplica um app já existente no aparelho da usuária (ex.: evitar "duas calculadoras" na tela inicial), priorizando opções que se misturem melhor ao padrão real de apps instalados.
   Dor/gap que resolve: Gap 10 do brief.
   MoSCoW: Could have
   Kano: Encantadora (delighter)
   Diferenciação: nenhuma fonte de benchmarking ou da literatura de vault/stalkerware apps propõe personalização adaptativa de disfarce — diferencial genuíno frente ao mercado.
   Nota de risco: implementação depende de ler a lista de apps instalados no aparelho, o que exige avaliação cuidadosa de permissões e de comunicação transparente com a usuária sobre esse acesso, para não introduzir um novo vetor de desconfiança ou de risco de privacidade.

12. SAÍDA DE EMERGÊNCIA PARA O DISFARCE, GENERALIZADA PARA QUALQUER DISFARCE ESCOLHIDO
   Descrição: dentro da interface real do Amparo, um gesto ou tecla física (ex.: botão de volume) devolve a usuária instantaneamente ao disfarce ativo, qualquer que seja o disfarce escolhido — não apenas para um disfarce fixo.
   Dor/gap que resolve: Gap 11 do brief, generalizando o mecanismo do Aspire News App (botão "X" que leva a uma tela aleatória do disfarce único) para uma biblioteca de múltiplos disfarces configuráveis.
   MoSCoW: Must have
   Kano: Básica
   Diferenciação: o Aspire News App documenta esse recurso apenas para seu disfarce único e fixo; nenhuma fonte consultada trata desse mecanismo como configurável por biblioteca de disfarces.

WON'T HAVE (ESCOPO EXCLUÍDO NESTA RODADA)

- Upload livre de ícone personalizado pela usuária (qualquer imagem) em vez de biblioteca pré-definida de disfarces: no iOS, a plataforma restringe a troca dinâmica de ícone a um conjunto de ícones alternativos definidos previamente no app — não há suporte nativo a ícone arbitrário definido pelo usuário em tempo real. Manter como item de biblioteca fixa (ideia 1), não como personalização irrestrita.
- Detecção automática de spyware/stalkerware instalado no aparelho da própria usuária (scanner anti-vigilância): tema relacionado à literatura trazida por Sofia (Gap 10), mas é uma funcionalidade distinta do RF-CORE-02 (proteger o próprio Amparo via disfarce, não detectar vigilância de terceiros no aparelho) — fora do recorte desta rodada, registrado como direção possível para rodada futura.
- "PIN de coação" com conteúdo-isca adicional para resistir a análise forense profissional (ex.: dados falsos que aparecem sob um PIN secundário, simulando cooperação): exige modelo de ameaça mais avançado (perícia forense institucional) que extrapola o escopo de um TCC; mantido como direção conceitual para trabalho futuro, sem aprofundamento de implementação nesta rodada.
- Publicação do app com nome 100% desvinculado de "Amparo" inclusive na Apple App Store sem qualquer menção à função real: a própria fonte que fundamenta a ideia 9 (NNEDV/Safety Net Project) documenta que a política da Apple pode exigir descrição que revele a função real — tratar esse ponto como pesquisa de viabilidade de política de loja a ser validada antes de qualquer implementação, não como entrega garantida desta rodada.
