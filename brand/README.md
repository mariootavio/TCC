# Amparo — Ativos de Marca (FONTE ÚNICA DA VERDADE — FINALIZADO)

> Esta pasta contém a identidade visual e o design system **definitivos e
> aprovados** do Amparo. Nenhuma squad, agente ou pipeline deste projeto
> deve gerar, propor ou sugerir uma cor, fonte, logotipo, espaçamento, raio
> de borda, ícone ou tom de voz diferente do que está documentado aqui.
> O trabalho de criação de marca já foi concluído — o que resta é aplicar,
> validar e manter consistência com estes arquivos.

## Arquivos

| Arquivo | O que é | Quando usar |
|---|---|---|
| `design-system.md` | Especificação completa e legível em texto: cores (hex), tipografia, espaçamento, raios, componentes, ícones, linguagem fotográfica, princípios inegociáveis de segurança. | Referência primária para qualquer decisão de UI, copy ou componente. Todo agente que for gerar uma tela, componente, peça gráfica ou texto de marca deve carregar este arquivo primeiro. |
| `LogoAmparo.svg` | Logotipo vetorial oficial (símbolo + wordmark), cor `#9F5773`/paleta oficial, sobre fundo `#F6F2F0`. | Único arquivo de logo a ser referenciado/embedado em protótipos, mockups, landing pages e apresentações. Nunca recriar o símbolo do zero. |
| `LogoAmparo-SemFundo.png` | Logotipo em PNG com fundo transparente. | Aplicações que precisem de PNG (apresentações, documentos, mockups fora de contexto SVG). |
| `LogoAmparo.jpg` | Logotipo em JPG sobre fundo sólido. | Aplicações que exigem JPG. |
| `manual-amparo.pdf` | Manual de Identidade Visual completo e publicado (15 seções: introdução, marca, missão/visão/valores, personas, território visual, logotipo, versões, usos incorretos, paleta, tipografia, ícones, componentes, aplicação em app, linguagem fotográfica, encerramento). | Documento de referência completo para consulta, anexo de monografia, e onboarding de qualquer squad que precise entender o racional completo por trás da marca. |

## Regra para todas as squads

- **marca-design-amparo**: seu papel deixou de ser "criar a identidade" e passou a ser "aplicar, documentar e auditar fidelidade" a estes arquivos. Ver aviso no topo de `squads/marca-design-amparo/pipeline/data/domain-framework.md`.
- **fluxos-uxui-amparo**: toda implementação em Figma deve reproduzir exatamente os tokens de `design-system.md` e o `LogoAmparo.svg` — nenhum valor novo.
- **landing-page-amparo**: toda peça de front-end (cores, fontes, espaçamento, logo) deve importar exatamente os valores daqui.
- **brainstorm-amparo / tcc-documentacao**: ao ilustrar ou descrever a marca, sempre citar/usar estes ativos, nunca inventar uma variação.

Resumo essencial (para não precisar abrir `design-system.md` toda vez):
Primária `#954B6E` (Vinho Amparo) · Secundárias `#4B2A3F` / `#C58DA8` / `#F2EAE4` ·
Texto `#333333` · Funcionais `#C62828` (SOS, uso restrito) / `#2E7D6B` (confirmação, uso restrito) ·
Tipografia: Quicksand (títulos) + Nunito Sans (corpo) + Inter (dados técnicos/legais) ·
Slogan definitivo: "Você não está sozinha." — nunca alterar.
