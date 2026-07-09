# Direção de layout — Princípios e biblioteca

Este arquivo é o **manual interno de direção de layout** que você (Claude) consulta sempre que precisa descrever a **direção visual de uma página**. Em vez de improvisar instruções soltas, recorra aos princípios e padrões aqui descritos.

A regra geral: nunca diga "use um layout limpo e bonito". Diga **qual sistema de layout**, **qual grid**, **qual hierarquia**, **qual ritmo**.

---

## 1. Sistema de grid

O grid é o esqueleto invisível que sustenta a composição. Toda página do manual e toda aplicação da marca segue um grid.

### Grid editorial (manual impresso A4)

- **Coluna única + margens generosas:** para textos longos, citações, capas. Margens 25-30mm.
- **Duas colunas:** para páginas duplas (texto + imagem; conceito + exemplo).
- **Grid de 12 colunas:** para páginas com muitos elementos (paleta de cores, galeria de ícones, aplicações).
- **Grid modular (cards):** para apresentação de variações (versões de logo, combinações de cores).

### Grid digital

- **Mobile-first**: comece pelo grid de 4 colunas (mobile), expanda para 8 (tablet), 12 (desktop).
- **Gutter (espaço entre colunas)**: 16-24px desktop, 8-16px mobile.
- **Container máximo**: 1280px (sites tradicionais), 1440px (sites com mais respiro), 100% com padding lateral (sites editoriais).

### Quando escolher cada grid

| Tipo de página | Grid recomendado |
|----------------|------------------|
| Capa / propósito / página de citação | Coluna única, centralizado, muito respiro |
| História da marca / texto corrido | Coluna única com margem lateral generosa |
| Página dupla (mood + texto) | Duas colunas |
| Paleta de cores | Grid 4x3 ou 6x2 de cards |
| Tipografia | Coluna única com hierarquia escalonada |
| Galeria de ícones | Grid de 6x4 ou 8x4 |
| Aplicações reais | Variável — uma aplicação por página, com mockup grande |
| Checklist | Coluna única, espaçamento generoso entre itens |

---

## 2. Hierarquia visual

A hierarquia é como o olho viaja pela página. Toda página premium tem **3 níveis claros**: o primeiro foco, o segundo plano, o terceiro plano (detalhes).

### Princípios

1. **Um foco por página.** Se há dois elementos do mesmo peso visual, o olho não sabe onde ir. Escolha.
2. **Contraste é hierarquia.** Tamanho, cor, peso de fonte, isolamento — tudo cria hierarquia.
3. **Hierarquia tipográfica é o esqueleto.** H1 muito maior que H2. H2 maior que H3. Diferença visível, não sutil.
4. **Isolamento aumenta peso.** Um elemento sozinho num espaço grande tem mais peso do que muitos elementos próximos.

### Anti-padrões de hierarquia

- ❌ Tudo em bold (perde hierarquia — bold só vale se há contraste com texto regular)
- ❌ Múltiplos elementos competindo por destaque (3 botões primários no mesmo bloco)
- ❌ Tipografia sem variação (todos os blocos no mesmo tamanho)
- ❌ Cores quentes em excesso (vermelho/laranja gritam, perdem hierarquia se aplicados demais)

---

## 3. Respiro e espaço negativo

O espaço vazio é elemento ativo. Em manuais premium, **respiro é assinatura visual**.

### Regras práticas

- **Margens generosas** valem mais do que conteúdo amontoado. Em A4, nunca menos de 20mm.
- **Espaço entre blocos** maior do que espaço dentro do bloco. Cria hierarquia visual sem precisar de linhas.
- **Páginas de respiro** (uma frase grande sobre fundo limpo) entre páginas densas. Funcionam como pausas musicais.
- **Espaço ao redor do logo** é sagrado. Área de proteção (2X) é mínima, não meta.

### Pergunta de auditoria

> "Se eu tirar 30% do conteúdo desta página e aumentar 30% o espaço em branco, ela fica pior ou melhor?"

Se ficar **melhor** ou **igual**: a página estava amontoada. Tire o conteúdo.

---

## 4. Ritmo editorial

Um manual de 40 páginas todas no mesmo formato é monotonia. Alterne.

### Padrão de ritmo

1. **Capa** (densa: logo + identidade)
2. **Sumário** (lista, vertical)
3. **Página densa** (texto + estrutura)
4. **Página leve** (uma frase, muito respiro) — *pausa*
5. **Página densa** (tabela ou regras)
6. **Página leve** (mood board ou imagem) — *pausa*
7. **Página densa** (specs técnicas)
8. **Página leve** (citação ou propósito) — *pausa*

