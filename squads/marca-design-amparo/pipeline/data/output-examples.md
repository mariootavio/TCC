# Output Examples — Extensão de Marca & Design System Amparo

> Compilação dos `Output Examples` de cada agente desta squad reformulada.
> Servem como referência de qualidade e profundidade esperada — não como
> template rígido. Todos os valores (hex, fontes, nomes de seção) usados
> nos exemplos abaixo são os valores REAIS de `brand/design-system.md`,
> não hipóteses — podem ser reaproveitados diretamente como referência.

## Flávia Fonte — Especificação de Conceito & Prompts

### Exemplo 1: Especificação de componente novo

```markdown
# Especificação — Componente "Card de Check-in Seguro"

Pedido original: "preciso de um card para o histórico de check-ins do app"
Verificação de duplicidade: não existe componente equivalente em
brand/design-system.md nem brand/manual-amparo.pdf (mais próximo é o card
genérico da seção 8, mas sem os campos de check-in) — lacuna real.
Roteamento: segue para Tomás Tokens (Step 4) — usuário pediu implementação
no Figma.

## Anatomia
- Radius: `radius-md` (12px, seção 7) — mesmo padrão dos cards existentes.
- Fundo: Branco Base #FFFFFF sobre tela Areia Acolhedora #F2EAE4 (seção 5,
  regra de card já documentada na seção 8).
- Ícone: "Check-in Seguro" (galeria da seção 9), traço 1.5pt, cor Grafite
  Leitura #333333.
- Texto de data/hora: Nunito Sans Regular 12px (Legenda, seção 6), cor
  Cinza Silêncio #8E8984.
- Texto de status: Nunito Sans SemiBold 16px (Corpo, seção 6), cor
  Confirmação Guardião #2E7D6B quando concluído (uso restrito e correto
  conforme seção 5 — não decorativo).

## Estados
Padrão, Concluído (borda esquerda 3px #2E7D6B), Pendente (sem borda
colorida — nunca usar Alerta SOS #C62828 aqui, é uso restrito a
emergência).

## Nomenclatura atômica
`Molecules/Card/Check-in-Historico`

## Próximo Passo
Aguardando checkpoint Step 3 (aprovação da especificação) antes de Tomás
implementar no Figma.
```

### Exemplo 2: Prompt de imagem

```markdown
# Prompt de Imagem — Hero da Landing Page

Pedido original: "imagem para o hero da landing page, mulher usando o app"
Roteamento: entrega final deste ciclo — usuário pediu só o prompt.

## Prompt

Editorial photograph of a confident Black woman in her early 30s, smiling
softly while looking at her smartphone on a sunlit urban street, natural
window/daylight, warm neutral background in dusty wine and sandy beige
tones (matching Amparo's palette: #954B6E, #F2EAE4), modern minimal
composition, contemporary lifestyle photography, hyper realistic, 4K
quality, clean composition, no visible text or UI content on the phone
screen, --ar 16:9 --style raw

## Justificativa
Segue a diretriz "sempre o depois, nunca o durante" (seção 10 do design
system) e o sujeito preferencial de direcao-imagens-ia.md: mulher real,
segura e no controle. Paleta calibrada com Vinho Amparo/Areia Acolhedora.
Nenhum texto ou UI visível no celular — preserva a discrição do app mesmo
numa imagem promocional pública.
```

## Tomás Tokens — Implementação em Figma (MCP)

### Exemplo 1: Implementação de componente novo

```markdown
# Implementação Figma — Componente "Card de Check-in Seguro"

Especificação de origem: especificacao.md (Flávia, aprovada Step 3)
Arquivo Figma: "Amparo — App" (localizado via figma-use, já existente,
construído por Caio Componentes na squad fluxos-uxui-amparo)
Página: "Design System / Componentes / Molecules"

## Tokens/variáveis usados (todos já existentes no arquivo)
- radius/md (12px)
- color/bg/surface (Branco Base #FFFFFF)
- color/text/muted (Cinza Silêncio #8E8984)
- color/action/confirm (Confirmação Guardião #2E7D6B)
- Ícone "Check-in Seguro" (componente de ícone já existente na biblioteca)

## Componente criado
Molecules/Card/Check-in-Historico — 3 variantes (Padrão, Concluído,
Pendente), adicionado como frame novo na página de Componentes, ao lado
dos cards já existentes — nenhum componente pré-existente foi alterado.

## Próximo Passo
Aguardando auditoria de fidelidade de Marina Marca (Step 5).
```

