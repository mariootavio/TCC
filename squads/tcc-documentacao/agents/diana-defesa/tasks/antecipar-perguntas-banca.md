---
task: "Antecipar Perguntas da Banca"
order: 2
input: |
  - teses: Output da task construir-teses-argumentativas.md
  - relatorio_tcc: Conteúdo de squads/tcc-documentacao/output/relatorio-tcc.md
output: |
  - perguntas_banca: Lista de 10-15 perguntas frequentes com resposta preparada de 2-4 frases cada
---

# Antecipar Perguntas da Banca

Lista as perguntas mais prováveis da banca examinadora — sobre metodologia,
limitações, escolhas de design, comparação com soluções existentes — com
respostas preparadas, fechadas e baseadas em evidência.

## Process

1. A partir das teses já formuladas e do relatório, mapear categorias de
   perguntas típicas de banca de TCC: metodologia, recorte do tema,
   limitações do estudo, comparação com soluções existentes, viabilidade
   técnica/jurídica.
2. Para cada categoria, formular 2-4 perguntas específicas ao conteúdo deste
   TCC (nunca perguntas genéricas que serviriam para qualquer trabalho).
3. Compilar a lista completa até atingir entre 10 e 15 perguntas.
4. Para cada pergunta, escrever uma resposta preparada de 2-4 frases, citando
   evidência do research brief ou do relatório sempre que aplicável.
5. Garantir que toda limitação do estudo mencionada no relatório também
   apareça como pergunta antecipada nesta lista, com resposta associada.
6. Revisar se alguma resposta ficou como placeholder ou nota de "a
   confirmar" — se sim, sinalizar explicitamente como pendência a resolver
   antes da aprovação final, nunca disfarçar como resposta completa.

## Output Format

```yaml
perguntas_banca:
  - categoria: "metodologia | limitações | comparação | viabilidade"
    pergunta: "Pergunta provável da banca"
    resposta: "Resposta preparada de 2-4 frases"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
PERGUNTAS ANTECIPADAS DA BANCA

[Categoria: Comparação com soluções existentes]

P: "Por que não usar uma solução já existente e aprovada
institucionalmente, como o Botão do Pânico estadual?"

R: O Botão do Pânico estadual exige que a vítima já tenha obtido uma medida
protetiva de urgência — ou seja, pressupõe que ela já denunciou formalmente.
O Amparo atua antes desse ponto: no momento em que a vítima ainda está
decidindo se e como denunciar. Isso não compete com a solução estatal,
complementa-a, servindo de ponte entre a violência silenciosa e o
acionamento formal do sistema de justiça.

[Categoria: Limitações do estudo]

P: "O trabalho não validou a solução com usuárias reais em situação de
violência doméstica — isso não é uma limitação grave da pesquisa?"

R: Sim, essa é uma limitação reconhecida explicitamente no capítulo de
Considerações Finais. A validação com usuárias reais exigiria protocolo
ético específico para população vulnerável, fora do escopo temporal deste
TCC. A avaliação realizada foi [conforme metodologia do trabalho], e a
validação com usuárias reais é indicada como trabalho futuro.

[Categoria: Viabilidade técnica]

P: "Como o Amparo garante que o armazenamento remoto de provas não cria um
novo risco de exposição de dados sensíveis?"

R: [PENDÊNCIA — resposta depende de confirmação da arquitetura técnica real
do Amparo (criptografia em trânsito/repouso, controle de acesso). Resolver
antes da aprovação final.]
```

## Quality Criteria

- [ ] Existem entre 10 e 15 perguntas antecipadas, cobrindo metodologia,
      limitações, comparação e viabilidade.
- [ ] Cada pergunta tem resposta preparada de 2-4 frases.
- [ ] Toda limitação mencionada no relatório também aparece como pergunta
      nesta lista, com resposta associada.

## Veto Conditions

Reject and redo if ANY are true:
1. A lista tem menos de 10 perguntas.
2. Alguma resposta é um placeholder genérico (ex.: "vamos verificar depois")
   sem estar explicitamente marcada como pendência a resolver.
