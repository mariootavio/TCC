---
execution: inline
agent: joana-jornada
inputFile: squads/design-ux-ui-amparo/output/design-system.md
outputFile: squads/design-ux-ui-amparo/output/fluxos-ux.md
---

# Step 6: Definir Fluxos de UX

## Context Loading

Load these files before executing:
- `squads/design-ux-ui-amparo/output/design-system.md` — design system aprovado no checkpoint anterior (Step 5)
- `_opensquad/_memory/company.md` — contexto do projeto Amparo
- `squads/design-ux-ui-amparo/pipeline/data/research-brief.md` — pesquisa de UX de segurança/discrição (seção 2) e benchmarking de apps (seção final)
- `squads/design-ux-ui-amparo/pipeline/data/quality-criteria.md` — critérios de qualidade de Joana Jornada
- `squads/design-ux-ui-amparo/agents/joana-jornada/tasks/mapear-arquitetura-informacao.md`
- `squads/design-ux-ui-amparo/agents/joana-jornada/tasks/desenhar-fluxos-ux.md`
- `squads/design-ux-ui-amparo/agents/joana-jornada/tasks/definir-padroes-seguranca-discrecao.md`

## Instructions

### Process

1. Executar a task `mapear-arquitetura-informacao.md`: listar todas as
   funcionalidades centrais (emergência, documentação segura, rede de apoio,
   profissionais, onboarding) e classificá-las em navegação principal vs.
   ações globais.
2. Executar a task `desenhar-fluxos-ux.md`: mapear ponta a ponta as 4 jornadas
   críticas (denúncia/evidência, emergência, modo discreto, rede de apoio),
   incluindo caminho de erro e heurística de Nielsen nomeada em cada decisão.
   Se necessário, usar FigJam (carregando `figma:figma-use-figjam` junto com
   `figma:figma-use`) para diagramar fluxos com múltiplos ramos.
3. Executar a task `definir-padroes-seguranca-discrecao.md`: especificar o
   nível de modo discreto adotado, o mecanismo de saída rápida (1 toque,
   posição consistente, transição instantânea) e a política de notificações
   neutras.
4. Consolidar as 3 tasks em um único documento `output/fluxos-ux.md` e parar
   aqui — o checkpoint seguinte (Step 7) decide se a squad avança para a UI.

## Output Format

The output MUST follow this exact structure:
```markdown
# Fluxos de UX — Amparo

## Arquitetura de Informação
[navegação principal + ações globais]

## Fluxos das Jornadas Críticas
### [Jornada 1: nome]
[passos, heurística nomeada, caminho de erro]
### [Jornada 2: nome]
[...]
(repetir para as 4 jornadas mínimas)

## Padrões de Segurança e Discrição
### Nível de Discrição Adotado
[decisão + justificativa]
### Saída Rápida
[especificação: toques, posição, transição]
### Notificações
[política de conteúdo neutro]

## Próximo Passo
Aguardando aprovação no checkpoint antes de Telma iniciar o desenho visual.
```

## Output Example

```markdown
# Fluxos de UX — Amparo

## Arquitetura de Informação
Navegação principal (bottom nav): Início, Meus Registros, Rede de Apoio, Eu.
Ações globais: Botão de Emergência (cor jade), Botão de Saída Rápida.

## Fluxos das Jornadas Críticas

### Jornada: Registrar Documentação Segura (evidência)
1. Início → "Meus Registros" → "+ Novo Registro"
2. Captura (foto/áudio/texto) local + opção de backup seguro na nuvem (mitiga
   gap de "armazenamento local vulnerável" do benchmarking — bSafe).
3. Confirmação antes de salvar (campo opcional, controle do usuário — Nielsen).
4. "Registro salvo com segurança." Erro sem conexão: salva localmente, nunca
   bloqueia a ação.

### Jornada: Acionar Emergência
1. Toque no botão de emergência (qualquer tela) → tela de confirmação
   (prevenção de erro — Nielsen) → "Confirmar e enviar" → notificação dos
   contatos de confiança + geolocalização.

## Padrões de Segurança e Discrição

### Nível de Discrição Adotado
Discrição em 3 camadas (Safety Net Project): ícone neutro configurável,
notificações sem preview, saída rápida com transição instantânea — sem
disfarce completo de UI (fora do escopo do TCC).

### Saída Rápida
1 toque, canto superior direito, presente em 100% das telas, transição
"Instant" para Tela Neutra (clima fake), remoção do app-switcher.

### Notificações
Conteúdo genérico sempre — nunca expõe o nome "Amparo" ou a ação realizada.

## Próximo Passo
Aguardando aprovação no checkpoint antes de Telma iniciar o desenho visual.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Alguma das 4 jornadas críticas mínimas está ausente ou sem caminho de erro
   documentado.
2. O mecanismo de saída rápida especificado exige mais de 1 toque ou não tem
   posição consistente definida.

## Quality Criteria

- [ ] As 4 jornadas críticas têm fluxo ponta a ponta documentado.
- [ ] Cada fluxo nomeia ao menos uma heurística de Nielsen.
- [ ] O nível de discrição adotado está justificado, não apenas descrito.
- [ ] Nenhuma notificação especificada expõe o nome "Amparo" em preview.
