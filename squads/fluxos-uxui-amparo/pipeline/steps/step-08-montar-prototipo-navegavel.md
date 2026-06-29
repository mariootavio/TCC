---
execution: inline
agent: pietro-prototipagem
inputFile: squads/fluxos-uxui-amparo/output/telas-alta-fidelidade.md
outputFile: squads/fluxos-uxui-amparo/output/prototipo-navegavel.md
---

# Step 8: Montar Protótipo Navegável

## Context Loading

Load these files before executing:
- `squads/fluxos-uxui-amparo/output/telas-alta-fidelidade.md` (Telma) —
  inventário de páginas, frames e nomenclatura de estados equivalentes.
- `squads/fluxos-uxui-amparo/output/fluxos-ux.md` (Joana) — transições
  esperadas (origem → destino) de cada caminho feliz e caminho de erro.
- `squads/fluxos-uxui-amparo/output/padroes-seguranca-discricao.md`
  (Daniela) — regra de transição instantânea da saída rápida.

## Instructions

### Process

1. Ler `telas-alta-fidelidade.md` e `fluxos-ux.md` por completo, confirmando
   cada transição esperada antes de criar qualquer conexão.
2. Ler `padroes-seguranca-discricao.md` para confirmar a regra de transição
   instantânea da saída rápida e seu destino exato.
3. Carregar `figma:figma-use` e conectar as telas: overlays para
   modais/confirmações, Interactive Components para estados de botão, Smart
   Animate entre frames de estado equivalente com nomenclatura consistente.
4. Aplicar transição instantânea (sem Smart Animate, sem easing) em toda
   ocorrência da saída rápida, em todas as telas onde ela aparece — sem
   exceção.
5. Percorrer manualmente a navegação completa de cada fluxo crítico —
   caminho feliz e cada caminho de erro — verificando ausência de telas
   mortas e links quebrados.
6. Testar a saída rápida a partir de ao menos 3 pontos distintos do
   protótipo.
7. Compilar `output/prototipo-navegavel.md` com as conexões criadas por
   fluxo, a tabela de verificação de navegação, e pendências encontradas e
   resolvidas.

## Output Format

The output MUST follow this exact structure:
```
PROTÓTIPO NAVEGÁVEL — AMPARO
Arquivo Figma: {nome}

FLUXO: {NOME}
Conexões criadas:
{N}. "{frame origem}" → "{frame destino}": {tipo de transição/overlay}

TABELA DE VERIFICAÇÃO DE NAVEGAÇÃO
| Fluxo | Caminho Feliz | Caminho(s) de Erro | Saída Rápida testada | Status |
|---|---|---|---|---|

PENDÊNCIAS ENCONTRADAS E RESOLVIDAS
{lista, ou "Nenhuma pendência remanescente."}
```

## Output Example

```
PROTÓTIPO NAVEGÁVEL — AMPARO
Arquivo Figma: "Amparo — Design System"

FLUXO: ACIONAMENTO DE EMERGÊNCIA (RF-CORE-01)
Conexões criadas:
1. "Emergência / Acionamento — Padrão" → "Emergência / Confirmação —
   Padrão": Smart Animate (300ms, ease-out).
2. Ícone de saída rápida (nos 3 frames) → "Disfarce / Tela Neutra":
   TRANSIÇÃO INSTANTÂNEA, sem exceção.

TABELA DE VERIFICAÇÃO DE NAVEGAÇÃO
| Fluxo | Caminho Feliz | Caminho(s) de Erro | Saída Rápida testada | Status |
|---|---|---|---|---|
| Acionamento de Emergência | OK | OK | OK — testada nos 3 frames | OK |

PENDÊNCIAS ENCONTRADAS E RESOLVIDAS
1. Frame "Rede de Apoio / Confirmação de Guardião — Erro Timeout" estava
   sem conexão de saída (tela morta). Corrigido: botão "Tentar novamente"
   conectado de volta ao frame Padrão via Smart Animate.
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. Alguma ocorrência da saída rápida usa Smart Animate ou qualquer transição
   animada, em vez de transição instantânea.
2. Algum fluxo crítico não foi testado manualmente de ponta a ponta (caminho
   feliz + caminhos de erro).

## Quality Criteria

- [ ] Todo modal/alerta/confirmação temporária usa overlay, nunca tela
      duplicada.
- [ ] Saída rápida é instantânea em 100% das ocorrências, testada a partir
      de múltiplos pontos.
- [ ] Todo fluxo crítico foi testado manualmente, com resultado registrado.
- [ ] Nenhuma tela morta ou link quebrado permanece sem resolução.
