---
task: "Mapear Arquitetura de Informação"
order: 1
input: |
  - design_system: Design system aprovado (componentes e tokens disponíveis) — squads/design-ux-ui-amparo/output/design-system.md
  - company_context: Contexto do projeto Amparo — _opensquad/_memory/company.md
output: |
  - arquitetura_informacao: Mapa hierárquico das funcionalidades, navegação principal e ações globais — incorporado em squads/design-ux-ui-amparo/output/fluxos-ux.md
---

# Mapear Arquitetura de Informação

Mapeia todas as funcionalidades do Amparo (emergência, documentação segura,
rede de apoio, acesso a profissionais) em uma arquitetura de informação
hierárquica, definindo navegação principal e agrupamento de telas antes de
qualquer fluxo individual ser desenhado.

## Process

1. Carregar o design system aprovado (componentes e tokens disponíveis) e o
   contexto do Amparo — a arquitetura deve ser definida sabendo quais
   componentes existem, não no vácuo.
2. Listar TODAS as funcionalidades centrais do app: emergência, documentação
   segura de evidências, rede de apoio pessoal, acesso a profissionais,
   onboarding. Nenhuma funcionalidade central pode ficar de fora do mapeamento.
3. Classificar cada funcionalidade como navegação principal (bottom nav) ou
   ação secundária/contextual (ação global, acessível de qualquer tela) — com
   critério explícito para a classificação, não por intuição.
4. Definir os itens da navegação principal com rótulos neutros (evitando
   exposição visual do propósito específico, ex.: evitar rótulo "Denunciar" em
   destaque) e as ações globais (ex.: botão de emergência, saída rápida).
5. Documentar a arquitetura completa, incorporando-a ao documento consolidado
   `output/fluxos-ux.md`, antes de iniciar o mapeamento de qualquer fluxo
   individual (próxima task).

## Output Format

```yaml
arquitetura_informacao:
  navegacao_principal:
    - item: "string — rótulo neutro"
      conteudo: "string — o que esta seção agrupa"
  acoes_globais:
    - item: "string"
      acessivel_de: "string — ex. qualquer tela"
      racional: "string"
  funcionalidades_mapeadas: ["string"]
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
ARQUITETURA DE INFORMAÇÃO — AMPARO

NAVEGAÇÃO PRINCIPAL (bottom nav — 4 itens, ícones neutros sem rótulo explícito
como "Denunciar", para reduzir exposição visual no app aberto):
  1. Início (resumo + ação de emergência em destaque)
  2. Meus Registros (documentação segura de evidências)
  3. Rede de Apoio (contatos de confiança + profissionais)
  4. Eu (perfil, configurações de discrição, ajuda)

AÇÃO GLOBAL (acessível de qualquer tela, fora da bottom nav):
  - Botão de Emergência (flutuante, cor jade — não vermelho — ver token
    color-action-emergency do design system)
    Racional: precisa estar acessível em 1 toque de qualquer ponto do app.
  - Botão de Saída Rápida (ver fluxo dedicado na task seguinte)
    Racional: requisito de segurança crítico, não pode depender de navegação.

FUNCIONALIDADES MAPEADAS: emergência, documentação segura, rede de apoio,
acesso a profissionais, onboarding, configurações de discrição.

Próximo passo: mapear os fluxos ponta a ponta das 4 jornadas críticas
(task desenhar-fluxos-ux).
```

## Quality Criteria

- [ ] Todas as funcionalidades centrais do app estão mapeadas e classificadas
      como navegação principal ou ação global/contextual.
- [ ] Nenhum rótulo de navegação principal expõe literalmente o propósito do
      app (ex.: evitar "Denunciar" como rótulo visível em destaque).
- [ ] Toda ação global tem racional explícito de por que precisa estar
      acessível fora da navegação hierárquica.

## Veto Conditions

Reject and redo if ANY are true:
1. Alguma funcionalidade central (emergência, documentação segura, rede de
   apoio, acesso a profissionais) não está mapeada na arquitetura.
2. A navegação principal usa um rótulo que expõe o propósito sensível do app
   de forma literal e visível.
