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
3. Verificar disponibilidade de `pandoc` e `typst` via Bash (`which pandoc`,
   `which typst`); se ausentes em ambiente Mac, instalar com
   `brew install pandoc typst` antes de prosseguir.
4. Gerar o DOCX:
   `pandoc squads/tcc-documentacao/output/tcc-amparo-final.md -o squads/tcc-documentacao/output/tcc-amparo-final.docx`
5. Gerar o PDF:
   `pandoc squads/tcc-documentacao/output/tcc-amparo-final.md -o squads/tcc-documentacao/output/tcc-amparo-final.pdf --pdf-engine=typst`
6. Validar ambos os arquivos com `test -s {arquivo}` (tamanho > 0). Se a
   geração do PDF falhar mesmo após a instalação das dependências, entregar
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
3. Dependências (pandoc/typst): {instaladas | já presentes}
4. DOCX gerado: squads/tcc-documentacao/output/tcc-amparo-final.docx
   Validação test -s: {OK | FALHOU}
5. PDF gerado: squads/tcc-documentacao/output/tcc-amparo-final.pdf
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
3. Dependências: pandoc e typst não encontrados — instalados via
   `brew install pandoc typst`.
4. DOCX gerado:
   $ pandoc squads/tcc-documentacao/output/tcc-amparo-final.md -o squads/tcc-documentacao/output/tcc-amparo-final.docx
   $ test -s squads/tcc-documentacao/output/tcc-amparo-final.docx && echo OK
   OK
5. PDF gerado:
   $ pandoc squads/tcc-documentacao/output/tcc-amparo-final.md -o squads/tcc-documentacao/output/tcc-amparo-final.pdf --pdf-engine=typst
   $ test -s squads/tcc-documentacao/output/tcc-amparo-final.pdf && echo OK
   OK

RESULTADO: Documento final exportado com sucesso em DOCX e PDF, ambos com
tamanho > 0, contendo o relatório completo e o pacote de argumentação como
apêndice.

[Cenário de fallback, se o PDF falhar:]
RESULTADO: DOCX gerado e validado com sucesso. A geração do PDF falhou
mesmo após instalação das dependências (erro de engine typst neste
ambiente). Entregando apenas o DOCX nesta rodada. Para gerar o PDF
manualmente depois, rode:
  pandoc squads/tcc-documentacao/output/tcc-amparo-final.md -o squads/tcc-documentacao/output/tcc-amparo-final.pdf --pdf-engine=typst
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