A cada 2-3 páginas densas, **uma página leve**. O leitor respira.

### Variantes de página leve

- **Frase grande** sobre fundo cor primária ou neutro: o propósito, um valor, um manifesto
- **Imagem ocupando 100%**: mood, foto signature, textura
- **Tipografia exibida em escala grande**: o alfabeto, o monograma, o slogan
- **Citação editorial**: uma fala da marca, atribuída ou anônima

---

## 5. Princípios de alinhamento

Alinhamento é o que diferencia design profissional de amador. **Tudo deve estar alinhado a algo.**

### Regras

- **Alinhamento à esquerda** é o default editorial. Texto corrido sempre à esquerda (não justificado, exceto em casos editoriais raros).
- **Centralizado** apenas para destaque (capa, citação, título de capítulo). Nunca para texto longo.
- **À direita** apenas em casos pontuais: números de página, legendas curtas alinhadas a uma imagem à direita.
- **Múltiplos alinhamentos numa mesma peça** = caos. Escolha um e mantenha.

### Anti-padrões

- ❌ Tudo centralizado (sintoma de design amador)
- ❌ Texto justificado sem ajuste de espaçamento (cria "rios" brancos no texto)
- ❌ Elementos próximos sem alinhamento claro (parece "espalhado")

---

## 6. Princípios de cor no layout

A paleta é definida em outra seção. Aqui é como a cor **opera dentro do layout**.

### Regras

