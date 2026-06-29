---
task: "Pesquisar Benchmarking de Segurança"
order: 2
input: |
  - foco_brainstorm: Conteúdo de squads/brainstorm-amparo/output/foco-brainstorm.md (recorte de benchmarking externo escolhido pelo usuário)
  - dados_ja_levantados: Benchmarking já levantado pela squad tcc-documentacao (saída da task anterior)
output: |
  - apps_referencia: Lista de apps de segurança/denúncia de violência doméstica com funcionalidade-chave e gap documentado
  - gaps_de_mercado: Lista de lacunas citadas na literatura acadêmica/jornalística, com fonte
---

# Pesquisar Benchmarking de Segurança

Pesquisa na web apps de segurança/denúncia de violência doméstica de
referência (bSafe, Circle of 6, Guardiã Maria da Penha/SP Mulher Segura,
myPlan, e outros relevantes ao recorte definido pelo usuário), suas
funcionalidades, e as lacunas/críticas documentadas na literatura acadêmica e
jornalística — sempre registrando o gap junto com o diferencial.

## Process

1. Reler o recorte de benchmarking definido no checkpoint "Foco do Brainstorm"
   (apps brasileiros, internacionais, ambos, ou pular benchmarking externo) e
   ajustar o escopo da busca de acordo.
2. Se o recorte não for "pular benchmarking externo": usar `web_search` e
   `web_fetch` para revisar os apps de referência (bSafe, Circle of 6, Guardiã
   Maria da Penha/SP Mulher Segura, myPlan) e localizar revisões sistemáticas
   ou artigos acadêmicos sobre apps de prevenção/resposta à violência
   doméstica.
3. Para cada app de referência encontrado, registrar: funcionalidade
   principal, diferencial, e gap/limitação documentada — nunca listar apenas o
   ponto forte sem o gap correspondente.
4. Se uma funcionalidade depender de integração institucional inviável para o
   escopo do projeto (ex.: tornozeleira eletrônica), registrar como referência
   conceitual com viabilidade técnica marcada como baixa.
5. Identificar explicitamente os gaps de mercado citados na literatura (ex.:
   ausência de IA/sinais comportamentais para alertas proativos, falta de
   mecanismo anti-falso-positivo, foco em resposta emergencial em detrimento de
   prevenção primária) como "espaço em branco" para o ideador.
6. Se o recorte escolhido pelo usuário for "pular benchmarking externo",
   reutilizar apenas o benchmarking já levantado pela squad tcc-documentacao,
   sem nova busca web, e registrar essa decisão explicitamente na saída.

## Output Format

```yaml
apps_referencia:
  - app: "Nome do app"
    origem: "Brasil | Internacional"
    funcionalidade_chave: "Descrição da funcionalidade principal"
    gap_documentado: "Limitação ou crítica documentada"
    viabilidade_tecnica: "Alta | Média | Baixa (para replicar no escopo do Amparo)"
gaps_de_mercado:
  - gap: "Descrição da lacuna"
    fonte: "Fonte/estudo que documenta a lacuna"
    confianca: "ALTA | MÉDIA | BAIXA"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
BENCHMARKING — APPS DE SEGURANÇA/DENÚNCIA

| App | Origem | Funcionalidade-chave | Gap documentado | Viabilidade técnica |
|---|---|---|---|---|
| bSafe | Internacional | Follow Me + fake call | Acionamento manual, sem detecção automática | Alta |
| Circle of 6 | Internacional | Círculo de 6 contatos pré-definidos | Sem cofre de evidências, círculo fixo sem diferenciação de papel | Alta |
| Guardiã Maria da Penha / SP Mulher Segura | Brasil | Cruzamento com tornozeleira eletrônica do agressor | Depende de integração institucional com órgão público | Baixa — não replicável sem parceria institucional |
| myPlan | Internacional | Plano de segurança digital personalizado | Foco em planejamento, não em resposta emergencial em tempo real | Média |

GAPS DE MERCADO IDENTIFICADOS

1. Nenhum dos apps revisados usa IA ou sinais comportamentais para alertas
   proativos — todos dependem de acionamento manual pela vítima.
   Confiança: ALTA
   Fonte: Smartphone Apps for Domestic Violence Prevention — Systematic
   Review (PMC, 2012-2022, 136 apps revisados)

2. Falta de mecanismo de auto-cancelamento padronizado, gerando risco de
   falso alarme e desconfiança no sistema.
   Confiança: MÉDIA
   Fonte: mesma revisão sistemática (PMC)

3. Foco excessivo em resposta emergencial (44,9% dos apps revisados),
   pouca prevenção primária.
   Confiança: ALTA
   Fonte: mesma revisão sistemática (PMC)

Nota: recorte de benchmarking definido pelo usuário nesta rodada — apps
internacionais e brasileiros (ambos). Nenhum app foi descartado por
limitação de idioma da fonte.
```

## Quality Criteria

- [ ] Toda funcionalidade de app concorrente tem um gap/limitação documentado
      junto, nunca apenas o ponto forte.
- [ ] Toda funcionalidade que depende de integração institucional inviável tem
      a viabilidade técnica marcada como Baixa.
- [ ] Os gaps de mercado têm fonte e nível de confiança explícitos.
- [ ] O recorte de benchmarking escolhido pelo usuário no checkpoint foi
      respeitado (não se pesquisou fora do escopo nem se pulou pesquisa
      pedida).

## Veto Conditions

Reject and redo if ANY are true:
1. Um app de benchmarking aparece na lista sem gap/limitação documentado.
2. O recorte de benchmarking do checkpoint foi ignorado (ex.: pesquisou apps
   internacionais quando o usuário pediu só brasileiros, ou vice-versa).
