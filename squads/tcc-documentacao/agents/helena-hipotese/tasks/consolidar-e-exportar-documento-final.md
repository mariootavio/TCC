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
apêndice — e exporta o resultado em DOCX e PDF via pandoc, com fallback
documentado caso as ferramentas não estejam instaladas.

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
4. Verificar se `pandoc` e `typst` estão disponíveis no ambiente, rodando:
   `which pandoc` e `which typst`. Se algum estiver ausente em ambiente Mac,
   instalar com: `brew install pandoc typst`.
5. Gerar o DOCX rodando via Bash:
   `pandoc squads/tcc-documentacao/output/tcc-amparo-final.md -o squads/tcc-documentacao/output/tcc-amparo-final.docx`
6. Gerar o PDF rodando via Bash:
   `pandoc squads/tcc-documentacao/output/tcc-amparo-final.md -o squads/tcc-documentacao/output/tcc-amparo-final.pdf --pdf-engine=typst`
7. Validar cada arquivo de saída com
   `test -s squads/tcc-documentacao/output/tcc-amparo-final.docx` e
   `test -s squads/tcc-documentacao/output/tcc-amparo-final.pdf` (exit code 0
   e tamanho > 0 confirmam sucesso).
8. Se a geração do PDF falhar mesmo após a instalação via Homebrew (ex.: erro
   de engine, fonte ausente, ambiente sem permissão de instalação): entregar
   ao menos o DOCX já validado, e informar ao usuário explicitamente o
   comando manual para gerar o PDF depois — por exemplo:
   `pandoc squads/tcc-documentacao/output/tcc-amparo-final.md -o squads/tcc-documentacao/output/tcc-amparo-final.pdf --pdf-engine=typst`
   — nunca declarar a exportação como falha total se ao menos o DOCX foi
   gerado com sucesso.

## Output Format

```yaml
documento_final:
  arquivo_md: "squads/tcc-documentacao/output/tcc-amparo-final.md"
  arquivo_docx: "squads/tcc-documentacao/output/tcc-amparo-final.docx"
  arquivo_pdf: "squads/tcc-documentacao/output/tcc-amparo-final.pdf"
  status_docx: "gerado | falhou"
  status_pdf: "gerado | falhou (comando manual informado)"
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

3. Verificando dependências:
   $ which pandoc
   pandoc not found
   $ which typst
   typst not found
   Instalando via Homebrew: `brew install pandoc typst`
   ✓ pandoc 3.x instalado
   ✓ typst 0.x instalado

4. Gerando DOCX:
   $ pandoc squads/tcc-documentacao/output/tcc-amparo-final.md -o squads/tcc-documentacao/output/tcc-amparo-final.docx
   $ test -s squads/tcc-documentacao/output/tcc-amparo-final.docx && echo OK
   OK

5. Gerando PDF:
   $ pandoc squads/tcc-documentacao/output/tcc-amparo-final.md -o squads/tcc-documentacao/output/tcc-amparo-final.pdf --pdf-engine=typst
   $ test -s squads/tcc-documentacao/output/tcc-amparo-final.pdf && echo OK
   OK

RESULTADO: Documento final exportado com sucesso.
- DOCX: squads/tcc-documentacao/output/tcc-amparo-final.docx (tamanho > 0)
- PDF: squads/tcc-documentacao/output/tcc-amparo-final.pdf (tamanho > 0)

[Cenário alternativo, se o PDF falhar mesmo após instalação:]
RESULTADO: DOCX gerado com sucesso. A geração do PDF falhou (engine typst
incompatível com o ambiente). Entregando apenas o DOCX nesta rodada.
Para gerar o PDF manualmente depois, rode:
  pandoc squads/tcc-documentacao/output/tcc-amparo-final.md -o squads/tcc-documentacao/output/tcc-amparo-final.pdf --pdf-engine=typst
```

## Quality Criteria

- [ ] A exportação só ocorre após confirmação do checkpoint de aprovação
      final.
- [ ] O Markdown consolidado tem o relatório como corpo e a argumentação
      como apêndice claramente identificado.
- [ ] Pelo menos o DOCX existe e tem tamanho > 0, validado com `test -s`.
- [ ] Se o PDF falhar, o comando manual de geração é informado explicitamente
      ao usuário.

## Veto Conditions

Reject and redo if ANY are true:
1. A exportação foi executada sem confirmação prévia do checkpoint de
   aprovação final.
2. Nenhum arquivo de saída (nem DOCX nem PDF) foi validado com `test -s` antes
   de declarar a task concluída.
