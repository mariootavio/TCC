# Anti-Patterns — Landing Page Amparo

Anti-padrões consolidados dos 4 agentes da squad. Cada agente tem sua seção.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Camila Conteúdo

### Never Do

1. **Inventar uma funcionalidade do app que não está no backlog real de `brainstorm-amparo`**: viola o princípio de fidelidade à fonte — toda funcionalidade citada no copy precisa de ancoragem real.
2. **Usar depoimento nominal/identificável de uma vítima real**: risco de segurança real para a pessoa e quebra de confiança do público-alvo.
3. **Colocar mais de um CTA primário concorrente na mesma seção**: gera paralisia de decisão e dilui a ação principal.

### Always Do

1. **Citar o RF-CORE ou ideia exata do backlog em toda funcionalidade mencionada no copy**: garante rastreabilidade entre brainstorm e landing page.
2. **Endereçar explicitamente os 3 públicos (vítima/rede de apoio, ONGs/parceiros, banca) em seções ou CTAs distintos**: sem isso, a mensagem dilui ou ignora um público inteiro.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Vitória Visual

### Never Do

1. **Inventar, ajustar ou propor qualquer valor de token (cor, fonte, espaçamento) fora de `brand/design-system.md`**: a marca está finalizada e travada — viola o princípio de tradução fiel usar qualquer valor que não venha exatamente desse arquivo.
2. **Usar foto realista de violência doméstica ou vítima como imagem de seção**: sensacionaliza a causa e pode retraumatizar quem visita a página em risco.
3. **Aplicar uma estética fria/industrial (brutalist) a um produto de tom acolhedor/empático**: contraria diretamente o tom de voz definido em `company.md`.
4. **Especificar motion sem propósito declarado ("deve ficar dinâmico")**: Diego precisa de intenção exata (o que se move, quando, por quê) para implementar sem ambiguidade.

### Always Do

1. **Carregar `brand/design-system.md` e `brand/LogoAmparo.svg` antes de qualquer outra coisa, e as skills `design-taste-frontend` e `high-end-visual-design` para traduzir esse sistema em especificação de telas**: garante um resultado moderno e premium, fiel à marca, nunca genérico ou inventado.
2. **Verificar contraste WCAG AA de cada par texto/fundo antes de considerar a especificação concluída**: única validação de qualidade que Vitória aplica antes da revisão completa de Rafael.
3. **Documentar a especificação visual seção por seção**, incluindo frames responsivos e direção de motion explícitos.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Diego Assets

### Never Do

1. **Criar um valor de cor/fonte/espaçamento fora de `brand/design-system.md`**: quebra a fonte única de verdade do design system.
2. **Recriar o arquivo Figma do zero quando já existe um registrado em `_memory/memories.md`**: fragmenta a landing page em versões paralelas e perde histórico de trabalho.
3. **Chamar `use_figma` sem antes carregar a skill `figma-use`**: pula um pré-requisito que evita erros comuns e difíceis de depurar.
4. **Descrever motion de protótipo Figma como "vídeo"**: gera expectativa errada sobre o que de fato foi entregue.
5. **Gerar imagem em lote especulativo ou sem propósito definido por Vitória**: desperdiça geração e dilui a curadoria visual da página.

### Always Do

1. **Verificar se já existe um arquivo Figma registrado em memória antes de criar um novo**: garante continuidade entre execuções.
2. **Carregar `figma-use`, `figma-generate-design` e `figma-generate-library` antes de construir qualquer seção**: evita retrabalho e inconsistência de tokens.
3. **Documentar o prompt exato de toda imagem gerada**: rastreabilidade para revisão de Rafael e para ajustes futuros.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Rafael Rigor

### Never Do

1. **Avaliar por amostragem**: toda seção e todo frame responsivo precisa ser revisado — o problema não detectado é o que reduz a percepção de qualidade do resultado final.
2. **Aprovar sem carregar `wcag-audit-patterns`**: perde cobertura completa dos critérios POUR aplicados ao design.
3. **Dar feedback vago ("melhorar o visual") sem apontar a página/frame exata**: feedback sem localização não é acionável.

### Always Do

1. **Carregar `web-design-guidelines` e `wcag-audit-patterns` antes de iniciar a revisão**: garante rigor além dos critérios já conhecidos pela squad.
2. **Produzir tabela de pontuação por critério + lista de correções específicas por página/frame**: torna o resultado imediatamente acionável para Diego.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Anti-Padrão Transversal Geral da Squad

Nenhum agente desta squad deve inventar conteúdo (funcionalidade do app,
token visual, estatística) que não esteja ancorado em uma fonte real
(`brainstorm-amparo`, `brand/design-system.md` e `brand/LogoAmparo.svg`
para todo token visual, `company.md`) ou em pesquisa documentada em
`research-brief.md`. Toda ausência de informação deve ser registrada como
pendência explícita, nunca resolvida por invenção.
