# Research Brief — Squad Marca & Design System Amparo

> Reaproveitado integralmente das seções 1 e 4 do research-brief da squad
> `design-ux-ui-amparo` (em processo de descontinuação/divisão), que já
> cobriam identidade visual trauma-informada e design systems — diretamente
> relevantes aos agentes desta squad (Renata, Flávia, Tomás, Marina). Fonte
> e formato mantidos sem alteração de conteúdo original.

## 1. Identidade Visual para Marcas Sensíveis (Trauma-Informed Design)

O framework guarda-chuva é o **design trauma-informado** (trauma-informed design):
- Paletas de tons frios e calmantes (azul, verde, lilás) em vez de vermelho/amarelo
  de alta energia, que sinalizam alarme e perigo institucional.
- Simbolismo de proteção e acolhimento — nunca imagética literal de violência
  (punhos, hematomas, grades, sangue), que pode retraumatizar a usuária.
- Restrição de segurança real, não apenas estética: o nome e o ícone do app não
  podem expor visualmente o propósito do aplicativo, pois o agressor pode ter
  acesso ao celular da vítima e ver a tela/ícone a qualquer momento.

Fontes: ThinkDesigns LLC; atrainmarketing.com; UX Magazine (trauma-informed design); Innovation Unit.

## 4. Design Systems — Atomic Design e Tokens

Metodologia de Brad Frost: hierarquia átomo → molécula → organismo → template → página.
- Tokens primitivos (ex.: purple-500) — valores brutos de cor/espaçamento.
- Tokens semânticos (ex.: color-action-primary) — referenciam os primitivos e carregam
  significado de uso. Definir tokens ANTES de qualquer componente.
- Como esta squad NÃO usa Figma, os "tokens" e "componentes" são documentados e publicados
  como especificação estruturada (markdown) + previews HTML no Claude Design, em vez de
  Figma Variables/Variant Properties — a lógica de separação primitivo/semântico e a
  hierarquia atômica continuam sendo a metodologia organizadora.

Fontes: Figma Blog (atomic components); makandra.de; Brad Frost (Design Systems Q&A); Figma Learn.

## Benchmarking de Apps (resumo reaproveitado — fonte completa em squads/tcc-documentacao/pipeline/data/research-brief.md, NÃO repesquisar)

| App | Diferencial | Gap conhecido |
|---|---|---|
| PenhaS (Brasil, ONG AzMina) | Cobertura nacional, rota de fuga, gravação de áudio | ONG, não serviço estatal unificado |
| bSafe (Noruega/EUA) | SOS, Follow Me, gravação áudio/vídeo | Armazenamento local vulnerável, monetização por assinatura |
| Circle of 6 (EUA) | UX de 1-2 toques, círculo de 6 contatos | Sem integração com legislação brasileira, eficácia não comprovada |

## Perfil Demográfico do Público-Alvo (reaproveitado de squads/tcc-documentacao/pipeline/data/research-brief.md, achado 3 — NÃO repesquisar)

Perfil das vítimas de feminicídio no Brasil em 2024: 63,6%-64% eram mulheres
negras; 70,5%-71% tinham entre 18 e 44 anos; 64,3% dos crimes ocorreram
dentro da própria residência. Confiança: ALTA (dado consistente entre FBSP
e reportagens de Agência Brasil/MPRS sobre o mesmo Anuário). Fonte: FBSP,
2026 (Retrato dos Feminicídios no Brasil).

Este perfil é o ponto de partida demográfico OBRIGATÓRIO para a pesquisa de
cor e público de Renata Referência (Step 2) — nunca tratar o público do
Amparo como "mulheres" de forma genérica e demograficamente neutra. A squad
tcc-documentacao já identificou que boa parte da literatura internacional
sobre safety apps usa amostras predominantemente brancas, sub-representando
mulheres negras e o contexto socioeconômico brasileiro — o mesmo gap se
aplica, por extensão, à literatura sobre psicologia de cor e percepção
visual em contextos de trauma, e deve ser tratado com a mesma ressalva
explícita por Renata.

## Nota Metodológica — Esta Squad Não Usa Figma

Diferente da squad `design-ux-ui-amparo` (sendo descontinuada/dividida),
esta squad documenta e publica a identidade visual e o design system
inteiramente no Claude Design (claude.ai/design), via ferramenta
`DesignSync`, usando HTML estruturado com comentários `<!-- @dsCard
group="..." -->` para categorização. A squad `fluxos-uxui-amparo` (em
construção paralela) é responsável por ler esse trabalho publicado e
reconstruí-lo fielmente dentro do Figma antes de desenhar fluxos de UX e
telas de alta fidelidade.
