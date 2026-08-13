==============================
 VEREDITO DA REVISÃO DE DESIGN: APROVAR COM RESSALVAS
==============================

Escopo revisado: 100% das 18 telas de Telma + 3 telas neutras locais de
Pietro (21 frames) em 6 páginas de fluxo, + 100% das conexões do protótipo
navegável (`prototipo-navegavel.md`), + o design system de Caio
(`design-system-figma.md`, 37 variáveis, 6 text styles, 1 effect style, 4
componentes). Skill `wcag-audit-patterns` carregado (princípios POUR).

------------------------------
 VERIFICAÇÃO DE SEGURANÇA/DISCRIÇÃO (Daniela Discrição) — SEM VIOLAÇÕES
------------------------------
- **Saída rápida**: posição fixa (canto superior direito, mesmo padding
  16px) em 100% das 15 telas onde aparece (Fluxos 1, 2, 4, 5, 6). Transição
  `null` (instantânea) confirmada nas 15 ocorrências via
  `prototipo-navegavel.md` — nenhuma exceção encontrada.
- **Modo disfarçado**: calculadora funcional (não apenas fachada), destrave
  por código numérico documentado com falha silenciosa (nenhuma mensagem de
  erro visível na tela "Calculadora — Ativa"). Conforme.
- **Notificações neutras**: "Rede de Apoio / Confirmação de Alerta —
  Padrão" usa título genérico "Você tem uma atualização" — não expõe nome
  de guardiã nem conteúdo do alerta. "Início / Nível MÉDIO" reutiliza o
  mesmo texto genérico. Conforme.
- **Minimização de rastro**: "Disfarce / App Switcher — Rastro Minimizado"
  mostra apenas o disfarce (ícone + "Calculadora"), nunca conteúdo real do
  Amparo. Conforme.

Nenhum gatilho de rejeição automática identificado.

------------------------------
 TABELA DE PONTUAÇÃO POR CRITÉRIO
------------------------------
| Critério | Cobertura avaliada | Status |
|---|---|---|
| Padrões de segurança/discrição (Daniela) | 100% das 21 telas | OK — ver seção acima |
| Consistência com design system (Caio) | 100% das telas | RESSALVA — ver correções 3-4 |
| WCAG 2.2 AA — Contraste 1.4.3 (texto) | 100% dos pares texto/fundo usados | FALHA — ver correção 1 |
| WCAG 2.2 AA — Contraste não-textual 1.4.11 | Ícone de saída rápida | FALHA — ver correção 2 |
| WCAG 2.2 AA — Touch target 2.5.8 | 100% dos elementos interativos | OK — menor elemento (chip de saída) mede 32×32px, acima do mínimo 24×24px |
| WCAG 2.2 AA — Ajuda consistente 3.2.6 | Posição da saída rápida entre telas | OK — idêntica nas 15 ocorrências |
| Auditoria POUR completa (wcag-audit-patterns) | 100% das telas | RESSALVA — ver correção 5 (Robust) |
| Heurísticas de Nielsen (Joana) | 6 fluxos | OK — feedback de status (H1), reconhecimento (H6) e prevenção silenciosa de erro (H9 invertida) corretamente refletidos nas telas correspondentes |
| Integridade do protótipo (Pietro) | 100% das 21 telas / todas as conexões | OK — nenhuma tela morta; 3 cross-page notes documentadas como limitação de plataforma, não como falha |

------------------------------
 CORREÇÕES ESPECÍFICAS OBRIGATÓRIAS
------------------------------

