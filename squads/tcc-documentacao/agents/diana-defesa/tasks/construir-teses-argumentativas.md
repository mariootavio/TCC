---
task: "Construir Teses Argumentativas"
order: 1
input: |
  - relatorio_tcc: Conteúdo de squads/tcc-documentacao/output/relatorio-tcc.md
  - research_brief: Conteúdo de squads/tcc-documentacao/pipeline/data/research-brief.md
output: |
  - teses: Lista de 3-5 teses argumentativas centrais, cada uma com evidência de suporte, contra-argumento provável e resposta preparada
---

# Construir Teses Argumentativas

A partir do research brief e do relatório, formula as teses centrais do TCC
(problema → objetivo → contribuição) com evidências de suporte, antecipando o
contra-argumento mais provável que a banca levantaria para cada uma.

## Process

1. Ler o relatório estruturado e o research brief, identificando a cadeia
   lógica central: problema de pesquisa → objetivo → contribuição/solução
   (Amparo) → evidência de suporte.
2. Formular de 3 a 5 teses argumentativas centrais, cada uma defensável com
   dados concretos do research brief — nunca com opinião ou senso comum.
3. Para cada tese, identificar o contra-argumento mais provável que a banca
   levantaria, considerando pontos frágeis reais (não hipotéticos triviais).
4. Preparar a resposta a cada contra-argumento citando evidência de suporte
   adicional — nunca apenas reafirmar a tese original sem novo dado.
5. Quando a resposta a um contra-argumento depender de detalhe técnico do
   Amparo ainda não confirmado (ex.: arquitetura de segurança), marcar
   explicitamente como pendência a ser confirmada com a documentação interna
   do projeto, em vez de inventar a resposta.
6. Citar, para cada tese, a seção exata do research brief ou relatório de
   onde vem a evidência.

## Output Format

```yaml
teses:
  - titulo: "TESE N: enunciado da tese"
    evidencia_suporte: "Dado + fonte + seção de origem"
    contra_argumento: "Pergunta crítica provável da banca"
    resposta_preparada: "Resposta com evidência adicional, ou nota de pendência se depender de dado técnico não confirmado"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
TESE 1: A subnotificação, não a ausência de violência, é a barreira central
a ser endereçada.

Evidência de suporte: Estudo do Observatório da Mulher contra a Violência
(Senado, DataSenado) estima subnotificação de 61% no registro de violência
contra a mulher no Brasil — 6 em cada 10 vítimas não procuram a delegacia.
(Fonte: research-brief.md, Seção "Dados e Estatísticas", Confiança: ALTA)

Contra-argumento provável da banca: "Se a vítima não denuncia por medo do
agressor, um app não resolve esse medo — por que a solução tecnológica
endereçaria a causa raiz?"

Resposta preparada: O Amparo não substitui o enfrentamento do medo, mas
reduz a fricção e o risco do primeiro passo: documentação segura de provas
sem exposição imediata, rede de apoio pessoal antes da denúncia formal, e
acesso a profissionais para construir um plano de saída gradual. A
literatura (revisão MDPI/PMC, 2023) já identifica que apps existentes falham
justamente por dependerem de exposição imediata e acionamento manual sem rede
de apoio prévia — o Amparo ataca exatamente essa lacuna intermediária.

---

TESE 3: A arquitetura de documentação segura do Amparo responde a uma falha
técnica documentada na literatura internacional.

Evidência de suporte: Revisão sistemática (MDPI/PMC, 2023, 136 apps
analisados) identifica que o armazenamento local de provas é vulnerável caso
o agressor tenha acesso ao aparelho. (Fonte: research-brief.md, Seção "Gaps
identificados na literatura")

Contra-argumento provável da banca: "Como o Amparo garante que o
armazenamento remoto de provas não cria um novo risco de exposição de dados
sensíveis?"

Resposta preparada: [PENDÊNCIA — depende de detalhes técnicos de arquitetura
do Amparo. Confirmar com a documentação interna do projeto: criptografia em
trânsito/repouso, controle de acesso, ausência de indicadores visuais do app.]
```

## Quality Criteria

- [ ] Existem entre 3 e 5 teses argumentativas centrais.
- [ ] Cada tese cita a seção exata do research brief ou relatório de onde
      vem a evidência.
- [ ] Cada tese tem um contra-argumento provável e uma resposta preparada (ou
      pendência explicitamente marcada).

## Veto Conditions

Reject and redo if ANY are true:
1. Uma tese é formulada sem evidência rastreável citada explicitamente.
2. Uma resposta a contra-argumento é inventada como certeza quando depende de
   dado técnico não confirmado, em vez de marcada como pendência.
