# Direção de Imagens Geradas por IA — Amparo

> Usado por Flávia Fonte (Step 5, card de abertura), Tomás Tokens (Step 7,
> fotos de contexto de mockup) e Helena Manual (Step 11, apresentação
> premium) sempre que avaliarem gerar uma imagem via `image-ai-generator`.
> Objetivo: toda imagem gerada fala diretamente com o público-alvo real do
> Amparo — mulheres, majoritariamente negras, 18-44 anos — com design
> bonito, moderno e que chama atenção, sem nunca comprometer a segurança
> trauma-informada do projeto.

## Sujeito preferencial

- **Mulheres reais usando celular**, com expressão de segurança,
  confiança e tranquilidade — é a imagem-âncora do Amparo. Ex.: mulher
  sorrindo discretamente enquanto olha o celular num ambiente cotidiano
  (casa, rua, transporte, trabalho), luz natural, composição editorial.
- **Representação**: refletir o público real trazido pela pesquisa de
  Renata (majoritariamente mulheres negras, 18-44 anos) — nunca um
  elenco genérico/branco por padrão.
- Quando a cena não pede pessoa (ex.: still life de um mockup de cartão
  sobre mesa), usar mood abstrato/textura como alternativa — mas sempre
  preferir a presença humana quando o slide/card for sobre o público ou
  a proposta do app.

## Tom e composição

- **Bonito, moderno, atrativo** — fotografia editorial contemporânea,
  nunca stock genérico de banco de imagens datado.
  Bonito = luz natural suave, paleta calibrada com a marca (tons frios +
  acento terracota), composição limpa, respiro.
- **Chama atenção sem alarme**: composição forte (enquadramento,
  contraste tonal) pode e deve chamar atenção — a régua trauma-informada
  proíbe cor/tema de alarme, não impacto visual ou beleza.

## Regras trauma-informadas (inegociáveis, valem para toda imagem)

- **Nunca** imagética literal de violência doméstica (hematomas, punhos,
  grades, sangue, expressão de medo/dor).
- **Nunca** vermelho/laranja saturado dominante na composição.
- **Nunca** qualquer elemento que exponha o propósito específico do app
  a quem vê a imagem de relance (sem texto "SOS", sem tela de app com
  conteúdo alarmante visível, sem símbolo de socorro óbvio).
- A mulher retratada deve parecer **segura e no controle**, nunca
  vulnerável ou em risco visível — a imagem comunica a promessa do
  Amparo ("você não está sozinha"), não o problema que ele resolve.

## Disciplina de geração

- `--mode test` sempre primeiro para validar composição; `--mode
  production` só depois de aprovação visual própria.
- 1 imagem por vez — nunca lote especulativo.
- `--reference` no logo aprovado quando fizer sentido compor os dois
  (ex.: mockup de tela de app na mão da modelo).
- Recurso pontual: gerar só onde realmente eleva o resultado (capas,
  aberturas, hero de apresentação) — nunca preenchimento automático de
  todo slide/card.
- Se `OPENROUTER_API_KEY` não estiver configurada, pular a geração e
  resolver com tipografia/composição/mockups existentes — nunca bloquear
  a entrega por isso.

## Exemplo de prompt

```
Editorial photograph of a confident Black woman in her late 20s,
smiling softly while looking at her smartphone, natural window light,
warm neutral background in slate and terracotta tones, modern minimal
composition, contemporary lifestyle photography, hyper realistic, 4K
quality, clean composition, no visible text or UI on the phone screen,
--ar 4:5 --style raw
```
