# Prompts de montagem visual

Use esses templates na Etapa 7 (final do processo). O objetivo é entregar ao usuário um prompt **pronto para colar** em ferramentas de design visual, traduzindo o manual produzido em instruções executáveis.

Adapte cada template substituindo as variáveis em `{CHAVES}` com os dados reais da marca que você acabou de produzir.

---

## Prompt para Figma (Figma AI / First Draft)

```
Crie um documento de manual de identidade visual para a marca "{NOME_DA_MARCA}".

Estilo editorial, padrão de estúdio premium. Não use estilo "infográfico do Canva".

Formato: A4 retrato (210x297mm), 30+ páginas.

Sistema visual da marca:
- Cor primária: {HEX_PRIMARIA} ({NOME_PRIMARIA})
- Cor secundária: {HEX_SECUNDARIA} ({NOME_SECUNDARIA})  
- Cor escura: {HEX_ESCURA} ({NOME_ESCURA})
- Cor de fundo neutra: {HEX_FUNDO} ({NOME_FUNDO})
- Fonte display (títulos): {FONTE_DISPLAY}
- Fonte de texto: {FONTE_TEXTO}
- Elemento gráfico signature: {DESCRICAO_DO_ELEMENTO}

Estrutura de páginas (cada uma é um frame separado):
1. Capa — logo centralizado, fundo neutro, slogan no rodapé
2. Sumário — tipografia hierárquica, números de página alinhados à direita
3-4. Apresentação da marca — página dupla com citação à esquerda e texto corrido à direita
5-7. Essência e fundamentos — uma página para propósito (frase grande centralizada), uma para missão/visão em duas colunas, uma para valores em cards
8-9. Personalidade e tom de voz — blocos visuais para personalidade, tabela "diz/não diz" para tom
10-14. Logotipo — apresentação, construção, versões, área de proteção, usos corretos, usos incorretos
15-18. Paleta de cores — cards generosos por cor (mínimo 80x80mm), escala cromática, gradientes, combinações sugeridas
19-21. Tipografia — exibição grande do alfabeto, hierarquia visual em escala
22-24. Elementos gráficos, ícones e fotografia
25-32. Aplicações da marca — uma página por aplicação (redes sociais, site, apresentação, cartão, banner, fachada)
33. Checklist de auditoria — checklist visual
34. Encerramento — espelhando a capa

Regras de layout:
- Margens generosas (mínimo 20mm).
- Hierarquia tipográfica clara: H1 em 48pt da fonte display, H2 em 32pt, H3 em 20pt, texto em 11pt.
- Cada página tem cabeçalho discreto com o nome da marca + numeração da página no rodapé.
- Use o elemento gráfico signature em opacidade 8-15% como detalhe sutil em algumas páginas — nunca dominante.
- Fundo padrão: cor neutra clara. Páginas-destaque (citações, propósito) podem ter fundo escuro ou primária.

Estilo geral: editorial, contido, com respiro. Não sobrecarregue. Pense em revista de design, não em flyer.
```

---

## Prompt para Canva (Magic Design / Brand Kit)

```
Quero montar um manual de identidade visual no Canva para a marca "{NOME_DA_MARCA}".

Antes de começar, configure o Brand Kit:
- Logo principal (upload): {ARQUIVO_LOGO}
- Cores da paleta: {LISTA_DE_HEX_COM_NOMES}
- Fontes: {FONTE_DISPLAY} para títulos, {FONTE_TEXTO} para corpo de texto

Crie um documento "Apresentação" em formato vertical (1080x1920) com 30 slides.

Cada slide é uma página do manual. Use o template "Apresentação editorial / brand book" como base, mas substitua TODAS as cores e fontes pelas da marca.

Sequência dos slides:
1. Capa: logo centralizado, fundo {COR_NEUTRA}, slogan no rodapé.
2. Sumário: lista de seções alinhada à esquerda, números à direita.
3-4. Apresentação: texto da história da marca em duas colunas.
5. Propósito: 1 frase grande centralizada, fundo {COR_ESCURA}, texto na cor {COR_NEUTRA}.
6. Missão e Visão: duas colunas.
7. Valores: 4 cards (1 por valor), cada card com ícone e descrição.
8. Personalidade: 4-6 blocos com traços de personalidade.
9. Tom de voz: tabela "Diz / Não Diz" em duas colunas.
10. Logotipo principal grande, fundo neutro.
11. Versões do logotipo: grid 2x3.
12. Área de proteção e tamanho mínimo: diagrama com cotas.
13. Usos corretos: grid de 4-6 exemplos com check verde.
14. Usos incorretos: grid de 6-8 exemplos com X vermelho.
15. Paleta de cores principais: cards grandes.
16. Cores neutras e de apoio: cards.
17. Escala cromática: barras lado a lado.
18. Gradientes oficiais.
19. Tipografia primária: alfabeto exibido grande.
20. Tipografia secundária: alfabeto exibido grande.
21. Hierarquia tipográfica: H1, H2, H3, texto, legenda, em escala visual.
22. Elementos gráficos da marca.
23. Sistema de ícones: galeria.
24. Linguagem fotográfica: mood board com 6 imagens de referência.
25. Aplicação em Instagram (feed + stories).
26. Aplicação em site (header + hero).
27. Aplicação em apresentação comercial.
28. Aplicação em cartão de visitas (frente e verso).
29. Aplicação em assinatura de e-mail.
30. Checklist final + página de encerramento.

Use o Brand Kit ativo. Não use cores fora da paleta. Não substitua fontes.
```

