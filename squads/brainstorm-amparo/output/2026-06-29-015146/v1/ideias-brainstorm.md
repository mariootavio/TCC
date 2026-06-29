BACKLOG DE IDEIAS — BRAINSTORM AMPARO
Foco desta rodada: Expansão informal da biblioteca de disfarces (extensão da Rodada 2 / RF-CORE-02) — novas opções de apps-disfarce neutros, cada uma com mecanismo de destrave coerente com o uso normal daquele tipo de app. Gerado sem novo brief de Sofia; ancorado nos Gaps 9, 10 e 11 já documentados na Rodada 2 (2026-06-28).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. CONVERSOR DE MOEDAS/UNIDADES
   Descrição: app funcional de conversão real. Destrave: converter um valor numérico específico (ex.: "1207") em vez de obter o resultado normal.
   Dor/gap que resolve: Gap 11 (ausência de padrão testado de gatilho).
   MoSCoW: Could have
   Kano: Encantadora
   Diferenciação: estende o padrão "número como código" já validado na calculadora (Rodada 2, ideia 2) para uma segunda utilidade, ampliando a biblioteca sem criar superfície de risco técnico nova.

2. LISTA DE TAREFAS (TO-DO)
   Descrição: app funcional de tarefas reais. Destrave: criar uma tarefa com um título-chave específico.
   Dor/gap que resolve: Gap 11 + Gap 10 (variedade de disfarces que não dupliquem apps já existentes no aparelho).
   MoSCoW: Could have
   Kano: Performance
   Diferenciação: mesma família de gatilho do bloco de notas (palavra-chave), mas visualmente/categoricamente distinto — ajuda quem já tem um app de notas real e não quer duplicar ícone (Gap 10).

3. LISTA DE COMPRAS/MERCADO
   Descrição: app funcional de lista de compras. Destrave: adicionar um item com nome-chave específico.
   Dor/gap que resolve: Gap 10.
   MoSCoW: Could have
   Kano: Encantadora
   Diferenciação: terceira opção na família "palavra-chave em campo de texto" — categoria de app ainda mais neutra e comum que lista de tarefas.

4. DESPERTADOR/ALARME
   Descrição: app funcional com alarmes reais. Destrave: configurar um alarme para um horário específico (ex.: 03:33) em vez de salvar o alarme normalmente.
   Dor/gap que resolve: Gap 11.
   MoSCoW: Could have
   Kano: Encantadora
   Diferenciação: nenhuma fonte de benchmarking ou literatura de vault apps documenta horário-como-código — espaço de ideação não testado, como o código matemático foi para a calculadora.

5. RÁDIO/SINTONIZADOR DE ESTAÇÕES
   Descrição: app funcional de rádio (streaming real). Destrave: digitar uma "frequência" específica (ex.: 98.7) em vez de sintonizar a estação.
   Dor/gap que resolve: Gap 11.
   MoSCoW: Could have
   Kano: Encantadora
   Diferenciação: mesmo padrão "número como código", em categoria de app rara nas listas de vault apps revisadas.

6. PREVISÃO DO TEMPO (CLIMA)
   Descrição: app funcional de clima real. Destrave: buscar por uma cidade com nome customizado/inventado (ex.: "Vila Esperança") em vez de mostrar "cidade não encontrada".
   Dor/gap que resolve: Gap 11.
   MoSCoW: Should have
   Kano: Performance
   Diferenciação: este disfarce já era citado na Rodada 2 (ideia 1, biblioteca de disfarces) como exemplo, mas sem gatilho definido — esta é a proposta concreta de destrave para ele.

7. CALENDÁRIO/AGENDA
   Descrição: app funcional de eventos reais. Destrave: criar um evento com um título-chave específico em uma data específica.
   Dor/gap que resolve: Gap 11.
   MoSCoW: Should have
   Kano: Performance
   Diferenciação: mesma família de gatilho do bloco de notas (palavra-chave), em categoria de app ainda mais comum e neutra.

8. CONTATOS (AGENDA TELEFÔNICA)
   Descrição: usa a própria agenda de contatos do disfarce. Destrave: criar um contato com um nome-chave específico (ex.: "Manutenção Ar Condicionado").
   Dor/gap que resolve: Gap 11.
   MoSCoW: Could have
   Kano: Encantadora
   Diferenciação: nenhuma fonte de benchmarking documenta agenda de contatos como vetor de destrave — espaço de ideação genuinamente não testado.

9. TRADUTOR
   Descrição: app funcional de tradução real. Destrave: traduzir uma frase/palavra-chave específica em vez de mostrar a tradução normal.
   Dor/gap que resolve: Gap 11.
   MoSCoW: Could have
   Kano: Encantadora
   Diferenciação: padrão de texto-livre como gatilho (igual ao bloco de notas), em app de categoria distinta — útil para quem já tem um app de notas real e não quer duplicar ícone (Gap 10).

10. MAPAS/NAVEGAÇÃO
    Descrição: busca de endereço real. Destrave: buscar um endereço com nome de local específico (ex.: "Praça das Flores, 1207").
    Dor/gap que resolve: Gap 11.
    MoSCoW: Could have
    Kano: Encantadora
    Diferenciação: extensão do padrão "campo de busca como gatilho" (Gap 11) para uma categoria de app de navegação real.
    Nota de risco (registrada por Bruno): o histórico de buscas recentes do app de mapas pode reter o endereço-código mesmo após o uso — exige o mesmo tratamento de "limpeza de rastro" já previsto na Rodada 2 (ideia 7, limpeza de snapshot), estendido aqui para histórico de busca.

11. CRONÔMETRO/TIMER
    Descrição: app funcional de cronômetro/timer. Destrave: configurar uma duração específica (ex.: 7 min 43 s) em vez de iniciar a contagem normal.
    Dor/gap que resolve: Gap 11.
    MoSCoW: Could have
    Kano: Encantadora
    Diferenciação: extensão do padrão "número como código" (calculadora/conversor/despertador) para mais uma categoria comum.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

WON'T HAVE (ESCOPO EXCLUÍDO NESTA RODADA)

- Navegador/browser com URL falsa como gatilho: descartado porque o histórico de navegação é mais difícil de limpar seletivamente sem deixar vestígio do que um campo de busca isolado dentro de um app — exigiria hardening desproporcional ao ganho.
- App de álbum/galeria protegida por senha: já descartado na Rodada 2 — um álbum com proteção por senha é, por si só, um padrão reconhecível por um agressor familiarizado com vault apps (Gap 10), contrariando o objetivo de neutralidade do disfarce.
- Gravador de áudio/notas de voz: já descartado na Rodada 2 — deixaria arquivos de áudio reais como vestígio que exigiria tratamento extra de limpeza (Gap 9).
