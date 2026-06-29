---
task: "Consolidar e Exportar Documento Final"
order: 3
input: |
  - relatorio_tcc: Conteúdo de squads/tcc-documentacao/output/relatorio-tcc.md (aprovado no checkpoint final)
  - argumentacao_defesa: Conteúdo de squads/tcc-documentacao/output/argumentacao-defesa.md (aprovado no checkpoint final)
output: |
  - documento_final_md: Markdown único consolidado (relatório + apêndice de argumentação)
  - documento_final_docx: squads/tcc-documentacao/output/tcc-amparo-final.docx
  - documento_final_pdf: squads/tcc-documentacao/output/tcc-amparo-final.pdf (ou ausente, com aviso, se a geração de PDF falhar)
---

# Consolidar e Exportar Documento Final

Após a aprovação final do usuário (checkpoint Step 7), consolida o relatório
do TCC e o pacote de argumentação/slide deck em um único documento Markdown
coeso — relatório como corpo principal, argumentação/roteiro de slides como
apêndice — e usa o skill `docx` para gerar o DOCX final com formatação ABNT
precisa (capa, margens, numeração de página, sumário), convertendo em seguida
esse MESMO arquivo DOCX para PDF — nunca duas conversões separadas a partir
do Markdown, para que DOCX e PDF nunca divirjam entre si.

## Process

1. Confirmar que o checkpoint de aprovação final (Step 7) foi concluído antes
   de iniciar esta task — nunca exportar conteúdo não aprovado pelo usuário.
2. Ler `squads/tcc-documentacao/output/relatorio-tcc.md` (corpo principal) e
   `squads/tcc-documentacao/output/argumentacao-defesa.md` (apêndice) por
   completo.
3. Consolidar os dois arquivos em um único Markdown final
   (`squads/tcc-documentacao/output/tcc-amparo-final.md`): o conteúdo do
   relatório entra primeiro, sem alterações de conteúdo; em seguida um
   separador de seção ("APÊNDICE A — Pacote de Argumentação de Defesa") e o
   conteúdo de argumentacao-defesa.md.
4. Invocar o skill `docx` (Skill tool) e usar `docx-js` para gerar
   `squads/tcc-documentacao/output/tcc-amparo-final.docx` a partir do
   Markdown consolidado, aplicando formatação ABNT explícita: capa (instituição,
   curso, título, autor, ano), margens 3cm (superior/esquerda) e 2cm
   (inferior/direita) conforme NBR 14724:2024, numeração de página no canto
   superior direito a partir da introdução, e sumário gerado automaticamente
   a partir dos títulos de seção.
5. Converter o DOCX recém-gerado em PDF a partir do MESMO arquivo, usando o
   script do skill `docx` baseado em LibreOffice:
   `python scripts/office/soffice.py --headless --convert-to pdf squads/tcc-documentacao/output/tcc-amparo-final.docx`
   (gera `tcc-amparo-final.pdf` na mesma pasta). Se o LibreOffice não estiver
   disponível no ambiente Mac, instalar com `brew install --cask libreoffice`
   antes de repetir a conversão.
6. Validar cada arquivo de saída com
   `test -s squads/tcc-documentacao/output/tcc-amparo-final.docx` e
   `test -s squads/tcc-documentacao/output/tcc-amparo-final.pdf` (exit code 0
   e tamanho > 0 confirmam sucesso).
7. Se a conversão para PDF falhar mesmo após a instalação do LibreOffice
   (ex.: ambiente sem permissão de instalação): entregar ao menos o DOCX já
   validado, e informar ao usuário explicitamente o comando manual para gerar
   o PDF depois — nunca declarar a exportação como falha total se ao menos o
   DOCX foi gerado com sucesso.

## Output Format

