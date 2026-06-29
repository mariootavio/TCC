---
type: checkpoint
---

# Step 10: Checkpoint — Aprovação Final

Apresente ao usuário o veredito completo de `revisao-final.md` (Rafael
Rigor): pontuação por critério, gatilho de rejeição automática (se houver),
correções obrigatórias, pontos fortes, e o caminho absoluto do projeto pronto
para uso.

## Instructions

1. Se o veredito for REJEITAR: explicar o gatilho de rejeição automática (se
   aplicável) ou os critérios que falharam, e informar que o pipeline volta
   ao Step 6 (Fábio Front-end) para correção. Perguntar se o usuário quer
   prosseguir com a correção automática ou intervir manualmente primeiro.
2. Se o veredito for APROVAR COM RESSALVAS: listar as correções obrigatórias
   e perguntar se o usuário quer que a squad aplique essas correções agora
   (volta ao Step 6) ou se aceita o resultado atual e fará os ajustes
   manualmente depois.
3. Se o veredito for APROVAR: parabenizar e apresentar o resumo final —
   caminho do projeto, comandos para rodar localmente, e sugestão de próximos
   passos (ex.: revisar o site no navegador, considerar deploy quando o
   usuário decidir a hospedagem).
4. Registrar o resultado final em `squads/landing-page-amparo/_memory/runs.md`
   (data, tema/foco da execução, output, resultado) e atualizar
   `_memory/memories.md` com qualquer aprendizado relevante (ex.: preferências
   de estilo confirmadas, pendências que ficaram em aberto para a próxima
   execução).

Esta é a última etapa do pipeline. Nenhuma ação adicional ocorre sem a
confirmação explícita do usuário aqui.