### Exemplo 2: Step não aplicável

```markdown
# Implementação Figma — Não Aplicável

Especificação de origem: especificacao.md (prompt de imagem, Flávia, Step 2)
Roteamento definido por Flávia: "entrega final deste ciclo — usuário pediu
só o prompt de imagem, não implementação no Figma".

Nenhuma ação de implementação foi executada neste ciclo. Seguindo para o
Step 5 (auditoria de Marina Marca sobre o prompt gerado).
```

## Marina Marca — Auditoria de Fidelidade

### Exemplo 1: Veredito APROVAR

```
==============================
 VEREDITO DA AUDITORIA: APROVAR
==============================
Material auditado: especificacao.md (Flávia) + implementacao-figma.md (Tomás).

| Critério | Nota | Resumo |
|---|---|---|
| Fidelidade de tokens/logo | 10/10 | Todos os valores rastreáveis a brand/design-system.md, seções 5-7 |
| Integridade do que já existia | 10/10 | Nenhum componente/token pré-existente foi alterado |
| Não-duplicação | 9/10 | Componente preenche lacuna real |
| Conformidade trauma-informada | 9/10 | Nenhuma cor funcional usada fora do contexto restrito |
| Qualidade da documentação | 8/10 | Clara, falta só o link direto do frame no Figma |
MÉDIA GERAL: 9.2/10

Nenhum gatilho de rejeição automática violado.

Ponto forte: o componente reaproveita exatamente os tokens de card já
documentados na seção 8, mantendo consistência visual perfeita.

VEREDITO: APROVAR.
```

### Exemplo 2: Veredito REJEITAR (gatilho de integridade violado)

```
==============================
 VEREDITO DA AUDITORIA: REJEITAR
==============================
Material auditado: implementacao-figma.md (Tomás).

| Critério | Nota | Resumo |
|---|---|---|
| Fidelidade de tokens/logo | 8/10 | Valores corretos |
| Integridade do que já existia | 1/10 | Atoms/Button/Primary foi movido e teve o padding alterado |
| Não-duplicação | 9/10 | Hero banner é novo |
| Conformidade trauma-informada | 8/10 | Sem violação |
| Qualidade da documentação | 7/10 | Clara |
MÉDIA GERAL: 6.6/10

GATILHO DE REJEIÇÃO AUTOMÁTICA: Integridade pontuou 1/10 — o componente
Atoms/Button/Primary, usado em outras telas, foi alterado para servir ao
novo hero. Rejeição obrigatória, independente da média.

Ponto forte: os novos elementos do hero usam corretamente os tokens de
cor e tipografia da marca.

Correção obrigatória: reverter Atoms/Button/Primary ao estado original e
criar uma NOVA variante (ex. Atoms/Button/Primary-Hero) em vez de alterar
a existente. Localização: arquivo Figma "Amparo — App".

VEREDITO: REJEITAR — gatilho de integridade violado. Pipeline retorna ao
Step 2 (Flávia Fonte reespecifica preservando o componente original).
```

## Helena Manual — Documentação de Extensões

### Exemplo 1: Entrada de apêndice — componente aprovado

```markdown
## [2026-07-09] Componente novo: Card de Check-in Seguro

Pedido original: "preciso de um card para o histórico de check-ins do app"
Criado por: Flávia Fonte (especificação) + Tomás Tokens (implementação Figma)
Veredito: APROVAR (Marina Marca, 9.2/10)

Tokens usados (origem: brand/design-system.md): radius-md (12px, seção 7),
Branco Base #FFFFFF (seção 5), Cinza Silêncio #8E8984 (seção 5),
Confirmação Guardião #2E7D6B — uso restrito conforme seção 5.

Localização: arquivo Figma "Amparo — App", página Design System /
Componentes / Molecules, componente Molecules/Card/Check-in-Historico.

Nenhum componente pré-existente foi alterado.
```

### Exemplo 2: Entrada de apêndice — prompt de imagem aprovado

```markdown
## [2026-07-09] Prompt de imagem: Hero da Landing Page

Pedido original: "imagem para o hero da landing page, mulher usando o app"
Criado por: Flávia Fonte
Veredito: APROVAR (Marina Marca, 9/10)

Prompt final: ver output/especificacao.md deste ciclo (prompt completo,
--ar 16:9). Paleta calibrada com Vinho Amparo #954B6E e Areia Acolhedora
#F2EAE4 (brand/design-system.md, seção 5). Sem imagem gerada neste ciclo
— entrega foi o prompt em texto.
```
