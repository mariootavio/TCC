---
task: "Montar Protótipo Navegável"
order: 2
input: |
  - telas_alta_fidelidade: Telas de alta fidelidade criadas na task anterior — incorporadas em squads/design-ux-ui-amparo/output/telas-prototipo.md
output: |
  - prototipo_navegavel: Especificação das conexões do protótipo navegável (link Figma + mapa de conexões) — squads/design-ux-ui-amparo/output/telas-prototipo.md (seção final, consolidando o documento completo)
---

# Montar Protótipo Navegável

Conecta as telas de alta fidelidade em um protótipo navegável no Figma
(transições, overlays, interactive components), permitindo navegação completa
pelos fluxos críticos sem telas mortas.

## Process

1. Antes de qualquer chamada à ferramenta `use_figma` para configurar
   conexões, invocar a skill `figma:figma-use` (pré-requisito obrigatório já
   carregado na task anterior, mas confirmar que segue ativo para esta etapa
   de prototipagem).
2. Planejar as interações de cada fluxo: usar overlays para modais/
   confirmações/alertas (nunca duplicar uma tela inteira para representar um
   estado temporário), Interactive Components para estados de botão (hover/
   pressed) definidos uma vez no componente mestre.
3. Usar Smart Animate para transições que se beneficiam de continuidade visual
   (ex.: abertura do botão de emergência) — exceto na ação de saída rápida, que
   deve usar transição "Instant" sem animação perceptível.
4. Nomear frames de forma consistente entre estados equivalentes (ex.: mesmo
   nome base "Modal-Captura" em variações de estado) para que o Smart Animate
   funcione corretamente.
5. Conectar todas as telas de cada fluxo crítico, garantindo que o caminho de
   saída rápida funcione a partir de qualquer ponto do fluxo, incluindo
   modais/overlays.
6. Testar a navegação completa do protótipo por todos os fluxos críticos antes
   de entregar: verificar que nenhum frame está sem conexão de entrada/saída
   (tela morta), documentar o resultado em `output/telas-prototipo.md`, e
   apresentar o link do protótipo a Wagner para revisão — nunca pular essa etapa.

## Output Format

```yaml
prototipo_navegavel:
  link_figma: "string"
  conexoes:
    - origem: "string — nome do frame"
      destino: "string — nome do frame"
      tipo_transicao: "Instant | Smart Animate | Dissolve | Overlay"
      gatilho: "string"
  verificacao_navegacao:
    total_frames: 0
    frames_sem_conexao: 0
    caminho_saida_rapida_testado: true | false
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
PROTÓTIPO NAVEGÁVEL — MODO DISCRETO E SAÍDA RÁPIDA
Página Figma: "05. Modo Discreto e Saída Rápida"

Conexões mapeadas:
  [Qualquer tela do app] --toque na saída rápida (presente em 22 frames)-->
  [Tela Neutra - Clima Fake]
  Transição: "Instant" — decisão deliberada: animação levaria tempo
  perceptível e poderia ser vista pelo agressor.

  [Tela Neutra] --toque longo (1.5s) no ícone do sol--> [Tela Início]
  Transição: "Smart Animate" (200ms) — aceitável pois é gesto intencional.

  [Lista de Registros] --"+ Novo Registro"--> [Modal: Escolher tipo de captura]
  Tipo: Overlay (não tela nova) — fecha com toque fora ou X.

Verificação de navegação completa: todos os 22 frames têm pelo menos uma
conexão de entrada e uma de saída; testado o caminho de saída rápida a partir
de cada um dos 22 frames — nenhuma tela morta.

Nomenclatura de frames para Smart Animate: frames de estado equivalente usam o
mesmo nome base (ex.: "Modal-Captura") para garantir interpolação correta.
```

## Quality Criteria

- [ ] O protótipo permite percorrer as 4 jornadas críticas ponta a ponta sem
      nenhuma tela morta ou link quebrado.
- [ ] A ação de saída rápida usa transição "Instant" em 100% das conexões que
      partem dela.
- [ ] Modais, alertas e confirmações são implementados como overlays, nunca
      como telas duplicadas.

## Veto Conditions

Reject and redo if ANY are true:
1. Existe pelo menos uma tela morta (frame sem conexão de entrada ou saída) no
   protótipo final.
2. A transição de saída rápida usa Smart Animate ou qualquer animação com
   duração perceptível em vez de "Instant".