- **Fundo neutro é a base.** 60-70% das páginas têm fundo neutro claro. Cor cheia é exceção, não regra.
- **Cor primária como destaque, não como base.** Use em CTAs, ícones, detalhes — não como fundo de bloco de texto corrido.
- **Cor escura para texto.** Texto preto puro (#000) é raro em marcas premium; prefira a cor escura da paleta (geralmente um marrom, azul-marinho, ou verde-floresta escuros). Cria sofisticação.
- **Páginas-destaque** podem ter fundo de cor primária ou escura, mas devem ser **exceções editoriais** — 1 a cada 4-5 páginas.

### Paleta dentro do manual

| Tipo de página | Fundo recomendado |
|----------------|-------------------|
| Capa | Cor neutra clara OU cor escura signature |
| Sumário | Cor neutra clara |
| Texto corrido | Cor neutra clara |
| Página de destaque (propósito, citação) | Cor primária ou escura |
| Paleta de cores | Cor neutra clara (deixa as cores falarem) |
| Tipografia | Cor neutra clara |
| Aplicações | Variável conforme a aplicação retratada |
| Encerramento | Espelhar a capa |

---

## 7. Tipografia como sistema de layout

A tipografia não é só "qual fonte usar". É **estrutura de layout**.

### Hierarquia padrão para o manual

- **H1 — Display, 48-72pt** — abertura de capítulo, propósito, citações grandes
- **H2 — Display ou Sans, 32-40pt** — título de seção
- **H3 — Sans Medium, 18-22pt** — subtítulo
- **Texto — Sans Regular, 10-12pt** — corpo
- **Legenda — Sans Regular, 8-9pt** — descritivo curto
- **Microcopy — Sans Regular, 7-8pt** — específicos técnicos, hex codes

### Entrelinha (line-height)

- H1: 1.0 a 1.1 (apertado, dá impacto)
- H2: 1.2
- H3: 1.3
- Texto: 1.5 a 1.7 (respiro vertical para leitura confortável)
- Legenda: 1.4

### Letter-spacing

- Caixa alta: sempre com tracking aberto (+40 a +80 em unidades de mil)
- Display em tamanho grande: tracking levemente fechado (-10 a -20)
- Texto corrido: 0

---

## 8. Direção de layout por tipo de página

Resumo prático: para cada tipo de página do manual, qual a direção de layout?

### Capa
- Composição centralizada com muito respiro.
- Logotipo principal ocupa 30-40% da área útil.
- Subtítulo ("Manual de Identidade Visual" + ano) abaixo, fonte de apoio em tamanho pequeno.
- Fundo: neutro claro OU cor escura assinatura.
- Elemento gráfico signature pode aparecer em opacidade reduzida.

### Sumário
- Coluna única, alinhamento à esquerda.
- Tipografia hierárquica (capítulos em destaque, subseções em peso menor).
- Linha sutil ou ponto separando título de número de página.
- Margens generosas.

### Página de propósito / citação
- Uma frase ocupando 50-70% da área útil.
- Centralizada vertical e horizontalmente.
- Fonte display em tamanho grande (48-72pt).
- Sem outros elementos competindo. Pode ter o elemento gráfico signature pequeno acima ou abaixo.
- Fundo cor primária ou escura para máximo impacto.

### Página de paleta de cores
- Grid de cards generosos (mínimo 80x80mm cada).
- Cada card mostra: cor cheia em cima, dados (nome, hex, RGB, CMYK, Pantone, uso) embaixo.
- Cards em fundo neutro claro para destacar as cores.
- Mínimo respiro entre cards.

### Página de tipografia
- Alfabeto exibido em tamanho muito grande (200-400pt) em uma página.
- Pesos da fonte exibidos em outra (Regular, Medium, SemiBold, Bold lado a lado).
- Hierarquia tipográfica em terceira página: escala visual de H1 a microcopy.

### Página de aplicação real
- Mockup grande da peça ocupando 60-70% da página.
- Texto descritivo (anatomia + specs) ao lado em coluna mais estreita.
- Pode incluir miniaturas de variações no rodapé.

### Checklist
- Coluna única, alinhamento à esquerda.
- Espaçamento vertical generoso entre itens (mínimo 16pt).
- Checkboxes desenhados (□) à esquerda de cada item.
- Tipografia de texto em peso regular.
- Agrupamento por categorias com subtítulo em H3.

---

## 9. Anti-padrões de layout (proibidos em manuais premium)

Estes layouts denunciam amadorismo. Trate como inimigos:

- ❌ **Tudo centralizado** (capas, sumário, texto, tudo no centro = preguiça compositional)
- ❌ **Cores berrantes sem hierarquia** (verde-limão, magenta, ciano juntos sem propósito)
- ❌ **Cantos arredondados em excesso** (caixinhas com `border-radius` alto em tudo = aparência de Canva default)
- ❌ **Sombras drop padrão** (sombras de Photoshop dos anos 2000)
- ❌ **Gradientes saturados sem critério** (arco-íris, neon, hologramas — quase sempre erram)
- ❌ **Ícones de bibliotecas misturadas** (Material + Font Awesome + emoji na mesma peça)
- ❌ **Fontes de Word default** (Calibri, Times New Roman, Arial — exceto se forem escolha consciente)
- ❌ **Imagens com qualidade baixa** (logo pixelado, foto serrilhada)
- ❌ **Texto sobre foto sem overlay** (texto disputando atenção com a imagem ao fundo)
- ❌ **Bullets longos como conteúdo principal** (manual virou lista, perdeu o caráter editorial)
- ❌ **Justificação forçada com "rios" brancos** (texto cheio de buracos por causa de justificação mal ajustada)

---

## 10. Como descrever direção de layout no manual

Quando você (Claude) for descrever a direção de layout de uma página, use esta fórmula:

> "**Página [N] — [Título]**
>
> **Layout:** [grid escolhido]. [posicionamento dos elementos principais].
>
> **Hierarquia visual:** [primeiro foco], [segundo plano], [terceiro plano].
>
> **Cor de fundo:** [cor específica com hex].
>
> **Tipografia em destaque:** [fonte + tamanho + peso].
>
> **Espaços:** margens [X], gutters [Y].
>
> **Elementos decorativos:** [elemento gráfico signature, opacidade, posição].
>
> **Ritmo:** página [densa / leve / de transição]."

### Exemplo aplicado

> **Página 14 — Paleta de cores principais**
>
> **Layout:** grid 3 colunas em página A4 retrato. Três cards de cor lado a lado, cada um ocupando 1/3 da largura útil.
>
> **Hierarquia visual:** primeiro foco — as três grandes amostras de cor cheia ocupando 50% vertical de cada card; segundo plano — nome da cor em fonte display logo abaixo; terceiro plano — dados técnicos (hex, RGB, CMYK, Pantone, uso) em fonte de apoio.
>
> **Cor de fundo:** #FAF5EF (Linho Natural).
>
> **Tipografia em destaque:** Cormorant Garamond Medium 22pt para nome da cor; Inter Regular 9pt com letter-spacing +40 para dados técnicos.
>
> **Espaços:** margens 25mm em todos os lados; gutter de 12mm entre cards.
>
> **Elementos decorativos:** ícone discreto do sol estilizado no canto superior direito de cada card (opacidade 30%, 16x16mm).
>
> **Ritmo:** página densa de catálogo. Será seguida por uma página leve (citação ou propósito de cor).

Essa estrutura garante que **qualquer designer consiga executar a página sem dúvidas**. É o que torna o manual operacional, não decorativo.
