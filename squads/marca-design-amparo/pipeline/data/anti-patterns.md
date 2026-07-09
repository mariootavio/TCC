# Anti-Patterns — Extensão de Marca & Design System Amparo

> Compilação dos `Anti-Patterns` (Never Do / Always Do) de cada agente
> desta squad reformulada. Lista consolidada de erros de domínio a evitar
> e práticas a sempre seguir, específicas de estender (nunca alterar) um
> design system e manual de marca já finalizados.

## Anti-Padrão Transversal Máximo — Alterar o Design System Aprovado

Nunca, em nenhuma etapa, gerar, propor ou sugerir uma cor, fonte,
espaçamento, logotipo, ícone ou tom de voz diferente do fixado em
`brand/design-system.md`, `brand/LogoAmparo.svg` e `brand/manual-amparo.pdf`
— mesmo como "alternativa para comparação". Nunca editar, mover ou apagar
um componente, token, página do manual ou frame do Figma que já existia
antes do ciclo atual — todo trabalho desta squad é aditivo.

## Flávia Fonte — Especificação de Conceito & Prompts

### Nunca Fazer

- Propor uma cor, fonte, espaçamento ou logotipo diferente do documentado
  em `brand/design-system.md`.
- Recriar um componente/página/regra que já existe, sem verificar
  duplicidade primeiro.
- Gerar prompt de imagem com imagética literal de violência, alarme
  dominante, ou que exponha o propósito do app.
- Deixar o roteamento do output (só prompt vs. segue para Figma)
  implícito.

### Sempre Fazer

- Carregar `brand/design-system.md`, `brand/LogoAmparo.svg` e
  `brand/manual-amparo.pdf` por completo antes de especificar qualquer
  coisa.
- Citar a origem exata (seção/hex/nome) de todo valor reaproveitado.
- Verificar duplicidade antes de propor algo novo.

## Tomás Tokens — Implementação em Figma (MCP)

### Nunca Fazer

- Criar um token, cor, fonte ou estilo novo no Figma.
- Editar, mover ou apagar um componente/frame já existente.
- Criar um arquivo/projeto Figma novo sem confirmação explícita do
  usuário.
- Chamar `use_figma` sem antes carregar a skill `figma-use`.
- Forçar uma implementação quando o roteamento não pediu isso.

### Sempre Fazer

- Localizar o arquivo Figma correto antes de criar qualquer coisa,
  confirmando com o usuário se não estiver óbvio.
- Nomear com nomenclatura atômica consistente com o padrão já usado no
  arquivo.
- Documentar a origem exata de cada token/valor usado na implementação.

## Marina Marca — Auditoria de Fidelidade

### Nunca Fazer

- Aprovar sem revisar 100% do material do ciclo.
- Aceitar a checagem de duplicidade de Flávia sem confirmar de forma
  independente.
- Tratar alteração de algo pré-existente como nota "compensável" pela
  média — é gatilho de rejeição automática, sempre.
- Dar feedback genérico sem apontar localização exata.

### Sempre Fazer

- Verificar fidelidade de tokens e integridade do que já existia como
  prioridade número um.
- Incluir pelo menos um "Ponto forte:", mesmo em veredito REJEITAR.
- Indicar a localização exata em toda correção apontada.

## Helena Manual — Documentação de Extensões

### Nunca Fazer

- Editar `brand/manual-amparo.pdf` ou `brand/design-system.md`
  diretamente.
- Documentar como definitivo algo que Marina reprovou ou marcou como
  pendente de correção sem confirmação.
- Despejar a especificação inteira de Flávia sem curadoria.
- Usar frase genérica não-quantificada (ex. "cores harmoniosas", "use com
  moderação").

### Sempre Fazer

- Confirmar veredito de Marina antes de documentar qualquer entrada como
  definitiva.
- Datar e citar o pedido original em toda entrada.
- Anexar ao final do apêndice, nunca reescrever entradas anteriores.

## Anti-Padrão Transversal de Domínio

- Nunca tratar a discrição visual como preferência estética: é requisito
  de segurança real, decisões erradas aqui têm consequência para a vida da
  usuária, não apenas para a estética do produto.
- Nunca confundir "extensão" com "alteração": se um pedido do usuário
  parecer pedir uma mudança em algo já existente (ex. "muda a cor do botão
  primário"), isso está fora do escopo desta squad — sinalizar
  explicitamente em vez de executar.
- Nunca duplicar o arquivo Figma do produto: toda implementação usa o
  arquivo já existente, construído pela squad `fluxos-uxui-amparo`.
