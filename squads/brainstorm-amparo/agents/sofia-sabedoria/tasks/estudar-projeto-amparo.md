---
task: "Estudar Projeto Amparo"
order: 1
input: |
  - foco_brainstorm: Conteúdo de squads/brainstorm-amparo/output/foco-brainstorm.md (área de interesse e recorte definidos pelo usuário no checkpoint)
  - company_context: Contexto do projeto Amparo (_opensquad/_memory/company.md)
output: |
  - funcionalidades_existentes: Lista de funcionalidades já definidas/planejadas no Amparo, com origem (squad/documento)
  - fluxos_ux_existentes: Lista de fluxos de UX já desenhados, se houver squad de design já executada
  - tom_de_voz: Resumo do tom de voz e posicionamento do produto
  - dados_ja_levantados: Dados estatísticos/legais já levantados pela squad tcc-documentacao, reutilizáveis no brief
---

# Estudar Projeto Amparo

Lê toda a documentação interna do projeto disponível — `company.md`, outputs
das squads já executadas (especialmente `tcc-documentacao`), design system e
fluxos já definidos (se existirem) — e extrai um resumo estruturado do estado
atual do produto, suas funcionalidades já definidas/planejadas e seu
posicionamento, para que Bruno Brainstorm nunca proponha algo que já existe.

## Process

1. Reler o foco recebido no checkpoint "Foco do Brainstorm" e reafirmar
   mentalmente o recorte (área de interesse + escopo do benchmarking) antes de
   abrir qualquer arquivo.
2. Ler `_opensquad/_memory/company.md` por completo: problema central, solução,
   público-alvo, tom de voz.
3. Ler `squads/tcc-documentacao/pipeline/data/research-brief.md` e extrair
   dados estatísticos, legislação e benchmarking já levantados — estes serão
   reutilizados no brief final sem repesquisa.
4. Verificar se existem outputs de squads de design/UX (ex.:
   `squads/design-ux-ui-amparo/pipeline/data/*` ou `squads/*/output/`) e, se
   existirem, extrair funcionalidades e fluxos já desenhados.
5. Compilar a lista de funcionalidades já existentes/planejadas, fluxos de UX
   já desenhados, tom de voz, e os dados reutilizáveis — esta lista alimenta
   diretamente a task `compilar-brief-conhecimento.md`.

## Output Format

```yaml
funcionalidades_existentes:
  - nome: "Nome da funcionalidade"
    origem: "Squad ou documento de onde veio"
    descricao: "Breve descrição"
fluxos_ux_existentes:
  - nome: "Nome do fluxo"
    origem: "Squad ou documento de onde veio"
tom_de_voz: "Resumo do tom de voz e posicionamento"
dados_ja_levantados:
  - dado: "Descrição do dado"
    fonte: "Nome da fonte"
    confianca: "ALTA | MÉDIA | BAIXA"
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
CONHECIMENTO INTERNO DO PROJETO — AMPARO

Funcionalidades já definidas (squad design-ux-ui-amparo, se executada;
ou descritas em company.md): botão de emergência com acionamento
discreto, cofre de documentação segura, rede de apoio pessoal
(contatos de confiança), acesso a profissionais (psicólogos/assistência
jurídica parceira).

Fluxos de UX já desenhados: nenhum fluxo de UX detalhado encontrado
além da descrição funcional em company.md — squad de design ainda não
executada nesta instância do projeto.

Tom de voz: acolhedor, empático, seguro e claro — linguagem sensível ao
tema, sem jargão técnico para o público final (fonte: company.md).

Dados já levantados (reutilizáveis, squad tcc-documentacao):
- Subnotificação de 61% dos casos de violência doméstica no Brasil.
  Confiança: ALTA. Fonte: DataSenado.
- Em 2025, 1.568 mulheres foram vítimas de feminicídio no Brasil.
  Confiança: ALTA. Fonte: FBSP.

Implicação: qualquer ideia de Bruno relacionada a botão de emergência,
cofre de documentos ou rede de apoio pessoal precisa ser diferenciada
do que já está descrito como existente, não uma reformulação do mesmo
conceito.
```

## Quality Criteria

- [ ] Toda funcionalidade/fluxo listado tem a origem (squad/documento)
      registrada.
- [ ] Os dados reutilizados da squad tcc-documentacao mantêm a fonte e
      confiança originais, sem alteração.
- [ ] O tom de voz é extraído literalmente de `company.md`, não inventado.

## Veto Conditions

Reject and redo if ANY are true:
1. A lista de funcionalidades existentes foi compilada sem consultar
   `company.md` ou os outputs de squads relevantes.
2. Um dado da squad tcc-documentacao foi reportado com fonte ou confiança
   diferente da original.
