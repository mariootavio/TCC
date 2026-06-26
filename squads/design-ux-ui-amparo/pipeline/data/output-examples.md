# Output Examples — Design UX/UI Amparo

> Compilação dos `output_examples` de cada agente em `design.yaml`. Servem como
> referência de qualidade e profundidade esperada — não como template rígido.

## Flávia Fonte — Identidade Visual e Design System

### Exemplo 1: Apresentação de identidade visual de marca para aprovação (3 direções)

```
IDENTIDADE VISUAL — AMPARO
Brief de origem: acolhedor, seguro, discreto (adjetivos do checkpoint)
Preparado em: 2026-06-26
Arquivo Figma: Amparo — Marca & Design System (página "01. Identidade Visual")

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

DIREÇÃO 1 — "Porto Seguro" (recomendada)

Logo: monograma circular com a letra "A" estilizada formando duas mãos
curvas e abstratas que se encontram — sem dedos, sem realismo, apenas
forma geométrica suave. Não remete a "ajuda" de forma óbvia para quem
olha de relance a tela de um celular.

Paleta:
  Primária:    #5B6B8C (azul-ardósia — calma, segurança, autoridade suave)
  Secundária:  #8B7FB8 (lilás suave — acolhimento, sem ser "cor de ONG óbvia")
  Acento:      #2D9D8F (verde-jade — ação positiva, usado só em CTAs de progresso)
  Neutro escuro: #2B2D3A (texto principal)
  Neutro claro:  #F4F2F7 (fundo)

Tipografia de marca: 'Source Sans 3' (humanista, alta legibilidade,
sem serifa decorativa — não parece institucional/burocrática nem infantil).

Justificativa: tons frios (azul-ardósia + lilás) seguem o princípio de
design trauma-informado de reduzir ansiedade visual, em contraste com o
vermelho/laranja que o benchmarking (research-brief.md) associa a apps
de "alarme" institucionais (Botão do Pânico estadual). O monograma não
contém nenhum símbolo "óbvio" de violência ou socorro (sem escudo, sem
cruz, sem punho), reduzindo risco caso o agressor veja o ícone do app.

DIREÇÃO 2 — "Abrigo"
[paleta em tons terrosos + verde-oliva, logo com forma de folha abstrata]
Mais "natural/orgânico", porém com risco de parecer app de bem-estar
genérico e diluir a identidade própria do Amparo.

DIREÇÃO 3 — "Constância"
[paleta azul-petróleo + dourado discreto, logo com padrão de ondas]
Transmite estabilidade, porém o dourado pode ler como "premium/financeiro"
e desviar do tom acolhedor pedido no brief.

RECOMENDAÇÃO: Direção 1 ("Porto Seguro") por atender simultaneamente aos
3 adjetivos do brief (acolhedor, seguro, discreto) e ao requisito de
segurança de não expor o propósito do app visualmente.

Próximo passo: aguardando aprovação no checkpoint antes de prosseguir
para o design system completo.
```

### Exemplo 2: Entrega de design system (tokens + componentes) após identidade aprovada

```
DESIGN SYSTEM — AMPARO
Base: Identidade Visual "Porto Seguro" (aprovada em checkpoint)
Arquivo Figma: Amparo — Marca & Design System (página "02. Design System")
Metodologia: Atomic Design + Figma Variables

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

TOKENS PRIMITIVOS (Figma Variables — coleção "primitives")
  slate-50 a slate-900, lilac-50 a lilac-900, jade-50 a jade-900
  spacing-1 a spacing-8 (4px a 64px), radius-sm/md/lg (8/16/24px)

TOKENS SEMÂNTICOS (coleção "semantic", referenciando "primitives")
  color-bg-default → slate-50 | color-bg-discrete → lilac-50
  color-action-primary → slate-600
  color-action-emergency → jade-700 (verde, não vermelho)
  color-text-primary → slate-900 | color-text-muted → slate-500
  color-border → slate-200

COMPONENTES (atomic hierarchy)
  Átomos: Button (primary/secondary/ghost/emergency × sm/md/lg), Input/Text,
          Icon (24x24), Tag, Avatar
  Moléculas: Form-Field, List-Item, Alert-Banner, Search-Bar
  Organismos: App-Header, Bottom-Nav, Report-Card, Contact-Card,
              Emergency-Action-Sheet

Touch targets: mínimo 24x24px (WCAG 2.5.8); Button "sm" com área de toque
mínima de 44x44px via padding invisível.

Próximo passo: aguardando aprovação no checkpoint antes de Joana iniciar
o desenho dos fluxos de UX sobre estes componentes.
```

## Joana Jornada — Arquitetura de Informação e Fluxos de UX

### Exemplo 1: Fluxo de UX para ativação de modo discreto e saída rápida

```
FLUXO DE UX — MODO DISCRETO E SAÍDA RÁPIDA
Jornada crítica: usuária precisa esconder o uso do app a qualquer momento

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

DECISÃO DE ARQUITETURA: discrição em 3 camadas (não disfarce total de app):
  1. Ícone neutro na tela inicial (nome configurável, não "Amparo")
  2. Notificações push sem preview de conteúdo
  3. Gesto de saída rápida em qualquer tela (canto superior direito, ícone
     neutro, touch target 44x44px) → transição "Instant" para Tela Neutra
     (clima fake funcional) → remoção do app-switcher do sistema

PONTOS DE DECISÃO E RACIONAL DE SEGURANÇA: por que não simular um app
completo (como Aspire News)? Exigiria testes extensivos com sobreviventes,
fora do escopo do TCC. Por que posição fixa do botão de saída? WCAG 3.2.6
exige consistência para mecanismos de ajuda/saída.

Próximo passo: aguardando aprovação no checkpoint antes de Telma iniciar
o desenho visual deste fluxo.
```