---

## Prompt para Adobe InDesign

```
Estou montando um manual de identidade visual no InDesign para a marca "{NOME_DA_MARCA}".

Configuração do documento:
- Tamanho: A4 retrato (210x297mm)
- Páginas: 34 (espelhadas para visualização de página dupla)
- Margens: superior 25mm, inferior 25mm, externa 20mm, interna 25mm
- Coluna principal: 1 coluna com gutter de 5mm
- Sangria: 3mm
- Páginas mestras: criar "A-Capa", "B-Conteúdo", "C-Destaque" (fundo escuro)

Estilos de parágrafo a criar:
- "H1-Display" — {FONTE_DISPLAY}, 48pt, peso Regular, tracking +20, cor {COR_PRIMARIA}
- "H2-Seção" — {FONTE_DISPLAY}, 32pt, peso Medium, cor {COR_ESCURA}
- "H3-Subtítulo" — {FONTE_TEXTO}, 18pt, peso SemiBold, cor {COR_ESCURA}
- "Corpo" — {FONTE_TEXTO}, 11pt, peso Regular, entrelinha 16pt, cor {COR_ESCURA}
- "Legenda" — {FONTE_TEXTO}, 8pt, tracking +40, caixa alta, cor {COR_PRIMARIA}
- "Citação" — {FONTE_DISPLAY}, 24pt italic, cor {COR_PRIMARIA}

Estilos de cor (Swatches):
{LISTA_DE_HEX_COM_NOMES_EM_CMYK}

Sequência de páginas: [seguir estrutura padrão]

Use formato PDF/X-1a:2001 para exportação final. Incluir marcas de corte e sangria 3mm.
```

---

## Prompt para Midjourney (gerar mockups para o manual)

Quando o manual precisa de mockups visuais (cartão de visita real, fachada renderizada, peça impressa em contexto), use estes prompts:

```
[Para mockup de cartão de visita]
mockup of premium business card design, brand "{NOME_DA_MARCA}", color palette: {DESCRICAO_DAS_CORES}, on natural texture surface (linen, wood, marble), top-down angle, soft natural light, editorial photography style, minimal composition, --ar 4:3 --style raw --v 6
```

```
[Para mockup de fachada]
modern facade signage for "{TIPO_DE_NEGOCIO}" called "{NOME_DA_MARCA}", logo in {COR_PRIMARIA}, premium signage, daylight, architectural photography, sophisticated minimal aesthetic --ar 16:9 --style raw --v 6
```

```
[Para mockup de social media]
flat lay of branding materials on neutral background, business cards, brochure, smartphone showing Instagram feed for brand "{NOME_DA_MARCA}", color palette {LISTA_DE_CORES}, editorial photography, soft shadows, sophisticated minimal aesthetic --ar 3:4 --style raw --v 6
```

```
[Para mockup de embalagem - quando aplicável]
premium packaging mockup for {TIPO_DE_PRODUTO} from "{NOME_DA_MARCA}", brand colors {LISTA_DE_CORES}, natural product photography, soft daylight, neutral background, editorial composition --ar 4:5 --style raw --v 6
```

---

## Recomendação ao entregar ao usuário

Sempre que apresentar esses prompts:

1. **Substitua as variáveis** com os dados reais da marca antes de entregar. Não deixe `{NOME_DA_MARCA}` no prompt final.
2. **Indique qual ferramenta recomenda** com base na situação do usuário:
   - Tem orçamento e equipe → Figma ou InDesign
   - Faz sozinho, pouco tempo → Canva
   - Precisa de mockups realistas para apresentar ao cliente → Midjourney
3. **Avise sobre limites**: Canva é mais rápido mas menos preciso. InDesign exige conhecimento. Figma é o equilíbrio ideal para times de design.
