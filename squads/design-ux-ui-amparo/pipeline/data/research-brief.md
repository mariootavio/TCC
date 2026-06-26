# Research Brief — Squad Design UX/UI Amparo

> Compilado na Fase de Design (Fase B — pesquisa web), a partir do `research_brief`
> consolidado em `squads/design-ux-ui-amparo/_build/design.yaml`. Cobre 5 frentes de
> pesquisa de design e UX/UI aplicadas ao app Amparo, com 2-3 fontes cada.

## Nota sobre Benchmarking de Apps (reaproveitamento, não repesquisa)

O benchmarking de apps similares de proteção contra violência doméstica (PenhaS,
Circle of 6, bSafe, Botão do Pânico estadual) **NÃO foi pesquisado novamente** por
esta squad. Esse levantamento já existia, completo, na squad **tcc-documentacao**,
gerado a partir da pesquisa acadêmica/de mercado feita para a documentação do TCC.

Esta squad de design **reaproveitou** esse benchmarking como insumo direto para as
decisões de UX (gaps de produto → requisitos de fluxo), em vez de rodar uma nova
pesquisa web equivalente. A fonte completa, com tabela comparativa detalhada e fontes
citadas, está em:

```
squads/tcc-documentacao/pipeline/data/research-brief.md
```

Os agentes desta squad (especialmente Joana Jornada, ao desenhar fluxos de UX) devem
referenciar esse documento ao justificar decisões ligadas a gaps de produto — por
exemplo, "armazenamento local vulnerável" (gap do bSafe) e "dependência de
conectividade" (gap comum no setor) foram usados como input direto para os fluxos de
documentação segura de evidências e para o estado de erro "sem conexão".

O resumo dos achados de benchmarking reaproveitados está na seção final deste
documento, mas para o detalhamento completo (fontes, tabela comparativa, dados de
legislação e estatísticas) sempre consultar o arquivo original acima.

---

## 1. Identidade Visual para Marcas Sensíveis (Trauma-Informed Design)

O framework guarda-chuva é o **design trauma-informado** (trauma-informed design):
- Paletas de tons frios e calmantes (azul, verde, lilás) em vez de vermelho/amarelo
  de alta energia, que sinalizam alarme e perigo institucional.
- Simbolismo de proteção e acolhimento — nunca imagética literal de violência
  (punhos, hematomas, grades, sangue), que pode retraumatizar a usuária.
- Restrição de segurança real, não apenas estética: o nome e o ícone do app não
  podem expor visualmente o propósito do aplicativo, pois o agressor pode ter
  acesso ao celular da vítima e ver a tela/ícone a qualquer momento.

**Fontes:** ThinkDesigns LLC; atrainmarketing.com; UX Magazine (artigo sobre
trauma-informed design); Innovation Unit.

## 2. UX de Segurança e Discrição

Referência principal: **Safety Net Project** (techsafety.org), guia "Choosing and
Using Apps: Considerations for Survivors".

Padrões-chave identificados:
- **Disguise/mask mode**: o app se disfarça visualmente como algo neutro (ex.: app
  de notícias, clima, notas).
- **Saída rápida (quick exit)**: deve estar disponível em no máximo 1 toque, a
  partir de qualquer tela do app.
- **Notificações sem preview de conteúdo** na tela de bloqueio — nunca expor o nome
  do app ou o conteúdo da notificação (ex.: "Amparo: denúncia registrada").
- **Minimização de rastro** no histórico do sistema operacional e no app-switcher
  (lista de apps recentes), reduzindo risco de descoberta pelo agressor.

Exemplo real de mercado: **Aspire News App** — disfarce completo como app de
notícias funcional (duas "personas" de UI mantidas simultaneamente).

**Fontes:** techsafety.org/choosingapps; PanicGuard (recurso "Mask Mode");
domesticshelters.org; Malwarebytes Labs (rastro digital).

## 3. Acessibilidade Mobile — WCAG 2.2 AA

Critérios mais relevantes para o Amparo:

| Critério WCAG 2.2 | Exigência |
|---|---|
| 1.4.3 Contraste (mínimo) | 4.5:1 texto normal, 3:1 texto grande/componentes UI |
| 2.5.8 Tamanho do Alvo (mínimo) | 24x24px mínimo para elementos interativos |
| 2.4.11 Foco Não Obscurecido | Estado de foco nunca coberto por outro elemento |
| 2.5.7 Movimentos de Arraste | Toda interação por arrasto precisa de alternativa de toque único |
| 3.2.6 Ajuda Consistente | Posição estável de mecanismos de ajuda/saída entre telas |
| 3.3.7 Entrada Redundante | Evitar pedir a mesma informação mais de uma vez |
| 3.3.8 Autenticação Acessível | Login sem depender exclusivamente de teste cognitivo |

**Fontes:** W3C WCAG 2.2 (especificação oficial); WCAG2Mobile (W3C); TestParty;
Deque Systems.

## 4. Design Systems — Atomic Design e Tokens

Metodologia de Brad Frost: hierarquia **átomo → molécula → organismo → template →
página**. Aplicação de tokens:
- **Tokens primitivos** (ex.: `purple-500`) — valores brutos de cor/espaçamento.
- **Tokens semânticos** (ex.: `color-action-primary`) — referenciam os primitivos
  e carregam significado de uso. Definir tokens ANTES de qualquer componente.
- No Figma: registrar tokens como **Figma Variables**; usar **Variant Properties**
  combinadas com **boolean/instance-swap properties** em vez de variantes
  combinatórias completas (evita explosão de variantes).

**Fontes:** Figma Blog (atomic components); makandra.de; Brad Frost (Design Systems
Q&A); Figma Learn.

## 5. Prototipagem Navegável no Figma

- Separar fluxos por página dentro do arquivo Figma (uma página por jornada/fluxo).
- Usar **overlays** para modais, alertas e confirmações — nunca duplicar telas
  inteiras para representar um estado temporário.
- **Interactive Components** para estados de componente (hover, pressed) definidos
  uma única vez no componente mestre.
- **Smart Animate** para transições com continuidade visual — depende de
  nomenclatura consistente de camadas entre frames de estado equivalente.
- Planejar as interações desde o início de cada fluxo, não como etapa final.
- Testar a navegação completa antes da entrega — sem telas mortas, sem links
  quebrados.

**Fontes:** Figma (High-Fidelity Prototyping); Figma Best Practices (prototyping
workflow); Figma Help Center (Guide to prototyping, Advanced prototyping examples).

---

## Resumo do Benchmarking Reaproveitado (ver fonte completa acima)

| App | Diferencial | Gap conhecido | Uso no design Amparo |
|---|---|---|---|
| PenhaS | Tecnologia + curadoria humana (voluntárias) | Depende de acionamento manual | Reforça necessidade de ação de emergência sempre visível e de 1 toque |
| Circle of 6 | UX de 2 toques, discrição social | Sem integração com legislação brasileira | Inspira meta de baixa fricção nos fluxos críticos |
| bSafe | Evidência forense (vídeo+geo com timestamp) | Armazenamento local vulnerável | Fluxo de documentação segura prevê backup seguro na nuvem desde o início |
| Botão do Pânico estadual | Acionamento direto da PM com geolocalização | Depende de autorização judicial prévia | Reforça que o Amparo precisa de caminho de ação independente de terceiros |

Gaps usados como input direto para os fluxos de Joana Jornada: falta de automação,
dependência de conectividade, armazenamento local vulnerável, medo do agressor
descobrir o app.