1. **[BLOQUEANTE] WCAG 1.4.3 — `color/text/muted` (#8E8984, "Cinza
   Silêncio") não atende contraste mínimo em nenhum uso real do protótipo:**
   - Sobre `color/bg/screen` (#F2EAE4): **2.91:1** — nem atinge o piso de
     3:1 para texto grande. Ocorre no parágrafo de introdução de
     "Emergência / Acionamento — Padrão" ("Toque no botão abaixo...").
   - Sobre `color/bg/surface` (branco, dentro de cards): **3.46:1** — abaixo
     de 4.5:1 exigido para texto normal (todo corpo de card usa 13-14px,
     que não se qualifica como "texto grande"). Afeta o corpo de
     praticamente todo card de status nas 6 páginas de fluxo (ex.: "Sua
     localização foi compartilhada...", "3 ocorrências registradas",
     "Sincronizado com armazenamento seguro...", e assim por diante).
   - Correção: este é o mesmo problema já reportado por Caio em
     `design-system-figma.md` (Step 2) como discrepância de marca — agora
     confirmado como um problema real e generalizado, não teórico. Requer
     decisão da squad `marca-design-amparo`: escurecer o token `Cinza
     Silêncio` ou criar um token secundário mais escuro para texto de apoio
     (`color/text/muted` atual deve ser reservado a elementos não-textuais
     ou textos ≥24px).

2. **[BLOQUEANTE] WCAG 1.4.11 — Ícone de saída rápida (placeholder X) sobre
   `color/bg/screen`: 2.91:1** — abaixo do mínimo 3:1 para componentes de
   UI/objetos gráficos. Ocorre nas 15 telas onde a saída rápida aparece.
   Correção: usar `color/text/body` (#333333, 10.63:1) ou um token
   dedicado, nunca `color/text/muted`, para o ícone de saída rápida —
   elemento crítico de segurança não pode depender de uma cor que falha
   contraste.

3. **[RESSALVA] Navegação principal (bottom nav) ausente em 100% das
   telas.** `arquitetura-informacao.md` (Iara) define 5 itens de bottom nav
   (Início, Documentação, Rede de Apoio, Chat de Apoio, Mais), mas nenhuma
   das 18 telas de Telma os exibe — já registrado como pendência de
   componente para Caio em `telas-alta-fidelidade.md`, e confirmado aqui
   como afetando a completude visual de toda tela de navegação principal
   (Documentação/Início, Rede de Apoio/Lista, Início dos 3 níveis de risco).
   Não bloqueante porque depende de um componente que ainda não existe, mas
   deve ser resolvido antes de considerar o protótipo pronto para testes de
   usuário reais.

4. **[RESSALVA] Anotação "PENDÊNCIA PARA CAIO" visível dentro do frame
   "Delegacias / Lista — Padrão"**: o texto de pendência foi desenhado como
   um card dentro da própria tela (visível como se fosse conteúdo real do
   produto), em vez de ficar apenas na documentação de Telma. Correção:
   mover a anotação para fora da área de conteúdo do frame (ex: como nota
   Figma anexada, ou removê-la do frame e mantê-la só em
   `telas-alta-fidelidade.md`), para que a tela não seja confundida com
   produto final ao ser exportada ou compartilhada isoladamente.

5. **[RESSALVA] POUR "Robust" — ícone de saída rápida é puramente gráfico,
   sem rótulo de texto (removido na passada de refinamento visual desta
   sessão em troca do ícone vetorial)**: em uma implementação real (fora do
   Figma), este elemento precisa de um rótulo acessível para leitores de
   tela (ex.: `aria-label="Sair rapidamente"` ou equivalente em React
   Native `accessibilityLabel`). Registrar como requisito não funcional
   para a squad de desenvolvimento — não é um problema do arquivo Figma em
   si, mas deve estar documentado antes da implementação.

------------------------------
 OBSERVAÇÃO SOBRE A REVISÃO DE ESCOPO EM TEMPO REAL (Step 6)
------------------------------
Os Fluxos 5 (pipeline RF-CORE-06) e 6 (Delegacias Próximas) foram
adicionados durante o checkpoint de aprovação, por decisão explícita do
usuário — Fluxo 6 promovido de "Trabalhos Futuros" da apresentação do TCC.
Ambos foram revisados com o mesmo rigor dos 4 fluxos originais; nenhum
tratamento diferenciado foi aplicado.

==============================
VEREDITO GERAL: APROVAR COM RESSALVAS
==============================
Nenhuma violação de segurança/discrição foi encontrada — todos os padrões
de Daniela Discrição foram confirmados conformes em 100% das telas e do
protótipo. As 2 correções bloqueantes (1 e 2) têm a mesma causa raiz (token
`color/text/muted` insuficiente) e devem ser resolvidas pela squad
`marca-design-amparo` antes de qualquer teste com usuárias reais — mas não
exigem retorno ao Step 7, pois a correção é uma troca de token, não uma
mudança estrutural de tela. As ressalvas 3-5 podem ser resolvidas em
paralelo, sem bloquear a entrega desta rodada.

------------------------------
 CORREÇÕES 1 E 2 APLICADAS (checkpoint Step 10, 2026-08-13)
------------------------------
Por decisão explícita do usuário no checkpoint Step 10, as duas correções
bloqueantes foram resolvidas nesta mesma rodada, sem retorno ao Step 7:
- `color/cinza-silencio` (primitiva) atualizado de `#8E8984` para
  `#6D6966` — mesma família de cinza quente, agora com 5.44:1 sobre branco
  e 4.57:1 sobre `bg/screen`, ambos acima do mínimo 4.5:1. Propagado
  automaticamente a todo uso de `color/text/muted` e `color/border/default`
  nas 6 páginas (era uma Variable, não um valor solto).
- Ícone de saída rápida: recor de hex fixo `#8E8984` (nunca vinculado a
  variável) para `color/text/body` (#333333, vinculado como Variable) nas
  15 ocorrências across 5 páginas — 10.63:1 de contraste.

Ambas as correções verificadas visualmente via screenshot após aplicação.
Nenhuma pendência bloqueante remanescente.
