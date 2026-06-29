---
execution: inline
agent: helena-hipotese
inputFile: squads/tcc-documentacao/output/relatorio-tcc.md
outputFile: squads/tcc-documentacao/output/tcc-amparo-final.docx
---

# Step 8: Consolidar e Exportar Documento Final

## Context Loading

Load these files before executing:
- `squads/tcc-documentacao/output/relatorio-tcc.md` — relatório final
  aprovado pelo usuário no checkpoint Step 7.
- `squads/tcc-documentacao/output/argumentacao-defesa.md` — pacote de
  argumentação final aprovado pelo usuário no checkpoint Step 7.
- `squads/tcc-documentacao/output/revisao.md` — veredito de Renata
  Referência, para confirmar que o conteúdo já passou pela revisão de
  qualidade.

## Instructions

### Process

1. Confirmar que o checkpoint de aprovação final (Step 7) foi concluído
   antes de iniciar a consolidação — nunca exportar conteúdo não aprovado.
2. Executar a task `consolidar-e-exportar-documento-final.md`: consolidar
   relatorio-tcc.md (corpo) + argumentacao-defesa.md (apêndice) em
   `squads/tcc-documentacao/output/tcc-amparo-final.md`.
3. Invocar o skill `docx` (Skill tool) e gerar o DOCX final via `docx-js`,
   com formatação ABNT explícita: capa, margens 3cm sup/esq e 2cm inf/dir
   (NBR 14724:2024), numeração de página a partir da introdução, e sumário
   automático.
4. Converter esse MESMO arquivo DOCX para PDF via LibreOffice (script do
   próprio skill `docx`):
   `python scripts/office/soffice.py --headless --convert-to pdf squads/tcc-documentacao/output/tcc-amparo-final.docx`
   Se o LibreOffice não estiver disponível, instalar com
   `brew install --cask libreoffice` antes de repetir.
5. Validar ambos os arquivos com `test -s {arquivo}` (tamanho > 0). Se a
   conversão para PDF falhar mesmo após a instalação do LibreOffice, entregar
   ao menos o DOCX validado e informar ao usuário o comando manual exato
   para gerar o PDF posteriormente — nunca declarar falha total se o DOCX
   foi gerado com sucesso.

## Output Format

The output MUST follow this exact structure:
```
CONSOLIDAÇÃO E EXPORTAÇÃO DO DOCUMENTO FINAL — TCC AMPARO

1. Checkpoint de aprovação final: {confirmado}
2. Markdown consolidado: squads/tcc-documentacao/output/tcc-amparo-final.md
   Estrutura: Capítulos do relatório + "APÊNDICE A — Pacote de Argumentação
   de Defesa"
3. DOCX gerado via skill `docx` (formatação ABNT — capa, margens, numeração,
   sumário): squads/tcc-documentacao/output/tcc-amparo-final.docx
   Validação test -s: {OK | FALHOU}
4. PDF gerado (conversão do mesmo DOCX via LibreOffice):
   squads/tcc-documentacao/output/tcc-amparo-final.pdf
   Validação test -s: {OK | FALHOU — comando manual informado}

RESULTADO: {resumo final do que foi entregue}
```

## Output Example

```
CONSOLIDAÇÃO E EXPORTAÇÃO DO DOCUMENTO FINAL — TCC AMPARO

1. Checkpoint de aprovação final: confirmado (Step 7, APROVAR).
2. Markdown consolidado: squads/tcc-documentacao/output/tcc-amparo-final.md
   Estrutura: Capítulos 1-5 do relatório + "APÊNDICE A — Pacote de
   Argumentação de Defesa" (teses, perguntas de banca, roteiro de slides).
3. DOCX gerado via skill `docx` (docx-js), com formatação ABNT: capa
   (instituição/curso/título/autor/ano), margens 3cm sup/esq e 2cm inf/dir,
   numeração de página a partir da introdução, sumário automático.
   $ test -s squads/tcc-documentacao/output/tcc-amparo-final.docx && echo OK
   OK
4. PDF gerado a partir do mesmo DOCX via LibreOffice:
   $ python scripts/office/soffice.py --headless --convert-to pdf squads/tcc-documentacao/output/tcc-amparo-final.docx
   $ test -s squads/tcc-documentacao/output/tcc-amparo-final.pdf && echo OK
   OK

RESULTADO: Documento final exportado com sucesso em DOCX e PDF, ambos com
tamanho > 0, formatação ABNT aplicada no DOCX e o PDF gerado a partir do
mesmo arquivo (sem risco de divergência entre os dois formatos).

[Cenário de fallback, se a conversão para PDF falhar:]
RESULTADO: DOCX gerado e validado com sucesso, com formatação ABNT completa.
A conversão para PDF falhou (LibreOffice indisponível neste ambiente).
Entregando apenas o DOCX nesta rodada. Para gerar o PDF manualmente depois,
instale o LibreOffice (`brew install --cask libreoffice`) e rode:
  python scripts/office/soffice.py --headless --convert-to pdf squads/tcc-documentacao/output/tcc-amparo-final.docx
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. A exportação foi executada sem confirmação prévia do checkpoint de
   aprovação final (Step 7).
2. Nenhum arquivo de saída foi validado com `test -s` antes de declarar a
   task concluída.

## Quality Criteria

- [ ] O Markdown consolidado tem o relatório como corpo e a argumentação
      como apêndice claramente identificado.
- [ ] Pelo menos o DOCX existe e tem tamanho > 0.
- [ ] Se o PDF falhar, o comando manual de geração é informado ao usuário.
