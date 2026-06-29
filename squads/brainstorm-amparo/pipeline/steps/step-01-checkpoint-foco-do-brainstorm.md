---
type: checkpoint
outputFile: squads/brainstorm-amparo/output/foco-brainstorm.md
---

# Step 1: Checkpoint — Foco do Brainstorm

Este é o primeiro checkpoint do pipeline da squad Brainstorm — Amparo. Antes de
iniciar qualquer pesquisa, explique brevemente o contexto da squad ao usuário:
esta é uma squad de brainstorm que combina especialização no tema de violência
doméstica contra mulheres com sabedoria total sobre o estado atual do projeto
Amparo ("Você não está sozinha"), para gerar e priorizar ideias de novas
funcionalidades e fluxos.

Em seguida, pergunte ao usuário qual é o foco desta rodada de brainstorm.

Perguntas sugeridas:

1. **Qual o foco deste brainstorm hoje?** (texto livre — exemplos: "novas
   funcionalidades de segurança/emergência", "fluxos de onboarding e uso
   diário", "rede de apoio e comunidade", ou "brainstorm geral" sem recorte
   específico).
2. **Qual o recorte do benchmarking externo que Sofia Sabedoria deve
   pesquisar?**
   1. Apps brasileiros de referência
   2. Apps internacionais
   3. Ambos
   4. Pular benchmarking externo e focar só no que a squad tcc-documentacao já
      levantou

A resposta do usuário é salva em
`squads/brainstorm-amparo/output/foco-brainstorm.md` e usada como `inputFile`
pelo Step 2 (Sofia Sabedoria).

Se o usuário não tiver preferência, sugira o padrão: brainstorm geral sobre
novas funcionalidades e fluxos, com recorte de benchmarking "Ambos" (apps
brasileiros e internacionais).
