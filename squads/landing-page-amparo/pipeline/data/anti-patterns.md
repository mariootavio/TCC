# Anti-Patterns — Landing Page Amparo

Anti-padrões consolidados dos 5 agentes da squad. Cada agente tem sua seção.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Camila Conteúdo

### Never Do

1. **Inventar uma funcionalidade do app que não está no backlog real de `brainstorm-amparo`**: viola o princípio de fidelidade à fonte — toda funcionalidade citada no copy precisa de ancoragem real.
2. **Usar depoimento nominal/identificável de uma vítima real**: risco de segurança real para a pessoa e quebra de confiança do público-alvo.
3. **Colocar mais de um CTA primário concorrente na mesma seção**: gera paralisia de decisão e dilui a ação principal.
4. **Tratar a Saída Rápida como detalhe a definir depois**: esse requisito precisa existir antes de qualquer decisão visual ou de código, nunca como adendo.

### Always Do

1. **Citar o RF-CORE ou ideia exata do backlog em toda funcionalidade mencionada no copy**: garante rastreabilidade entre brainstorm e landing page.
2. **Endereçar explicitamente os 3 públicos (vítima/rede de apoio, ONGs/parceiros, banca) em seções ou CTAs distintos**: sem isso, a mensagem dilui ou ignora um público inteiro.
3. **Especificar a Saída Rápida com posição, rótulo, comportamento e atalho de teclado exatos**: ambiguidade aqui se propaga como falha de segurança real no código.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Vitória Visual

### Never Do

1. **Inventar um valor de token (cor, espaçamento) quando o design system da marca-design-amparo já existe**: viola o princípio de tradução fiel — usar o que já foi decidido, não reinterpretar.
2. **Usar foto realista de violência doméstica ou vítima como imagem de seção**: sensacionaliza a causa e pode retraumatizar quem visita a página em risco.
3. **Aplicar uma estética fria/industrial (brutalist) a um produto de tom acolhedor/empático**: contraria diretamente o tom de voz definido em `company.md`.
4. **Esconder a marcação "PENDENTE" quando o design system da marca ainda não existe**: mascarar a ausência de fonte real impede a correção posterior quando a marca publicar.

### Always Do

1. **Carregar as skills `design-taste-frontend` e `high-end-visual-design` antes de definir o design system**: garante um resultado moderno e premium, não genérico.
2. **Verificar contraste WCAG AA de cada par texto/fundo antes de considerar a especificação concluída**: única validação de qualidade que Vitória aplica antes da revisão completa de Rafael.
3. **Documentar a especificação visual seção por seção**, incluindo breakpoints responsivos explícitos.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Fábio Front-end

### Never Do

1. **Animar a Saída Rápida ou adicionar qualquer transição/confirmação antes do redirecionamento**: qualquer atraso perceptível cria uma janela de exposição inaceitável neste domínio.
2. **Usar `window.location.href` em vez de `window.location.replace()` na Saída Rápida**: deixa a página atual no histórico de "voltar" do destino.
3. **Colocar termos explícitos de violência doméstica no `<title>`, meta description ou Open Graph**: aparece no histórico/aba do navegador e no preview de compartilhamento.
4. **Criar um valor de design (cor, fonte, espaçamento) fora da especificação de Vitória "porque parece bom"**: introduz deriva de design fora do controle da fonte de verdade.
5. **Deixar código truncado, com placeholders ou comentários "implementar depois"**: viola a exigência de output completo da skill `full-output-enforcement`.

### Always Do

1. **Implementar a Saída Rápida como componente fixo no layout raiz, com atalho Esc-Esc global**: garante presença em 100% das rotas, não apenas na home.
2. **Carregar a skill `shadcn` ao montar componentes de UI**: garante acessibilidade e consistência visual desde a base.
3. **Verificar `vercel-react-best-practices` e `vercel-composition-patterns` antes de finalizar a arquitetura de componentes**: evita re-trabalho na revisão de Rafael.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Mariana Movimento

### Never Do

1. **Animar a Saída Rápida de qualquer forma (hover, transição de entrada, scroll-reveal)**: regra inegociável — esse é o único ponto do site onde nunca pode haver atraso.
2. **Animar propriedades de layout (`width`, `top`, `margin`) em vez de `transform`/`opacity`**: força recálculo de layout em cada frame, causa jank perceptível em mobile.
3. **Ignorar `prefers-reduced-motion`**: além de falha de acessibilidade, pode causar desconforto real em usuárias já em estado de estresse/ansiedade.
4. **Animar todo elemento da página sem critério**: quando tudo se move, nada se destaca e a página perde sensação de controle para quem usa.

### Always Do

1. **Configurar `MotionConfig reducedMotion="user"` no layout raiz antes de qualquer outra animação**: garante conformidade por padrão em todo o site.
2. **Usar `viewport={{ once: true }}` em todo scroll-reveal**: evita reanimação repetida ao subir/descer a página.
3. **Testar o resultado em dispositivo mobile real**, não apenas desktop — jank é muito mais perceptível em hardware mobile médio.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Rafael Rigor

### Never Do

1. **Aprovar um site com qualquer violação na Saída Rápida, mesmo que isolada**: gatilho de rejeição automática, independente da média geral — mesma regra do Wagner WCAG em `fluxos-uxui-amparo`.
2. **Avaliar performance só em desktop**: a meta de Core Web Vitals é definida para mobile/4G simulado, que é o cenário real de uso em situação de risco.
3. **Aprovar sem carregar a skill `wcag-audit-patterns`**: perde cobertura completa dos critérios POUR.
4. **Dar feedback vago ("melhorar a performance") sem apontar o arquivo/seção exata**: feedback sem localização não é acionável para correção.

### Always Do

1. **Destacar qualquer violação de Saída Rápida no topo do veredito**: mantém a hierarquia de gravidade correta — segurança acima de qualquer outro critério.
2. **Carregar `web-design-guidelines` e `wcag-audit-patterns` antes de iniciar a revisão**: garante rigor além dos critérios já conhecidos pela squad.
3. **Produzir tabela de pontuação por critério + lista de correções específicas por arquivo/seção**: torna o resultado imediatamente acionável para Fábio.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

## Anti-Padrão Transversal Geral da Squad

Nenhum agente desta squad deve inventar conteúdo (funcionalidade do app, token visual, estatística) que não esteja ancorado em uma fonte real (`brainstorm-amparo`, `marca-design-amparo`, `company.md`) ou em pesquisa documentada em `research-brief.md`. Toda ausência de informação deve ser registrada como pendência explícita, nunca resolvida por invenção. E, transversalmente acima de tudo: **a Saída Rápida é um requisito de primeira classe em toda etapa — nunca um extra de acessibilidade.**
