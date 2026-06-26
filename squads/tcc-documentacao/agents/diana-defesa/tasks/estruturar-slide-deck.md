---
task: "Estruturar Slide Deck"
order: 3
input: |
  - teses: Output da task construir-teses-argumentativas.md
  - perguntas_banca: Output da task antecipar-perguntas-banca.md
  - relatorio_tcc: Conteúdo de squads/tcc-documentacao/output/relatorio-tcc.md
output: |
  - roteiro_slides: Lista ordenada de slides com título, conteúdo-chave e nota de fala, respeitando proporção de ~1 slide/minuto
---

# Estruturar Slide Deck

Produz o roteiro do slide deck de defesa (estrutura, conteúdo por slide,
tempo estimado de fala), seguindo a proporção de 1 slide por minuto para uma
apresentação típica de 20-30 minutos.

## Process

1. Calcular o número-alvo de slides com base na duração esperada da defesa
   (padrão: 20 minutos ≈ 18-20 slides, na proporção de ~1 slide/minuto).
2. Estruturar a sequência seguindo a ordem: capa → problema → contexto →
   problema de pesquisa → objetivos → justificativa → referencial teórico →
   metodologia → resultados/solução (Amparo) → validação → limitações →
   contribuição/trabalhos futuros → encerramento.
3. Para cada slide, especificar título, conteúdo-chave (no máximo 3-5
   bullets ou um elemento visual central — nunca texto corrido) e nota de
   fala sugerida.
4. Garantir que toda limitação do estudo identificada na task
   `antecipar-perguntas-banca.md` apareça em um slide dedicado, com nota de
   fala que a apresente com confiança, não como fraqueza escondida.
5. Verificar que o slide final de contribuição recupera explicitamente a
   promessa feita no slide de objetivos (introdução), fechando o arco
   narrativo da apresentação.
6. Revisar a contagem final de slides contra a duração-alvo — se exceder a
   proporção de 1 slide/minuto, condensar slides de conteúdo similar.

## Output Format

```yaml
roteiro_slides:
  duracao_estimada_min: 20
  total_slides: 18
  slides:
    - numero: 1
      titulo: "Título do slide"
      conteudo: "Bullets ou elemento visual central"
      nota_fala: "O que dizer neste slide"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
ROTEIRO DE SLIDE DECK — DEFESA TCC AMPARO
Duração estimada: 20 minutos | 18 slides (~1,1 min/slide)

SLIDE 1 — Capa
Conteúdo: Título do TCC, nome do autor, orientador(a), instituição, data.
Nota de fala: Apresentação protocolar, 15 segundos.

SLIDE 2 — O problema em um dado
Conteúdo: "61% das mulheres vítimas de violência doméstica no Brasil não
denunciam" (DataSenado). Visual: número grande + ícone, sem texto corrido.
Nota de fala: Abrir com o dado de subnotificação como gancho — é o número
que justifica a existência do projeto inteiro.

SLIDE 9 — A lacuna identificada
Conteúdo: Síntese visual do gap (diagrama "antes da denúncia formal" vs.
"depois da denúncia formal" com o Amparo posicionado no meio).
Nota de fala: Este é o slide-chave da tese central do TCC.

SLIDE 16 — Limitações do estudo
Conteúdo: 2-3 limitações reconhecidas explicitamente (ex.: ausência de
validação com usuárias reais em situação de violência doméstica).
Nota de fala: Apresentar limitações com confiança — antecipa e neutraliza a
pergunta da banca sobre o tema.

SLIDE 17 — Contribuição e trabalhos futuros
Conteúdo: Síntese da contribuição original do TCC + 2-3 sugestões de
continuidade.
Nota de fala: Recuperar a promessa feita no slide 4 (objetivos) e mostrar
que foi cumprida.

SLIDE 18 — Encerramento
Conteúdo: Agradecimentos + abertura para perguntas.
Nota de fala: Transição direta para a arguição, sem prolongar.
```

## Quality Criteria

- [ ] O número total de slides respeita a proporção de ~1 slide por minuto
      da duração estimada.
- [ ] Nenhum slide tem mais de 5 bullets ou texto corrido em parágrafo.
- [ ] Toda limitação do estudo do relatório aparece em um slide dedicado.
- [ ] O slide de contribuição final recupera explicitamente os objetivos
      apresentados nos primeiros slides.

## Veto Conditions

Reject and redo if ANY are true:
1. O total de slides excede significativamente a proporção de 1 slide/minuto
   para a duração estimada (ex.: 40 slides para 20 minutos).
2. Algum slide contém parágrafo de texto corrido em vez de bullets/visual.