### Exemplo 2: Arquitetura de informação e fluxo de registro de denúncia/evidência

```
ARQUITETURA DE INFORMAÇÃO — AMPARO

NAVEGAÇÃO PRINCIPAL (bottom nav, ícones neutros): Início | Meus Registros |
Rede de Apoio | Eu. AÇÃO GLOBAL: Botão de Emergência (cor jade) + Saída Rápida.

FLUXO — REGISTRAR DOCUMENTAÇÃO SEGURA (evidência)
1. Início → "Meus Registros" → "+ Novo Registro"
2. Captura local primeiro, com opção de backup seguro na nuvem (mitiga gap
   de "armazenamento local vulnerável" do bSafe, do benchmarking)
3. Confirmação antes de salvar, campos opcionais (nunca obrigatórios)
4. "Registro salvo com segurança." (tom acolhedor, não celebratório)
5. Erro sem conexão: "Registro salvo localmente. Será sincronizado quando
   você tiver conexão." — nunca bloquear por falta de internet

Próximo passo: aguardando aprovação no checkpoint.
```

## Telma Tela — Telas de Alta Fidelidade e Protótipo Navegável

### Exemplo 1: Especificação de tela de alta fidelidade — Tela de Emergência

```
TELA DE ALTA FIDELIDADE — AÇÃO DE EMERGÊNCIA
Página Figma: "04. Fluxo de Denúncia" / Frame: "Emergência - Confirmação"
Componentes usados: Button/Emergency/Large, Alert-Banner, App-Header —
todos do design system aprovado.

Layout (mobile, 390x844pt): App-Header com saída rápida (posição idêntica
em todas as 18 telas); título "Pedir ajuda agora"; Alert-Banner cor
color-action-emergency (jade-700); Button "Confirmar e enviar" (touch
target 56x56px, contraste 8.1:1); link "Cancelar" (44x44px).

Estado de confirmação (prevenção de erro de Nielsen): existe para que o
toque no botão de emergência da Tela Início não dispare a ação imediata.

Anotação de protótipo: conecta para "Emergência - Enviada" (300ms,
ease-out) ou de volta para "Início" via "Cancelar".
```

### Exemplo 2: Especificação do protótipo navegável — conexões do modo discreto

```
PROTÓTIPO NAVEGÁVEL — MODO DISCRETO E SAÍDA RÁPIDA

[Qualquer tela] --saída rápida (presente em 22 frames)--> [Tela Neutra]
  Transição: "Instant" (decisão deliberada — sem atraso perceptível)

[Tela Neutra] --toque longo (1.5s) no ícone do sol--> [Tela Início]
  Transição: "Smart Animate" (200ms) — aceitável pois é gesto intencional

[Lista de Registros] --"+ Novo Registro"--> [Modal: Escolher tipo de captura]
  Tipo: Overlay (não tela nova)

Verificação: todos os 22 frames com entrada e saída; testado o caminho de
saída rápida a partir de cada frame — nenhuma tela morta. Nomenclatura de
frames consistente para Smart Animate (ex.: "Modal-Captura").
```

## Wagner WCAG — Revisão Estruturada

### Exemplo 1: Revisão com veredito APROVAR

```
==============================
 VEREDITO DA REVISÃO: APROVAR
==============================
Revisão: 1 de 3

| Critério                          | Nota  | Resumo |
|------------------------------------|-------|--------|
| Consistência com design system     | 9/10  | Zero estilo ad-hoc detectado |
| Acessibilidade WCAG 2.2 AA          | 8/10  | 1 frame com foco obscurecido |
| Heurísticas de usabilidade (Nielsen)| 9/10  | Confirmação em todas as ações irreversíveis |
| Aderência à marca / tom acolhedor   | 9/10  | Linguagem consistente |
| Integridade do protótipo navegável  | 8/10  | 1 conexão com transição incorreta |
| Padrões de segurança/discrição      | 10/10 | Saída rápida consistente em 100% das telas |
MÉDIA GERAL: 8.8/10

Ponto forte: saída rápida na posição idêntica nas 22 telas, transição
"Instant" sem animação — requisito de segurança cumprido integralmente.

Sugestão (não-bloqueante): ajustar z-index do header em "Lista de
Registros" para não obscurecer o foco do campo de busca (WCAG 2.4.11).

VEREDITO: APROVAR — todos os critérios ≥7/10, nenhum gatilho violado.
```

### Exemplo 2: Revisão com veredito REJEITAR (gatilho de segurança)

```
==============================
 VEREDITO DA REVISÃO: REJEITAR
==============================
Revisão: 1 de 3

| Critério                          | Nota  | Resumo |
|------------------------------------|-------|--------|
| Padrões de segurança/discrição      | 3/10  | Saída rápida ausente em 4 das 22 telas |
MÉDIA GERAL: 6.5/10

GATILHO DE REJEIÇÃO AUTOMÁTICA: Padrões de segurança/discrição pontuou
3/10 — rejeição obrigatória independente da média geral.

Correção obrigatória: adicionar o componente App-Header (contém o botão
de saída rápida) aos frames "Modal-Captura", "Modal-Confirmação-Denúncia",
"Tela de Contato-Profissional" e "Tela de Erro-Conexão".

Ponto forte: a Tela Neutra de saída rápida está bem executada nas telas
em que o botão está presente.

CAMINHO PARA APROVAÇÃO: 1) Adicionar saída rápida aos 4 frames. 2)
Ajustar touch target dos botões "Editar"/"Excluir". 3) Adicionar overlay
de confirmação antes de excluir registro. 4) Conectar tela morta de Rede
de Apoio. 5) Resubmeter como Revisão 2.

VEREDITO: REJEITAR — gatilho de segurança automático.
```
