---
execution: inline
agent: telma-tela
inputFile: squads/fluxos-uxui-amparo/output/fluxos-ux.md
outputFile: squads/fluxos-uxui-amparo/output/telas-alta-fidelidade.md
---

# Step 7: Criar Telas de Alta Fidelidade

## Context Loading

Load these files before executing:
- `squads/fluxos-uxui-amparo/output/fluxos-ux.md` (Joana, já aprovado no
  checkpoint Step 6) — fluxos completos a traduzir em telas.
- `squads/fluxos-uxui-amparo/output/design-system-figma.md` (Caio) —
  inventário de componentes e tokens já reconstruídos, uso exclusivo e
  obrigatório.
- `squads/fluxos-uxui-amparo/output/padroes-seguranca-discricao.md`
  (Daniela) — posição e comportamento exatos dos elementos de segurança em
  cada tela.

## Instructions

### Process

1. Ler `fluxos-ux.md` por completo e identificar cada tela necessária para
   cobrir o caminho feliz e os caminhos de erro de cada fluxo crítico.
2. Ler `design-system-figma.md` e as regras de design system geradas por
   Caio, confirmando o inventário completo de componentes e tokens
   disponíveis antes de desenhar qualquer tela.
3. Carregar `figma:figma-use` e depois `figma:figma-generate-design` para
   traduzir cada fluxo em telas usando exclusivamente componentes/tokens já
   existentes no arquivo Figma.
4. Criar uma página por fluxo no arquivo Figma, com um frame por tela
   (caminho feliz e cada caminho de erro relevante), nomeando frames de
   forma consistente entre estados equivalentes.
5. Verificar que todo elemento de segurança (saída rápida, indicador de modo
   disfarçado) está na posição e comportamento exatos especificados por
   Daniela, em todas as telas.
6. Quando um fluxo exigir um componente ausente do design system, registrar
   a pendência nomeada para Caio e usar um placeholder temporário
   explicitamente sinalizado.
7. Compilar `output/telas-alta-fidelidade.md` com a lista de páginas/telas,
   correspondência exata aos passos de `fluxos-ux.md`, e pendências de
   componente, se houver.

## Output Format

The output MUST follow this exact structure:
```
TELAS DE ALTA FIDELIDADE — AMPARO
Arquivo Figma: {nome}

PÁGINA: "{nome da página}"
Fonte: fluxos-ux.md, fluxo "{nome}", {ancoragem}

Frame "{nome consistente}": {descrição, componentes usados, correspondência ao passo}

PENDÊNCIA PARA CAIO: {se houver — necessidade, componente mais próximo usado como placeholder, recomendação}
```

## Output Example

```
TELAS DE ALTA FIDELIDADE — AMPARO
Arquivo Figma: "Amparo — Design System"

PÁGINA: "Fluxo — Acionamento de Emergência"
Fonte: fluxos-ux.md, fluxo "Acionamento de Emergência", RF-CORE-01.

Frame "Emergência / Acionamento — Padrão": botão de emergência (ação
global) sempre visível, componente "Botão Primário — Tamanho Grande".
Corresponde ao passo 1 do Caminho Feliz.

Frame "Emergência / Confirmação — Padrão": feedback visual imediato,
componente "Indicador de Status — Sucesso". Corresponde ao passo 1-2.

Frame "Emergência / Confirmação — Erro Sem Conexão": variação do frame
anterior, componente "Indicador de Status — Atenção", mesma estrutura.

Posição da saída rápida: ícone fixo no canto superior direito, idêntico
nos 3 frames, conforme Padrão 1 de Daniela.

PENDÊNCIA PARA CAIO: indicador de "Backup Pendente" não existe no
design system atual — usado "Indicador de Status — Atenção" como
placeholder temporário no fluxo de Documentação de Evidências.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Algum elemento visual novo (cor, fonte, componente) foi criado fora do
   design system de Caio sem registrar a pendência correspondente.
2. Alguma conexão de protótipo (overlay, link, Interactive Component) foi
   criada por Telma — essa responsabilidade pertence exclusivamente a
   Pietro no Step 8.

## Quality Criteria

- [ ] Toda tela usa exclusivamente componentes/tokens já existentes no
      design system de Caio.
- [ ] Toda tela cita o fluxo e passo exato de `fluxos-ux.md` que traduz.
- [ ] Toda pendência de componente ausente está registrada nomeada para
      Caio.
- [ ] Frames de estados equivalentes seguem nomenclatura consistente.
