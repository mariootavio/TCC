# Quality Criteria — Brainstorm Amparo

Critérios de qualidade consolidados dos 3 agentes da squad. Cada agente tem sua
própria seção; o checklist DFV de Carla é compartilhado por referência com
`domain-framework.md`.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Sofia Sabedoria — Brief de Conhecimento

- [ ] Toda funcionalidade de benchmarking listada tem ao menos um gap/limitação registrado junto — nunca apenas o ponto forte.
- [ ] O conhecimento interno do projeto (funcionalidades já existentes/planejadas, tom de voz, dados já levantados pela squad tcc-documentacao) está presente e atualizado antes de qualquer recomendação externa.
- [ ] A seção de Gaps de Mercado existe e tem no mínimo 2 oportunidades concretas e específicas.
- [ ] Nenhum dado já levantado pela squad tcc-documentacao é repetido com fonte diferente sem necessidade — reutilizar a fonte original.
- [ ] Toda afirmação externa (benchmarking, literatura) tem fonte rastreável e nível de confiança (alta/média/baixa) explícito.
- [ ] O brief separa claramente conhecimento interno de externo em seções distintas.
- [ ] A recomendação final para o brainstorm está presente e aponta explicitamente quais gaps merecem prioridade de exploração.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Bruno Brainstorm — Backlog de Ideias

- [ ] Toda ideia do backlog cita explicitamente a dor/gap do brief de Sofia que a originou — nenhuma ideia "solta" sem ancoragem.
- [ ] Toda ideia tem classificação MoSCoW e Kano preenchidas (ver `domain-framework.md`).
- [ ] Nenhuma ideia duplica uma funcionalidade de benchmarking sem nota de diferenciação explícita.
- [ ] Existe uma seção "Won't have" com ao menos uma exclusão de escopo registrada e justificada.
- [ ] Geração e avaliação não foram misturadas — nenhuma ideia foi descartada ou pré-julgada durante a geração (isso é responsabilidade exclusiva de Carla).
- [ ] Nenhuma prioridade RICE foi atribuída pelo próprio Bruno — essa etapa é exclusiva de Carla Critério.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Carla Critério — Avaliação e Priorização

- [ ] Toda ideia tem os 7 critérios do checklist DFV avaliados, com os 2 bloqueantes (alinhamento à missão, risco de segurança) explicitamente marcados OK/FALHA.
- [ ] Nenhuma ideia que falhe em um critério bloqueante aparece no ranking RICE.
- [ ] RICE foi aplicado apenas às ideias já aprovadas pelo filtro DFV (nunca antes do filtro).
- [ ] O veredito geral (APROVAR/REJEITAR/APROVAÇÃO CONDICIONAL) é consistente com a proporção de ideias aprovadas vs. rejeitadas.
- [ ] Existe ao menos um "Ponto forte" registrado mesmo quando o veredito geral é REJEITAR.
- [ ] Toda justificativa de nota/veredito é específica — nunca uma nota sem explicação.
- [ ] Quando o veredito é REJEITAR ou APROVAÇÃO CONDICIONAL, há uma lista de mudanças obrigatórias específicas por ideia.
- [ ] O número da rodada de revisão atual está registrado no cabeçalho do veredito (ex.: "Revisão 1 de 3").

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Critério de Aprovação Geral do Backlog (regra de decisão de Carla)

- Aprovar ideias individuais com pelo menos **5 dos 7 critérios DFV positivos**.
- Critérios 1 (alinhamento à missão) e 4 (risco de segurança) são **bloqueantes**: falha em qualquer um deles rejeita a ideia automaticamente, independente da pontuação total.
- Se o backlog inteiro tiver **menos de 5 dos 7 critérios médios atendidos** entre as ideias avaliadas, o veredito geral é **REJEITAR**, mesmo que ideias individuais isoladas sejam fortes — sinaliza problema sistêmico de geração, não de uma ideia isolada.
