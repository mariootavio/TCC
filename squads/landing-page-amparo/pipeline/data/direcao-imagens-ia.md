# Direção de Imagens Geradas por IA — Landing Page Amparo

> Usado por Diego Assets (Step 6) sempre que a especificação visual de
> Vitória Visual pedir fotografia editorial para uma seção (tipicamente
> Hero, Sobre o Projeto, Prova Social, Como Funciona). Objetivo: toda
> imagem fala diretamente com o público-alvo real do Amparo — mulheres,
> majoritariamente negras, 18-44 anos — com fotografia bonita, moderna e
> que chama atenção, sem nunca comprometer a segurança trauma-informada
> do projeto.
>
> **Paleta real e travada (ver `brand/design-system.md`):** Vinho Amparo
> `#954B6E` (primária), Vinho Profundo `#4B2A3F`, Malva Suave `#C58DA8`,
> Areia Acolhedora `#F2EAE4` — toda imagem gerada deve compor com esses
> tons, nunca introduzir uma paleta cromática dissonante.

## Sujeito preferencial

- **Mulheres reais usando celular**, com expressão de segurança,
  confiança e tranquilidade — é a imagem-âncora do Amparo. Ex.: mulher
  sorrindo discretamente enquanto olha o celular num ambiente cotidiano
  (casa, rua, transporte, trabalho), luz natural, composição editorial.
- **Representação**: refletir o público real do Amparo, já documentado em
  `_opensquad/_memory/company.md` e `brand/design-system.md` — nunca um
  elenco genérico/branco por padrão.
- Quando a seção não pede pessoa (ex.: fundo abstrato do Hero, textura de
  seção institucional), usar ilustração/forma abstrata simbólica (mãos,
  luz, espaços seguros) como alternativa — mas sempre preferir a presença
  humana quando a seção for sobre o público ou a proposta do app.

## Tom e composição

- **Bonito, moderno, atrativo** — fotografia editorial contemporânea,
  nunca stock genérico de banco de imagens datado.
  Bonito = luz natural suave, paleta calibrada com a marca (Vinho Amparo
  `#954B6E` e Areia Acolhedora `#F2EAE4`, nunca tons frios/azulados),
  composição limpa, respiro.
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
  production` só depois de aprovação visual própria de Diego.
- 1 imagem por vez — nunca lote especulativo. Gerar só onde a
  especificação de Vitória realmente pede (Hero e 1-2 seções
  institucionais), nunca preenchimento automático de toda seção.
- `--reference` no logo aprovado quando fizer sentido compor os dois
  (ex.: mockup de tela do app na mão da modelo).
- Se `OPENROUTER_API_KEY` não estiver configurada, pular a geração e
  resolver com tipografia/composição/ilustração simbólica existentes —
  nunca bloquear a entrega por isso; registrar a pendência em
  `implementacao-figma.md`.

## "Vídeo" e dinamismo nesta squad

Como o entregável desta squad é 100% um arquivo Figma (não um site em
produção), "vídeo" e elementos dinâmicos são sempre traduzidos em **motion
do protótipo Figma** (Smart Animate, interações, transições de estado) via
skill `figma-use-motion` — nunca em arquivo de vídeo renderizado. Diego
sempre nomeia essa distinção com clareza no output.

## Exemplo de prompt

```text
Editorial photograph of a confident Black woman in her late 20s,
smiling softly while looking at her smartphone, natural window light,
warm neutral background in dusty wine and sandy beige tones (matching
Amparo's palette: #954B6E, #F2EAE4), modern minimal composition,
contemporary lifestyle photography, hyper realistic, 4K quality, clean
composition, no visible text or UI on the phone screen,
--ar 4:5 --style raw
```
