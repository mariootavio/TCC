# Anti-Patterns — Marca & Design System Amparo

> Compilação dos `Anti-Patterns` (Never Do / Always Do) de cada agente
> desta squad. Lista consolidada de erros de domínio a evitar e práticas a
> sempre seguir, específicas da criação de identidade visual e design
> system para um app de proteção contra violência doméstica, publicado
> inteiramente no Claude Design.

## Renata Referência — Pesquisa de Cor e Público

### Nunca Fazer
- Recomendar cor/simbolismo sem fonte nomeada e nível de confiança
  atribuído: transforma pesquisa em opinião disfarçada — quebra o padrão
  de rastreabilidade que a banca acadêmica vai exigir.
- Tratar a literatura internacional de psicologia das cores como
  diretamente aplicável ao público brasileiro sem ressalva: ignora o gap
  de sub-representação racial já identificado pela squad-irmã.
- Inventar ou supor um exemplo de benchmarking sem verificar a fonte: um
  exemplo fictício apresentado como real compromete a credibilidade de
  toda a pesquisa perante a banca.
- Decidir a identidade final em vez de entregar recomendação: usurpa o
  papel de Flávia Fonte e quebra a separação de responsabilidades da
  squad.

### Sempre Fazer
- Calibrar toda recomendação à demografia real do Amparo (mulheres negras,
  18-44 anos, agressão majoritariamente doméstica).
- Marcar explicitamente cada gap de aplicabilidade racial/cultural.
- Reaproveitar achados já confirmados no research-brief da squad e da
  squad tcc-documentacao em vez de repesquisar.

## Flávia Fonte — Identidade Visual

### Nunca Fazer
- Usar imagética literal de violência (punhos, hematomas, grades, sangue)
  no logo ou em ícones: gera alarmismo visual, pode retraumatizar a
  usuária e expõe o propósito do app caso a tela seja vista pelo
  agressor.
- Usar vermelho/laranja saturado como cor dominante de marca: associado a
  "alarme/perigo institucional" — o objetivo do Amparo é acolhimento.
- Hardcodar um valor de cor/tipografia sem registrar como especificação
  nomeada: quebra a fonte única de verdade que Tomás vai herdar.
- Apresentar uma única direção fechada para aprovação: o checkpoint
  precisa de 2-3 alternativas reais para a aprovação ser uma escolha
  informada.
- Forçar um visual mode pré-definido do brandkit sem adaptação: nenhum
  modo foi desenhado para proteção trauma-informada — usar sem adaptar
  produz uma identidade genérica e incoerente.

### Sempre Fazer
- Verificar contraste WCAG AA antes de fixar qualquer combinação na
  paleta final.
- Conferir se já existe um projeto no Claude Design via `list_projects`
  antes de `create_project`.
- Documentar a justificativa de cada escolha visual ligada ao brief E à
  pesquisa de Renata.

## Tomás Tokens — Design System

### Nunca Fazer
- Criar um componente antes de o token correspondente existir: inverte a
  ordem fundação→construção e gera retrabalho.
- Hardcodar qualquer valor de cor, tipografia ou espaçamento em um
  componente: quebra a fonte única de verdade do design system.
- Criar um segundo projeto no Claude Design em vez de localizar o
  existente: fragmenta a documentação da marca em dois lugares
  diferentes.
- Reinterpretar ou alterar uma decisão de cor/tipografia já aprovada na
  identidade visual: não é papel de Tomás revisar a marca.

### Sempre Fazer
- Verificar contraste WCAG AA em todo par semântico de texto/fundo antes
  de fixar o token.
- Nomear componentes de forma atômica e consistente (ex.
  `Atoms/Button/Primary`).
- Restringir a paleta final a no máximo 5-6 cores-base.

## Marina Marca — Revisão Estruturada

### Nunca Fazer
- Aprovar sem revisar 100% das direções e componentes: avaliação por
  amostragem pode deixar passar exatamente o problema crítico de
  discrição.
- Aceitar o contraste documentado por Tomás sem recalcular: Marina é a
  última camada de checagem antes da squad fluxos-uxui-amparo herdar este
  trabalho.
- Tratar violação de discrição/trauma-informado como nota "compensável"
  pela média: é gatilho de rejeição automática, sempre.
- Dar feedback genérico sem apontar frame/seção/página exata: toda nota
  que não é máxima precisa de localização específica e correção
  acionável.

### Sempre Fazer
- Verificar conformidade trauma-informada como prioridade número um.
- Incluir pelo menos um "Ponto forte:" com exemplo concreto, mesmo em
  revisões com veredito REJEITAR.
- Indicar a localização exata em toda correção apontada.

## Anti-Padrão Transversal de Domínio (de research-brief.md)

- Nunca tratar a discrição visual como preferência estética: é requisito
  de segurança real, decisões erradas aqui têm consequência para a vida
  da usuária, não apenas para a estética do produto.
- Nunca duplicar o projeto Claude Design da squad: toda a documentação de
  marca e design system deve viver em um único projeto coerente, fonte
  única de verdade para a squad `fluxos-uxui-amparo` reconstruir no Figma.