```yaml
documento_final:
  arquivo_md: "squads/tcc-documentacao/output/tcc-amparo-final.md"
  arquivo_docx: "squads/tcc-documentacao/output/tcc-amparo-final.docx"
  arquivo_pdf: "squads/tcc-documentacao/output/tcc-amparo-final.pdf"
  status_docx: "gerado | falhou"
  status_pdf: "gerado (a partir do docx via LibreOffice) | falhou (comando manual informado)"
  formatacao_abnt:
    capa: true
    margens: "3cm sup/esq, 2cm inf/dir"
    numeracao_pagina: "a partir da introdução"
    sumario_automatico: true
  validacao:
    docx_tamanho_maior_que_zero: true
    pdf_tamanho_maior_que_zero: true
```

## Output Example

> Use como referência de qualidade, não como template rígido.

```
CONSOLIDAÇÃO E EXPORTAÇÃO DO DOCUMENTO FINAL — TCC AMPARO

1. Checkpoint de aprovação final confirmado (Step 7) — prosseguindo com a
   exportação.

2. Consolidando relatorio-tcc.md (corpo) + argumentacao-defesa.md (apêndice)
   em squads/tcc-documentacao/output/tcc-amparo-final.md...
   Estrutura final: Capítulos 1-5 (relatório) + "APÊNDICE A — Pacote de
   Argumentação de Defesa" (teses, perguntas de banca, roteiro de slides).

3. Gerando DOCX via skill `docx` (docx-js), com formatação ABNT:
   - Capa: instituição, curso, título, autor, ano.
   - Margens: 3cm superior/esquerda, 2cm inferior/direita (NBR 14724:2024).
   - Numeração de página no canto superior direito a partir da introdução.
   - Sumário gerado automaticamente a partir dos títulos de seção.
   $ test -s squads/tcc-documentacao/output/tcc-amparo-final.docx && echo OK
   OK

4. Convertendo o mesmo DOCX para PDF via LibreOffice (mesmo arquivo, nunca
   uma segunda conversão a partir do Markdown):
   $ python scripts/office/soffice.py --headless --convert-to pdf squads/tcc-documentacao/output/tcc-amparo-final.docx
   $ test -s squads/tcc-documentacao/output/tcc-amparo-final.pdf && echo OK
   OK

RESULTADO: Documento final exportado com sucesso.
- DOCX: squads/tcc-documentacao/output/tcc-amparo-final.docx (tamanho > 0,
  formatação ABNT aplicada)
- PDF: squads/tcc-documentacao/output/tcc-amparo-final.pdf (tamanho > 0,
  gerado a partir do mesmo DOCX — sem risco de divergência entre os dois)

[Cenário alternativo, se a conversão para PDF falhar mesmo após instalar o LibreOffice:]
RESULTADO: DOCX gerado e validado com sucesso, com formatação ABNT completa.
A conversão para PDF falhou (LibreOffice indisponível neste ambiente).
Entregando apenas o DOCX nesta rodada. Para gerar o PDF manualmente depois,
instale o LibreOffice (`brew install --cask libreoffice`) e rode:
  python scripts/office/soffice.py --headless --convert-to pdf squads/tcc-documentacao/output/tcc-amparo-final.docx
```

## Quality Criteria

- [ ] A exportação só ocorre após confirmação do checkpoint de aprovação
      final.
- [ ] O Markdown consolidado tem o relatório como corpo e a argumentação
      como apêndice claramente identificado.
- [ ] O DOCX foi gerado via skill `docx` com capa, margens ABNT (3-3-2-2cm),
      numeração de página a partir da introdução e sumário automático.
- [ ] Pelo menos o DOCX existe e tem tamanho > 0, validado com `test -s`.
- [ ] O PDF, quando gerado, é uma conversão direta do mesmo DOCX (nunca uma
      segunda conversão independente a partir do Markdown).
- [ ] Se o PDF falhar, o comando manual de geração é informado explicitamente
      ao usuário.

## Veto Conditions

Reject and redo if ANY are true:
1. A exportação foi executada sem confirmação prévia do checkpoint de
   aprovação final.
2. Nenhum arquivo de saída (nem DOCX nem PDF) foi validado com `test -s` antes
   de declarar a task concluída.
