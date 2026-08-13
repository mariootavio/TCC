# Squad Memory: fluxos-uxui-amparo

## Estilo de Escrita

## Design Visual

- Telas precisam de acabamento real, não wireframe: sombra em cards (usar o effect style já definido, nunca deixar sem elevação), ícones vetoriais reais (nunca emoji ou texto como placeholder de ícone), e detalhes já especificados no manual da marca mas fáceis de esquecer (ex.: anel de pulso do Botão SOS) devem ser implementados, não pulados. Feedback direto do usuário: "está muito simples, utilizar as skills de design para o fluxo" (2026-08-13).
- Falhas de contraste WCAG encontradas em telas construídas devem ser corrigidas no token do design system (propagando via variável), não centralizadas em relatório como pendência eterna — o usuário prefere resolver na hora quando a correção é uma troca de valor, não uma mudança estrutural.

## Estrutura de Conteúdo

- Ao pedir "telas" ou "protótipo", o usuário espera o app completo e navegável — não apenas as telas dos fluxos críticos formalmente escopados por Joana. Inclui: navegação inferior real (não só definida na arquitetura, mas construída e aplicada), jornada de entrada completa (onboarding/login/cadastro), e o conteúdo de todo item de menu mapeado por Iara (não deixar destinos como "Mais" sem tela própria). Feedback direto: "não tem nada feito na parte das telas do APP, cadê todo o app com o fluxo completo" (2026-08-13).
- O usuário valoriza uma visão única e consolidada (\"quero tudo em uma única tela também com o fluxo completo do aplicativo\") além dos fluxos detalhados separados — um mapa/sitemap de página única com todas as telas e conexões é um entregável esperado, não opcional, em rodadas de prototipagem completas.

## Proibições Explícitas

## Técnico (específico do squad)

- **Protótipos do Figma são "per page"**: a ação `NAVIGATE` do Plugin API rejeita destinos fora da página de origem do frame. Ao organizar telas em várias páginas (uma por fluxo, convenção desta squad), conexões entre páginas (ex.: saída rápida → disfarce, bottom nav entre hubs) não podem ser wireds diretamente — é necessário criar uma réplica local do destino na página de origem, ou aceitar que a interatividade fica limitada à página, documentando a limitação (não é bug do trabalho, é constraint da plataforma).
- Nós dentro de um frame com `layoutMode` (auto-layout) ignoram `x`/`y` manuais a menos que `layoutPositioning = 'ABSOLUTE'` seja definido explicitamente antes de posicionar — causa comum de elementos "grudados" no topo do fluxo em vez de fixados (ex.: ícone de saída rápida, barra de navegação inferior).
