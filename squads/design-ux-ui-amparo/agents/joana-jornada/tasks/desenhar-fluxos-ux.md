---
task: "Desenhar Fluxos de UX"
order: 2
input: |
  - arquitetura_informacao: Arquitetura de informação mapeada na task anterior — incorporada em squads/design-ux-ui-amparo/output/fluxos-ux.md
  - design_system: Design system aprovado — squads/design-ux-ui-amparo/output/design-system.md
output: |
  - fluxos_ux: Fluxos ponta a ponta das jornadas críticas, com pontos de decisão, estados de erro e heurísticas nomeadas — incorporado em squads/design-ux-ui-amparo/output/fluxos-ux.md
---

# Desenhar Fluxos de UX

Desenha os fluxos de usuário ponta a ponta para as jornadas críticas
(registrar denúncia/evidência, acionar emergência, ativar modo discreto,
contatar rede de apoio), documentando decisões e pontos de fricção
intencionais/evitáveis, sempre em texto/diagrama antes de qualquer wireframe.

## Process

1. Carregar a arquitetura de informação já mapeada e o design system aprovado
   — os fluxos usam os componentes que já existem, nunca inventam novos.
2. Para cada uma das 4 jornadas críticas mínimas (denúncia/evidência,
   emergência, modo discreto, rede de apoio), mapear o fluxo ponta a ponta:
   listar cada tela, decisão e possível ponto de saída, em texto/diagrama —
   nunca direto em wireframe visual.
3. Se algum fluxo tiver múltiplos ramos complexos que se beneficiem de
   visualização, invocar a skill `figma:figma-use-figjam` junto com
   `figma:figma-use` antes de qualquer chamada de ferramenta no contexto
   FigJam, e diagramar lá.
4. Aplicar pelo menos uma heurística de usabilidade de Nielsen a cada fluxo
   (visibilidade do status, controle e liberdade do usuário, prevenção de
   erros, reconhecimento em vez de memorização), nomeando-a explicitamente —
   com atenção especial a "prevenção de erros" em ações irreversíveis.
5. Mapear o caminho de erro/exceção de cada fluxo crítico (não só o caminho
   feliz) — ex.: sem conexão, denúncia incompleta — e verificar contra
   critérios de acessibilidade aplicáveis (WCAG 3.2.6, 2.5.8).
6. Documentar cada fluxo com pontos de decisão, estados de erro e o racional
   por trás de cada escolha, incorporando ao `output/fluxos-ux.md`.

## Output Format

```yaml
fluxos_ux:
  - jornada: "string — ex. registrar documentação segura"
    passos:
      - numero: 1
        tela: "string"
        acao: "string"
        heuristica_aplicada: "string"
    caminho_erro:
      condicao: "string — ex. sem conexão"
      comportamento: "string"
    confirmacao_irreversivel: true | false
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
FLUXO — REGISTRAR DOCUMENTAÇÃO SEGURA (evidência)

1. Início → "Meus Registros" → "+ Novo Registro"
2. Tela de captura: Foto / Áudio / Texto livre — captura local primeiro, com
   opção explícita de "Salvar com backup seguro na nuvem" (mitigando o gap de
   "armazenamento local vulnerável" do benchmarking — bSafe).
   Heurística aplicada: prevenção de erros (Nielsen).
3. Tela de confirmação ANTES de salvar: resumo do capturado + pergunta sobre
   data/local/descrição (campo opcional, nunca obrigatório — controle e
   liberdade do usuário, Nielsen).
4. Confirmação final: "Registro salvo com segurança." (linguagem neutra, sem
   ícone de "sucesso" festivo).
5. Estado de erro (sem conexão): "Registro salvo localmente. Será
   sincronizado quando você tiver conexão." — nunca bloquear por falta de
   internet (gap conhecido de soluções concorrentes, do benchmarking).

Confirmação em ação irreversível: N/A para este fluxo (registro pode ser
editado depois); aplicável no fluxo de emergência e exclusão de registro.
```

## Quality Criteria

- [ ] As 4 jornadas críticas mínimas têm fluxo ponta a ponta documentado,
      incluindo caminho de erro.
- [ ] Cada fluxo cita ao menos uma heurística de Nielsen nomeada
      explicitamente.
- [ ] Toda ação irreversível identificada no fluxo tem etapa de confirmação
      explícita documentada.

## Veto Conditions

Reject and redo if ANY are true:
1. Algum fluxo crítico mapeia apenas o caminho feliz, sem caminho de erro/
   exceção.
2. Algum fluxo é desenhado direto como wireframe visual antes de existir
   documentação em texto/diagrama do fluxo completo.
