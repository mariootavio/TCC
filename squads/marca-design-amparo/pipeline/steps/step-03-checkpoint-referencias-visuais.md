---
type: checkpoint
outputFile: squads/marca-design-amparo/output/referencias-visuais.md
---

# Step 3: Checkpoint — Referências Visuais

## Contexto

Antes de Flávia Fonte criar qualquer direção de identidade visual (Step
4), a squad dá ao usuário a oportunidade de fornecer referências visuais
concretas — algo que o brief de adjetivos (Step 1) por si só não captura.
Este checkpoint existe separadamente do brief de design porque referências
visuais costumam chegar de forma mais solta (links, descrições, imagens
mentais) e merecem um espaço dedicado em vez de competir com as perguntas
mais estruturadas do Step 1.

## Instruções

1. Perguntar ao usuário, em texto livre e aberto: "Você tem referências
   visuais (logos, marcas, paletas, sites) que gostaria que a Flávia
   considerasse ao criar a identidade visual? Pode descrever, colar
   links/URLs, ou dizer que não tem nenhuma referência específica."
2. Aceitar qualquer formato de resposta: texto livre descrevendo um estilo
   ou marca, URLs de sites/posts/imagens, nomes de apps/marcas que o
   usuário admira ou quer evitar, ou uma resposta explícita de "não tenho
   referência específica" — todas são respostas válidas e completas para
   este checkpoint.
3. Se o usuário fornecer URLs, registrá-las no documento de saída
   exatamente como enviadas (este runner não precisa visitar os links
   nesta etapa — isso é trabalho de Flávia no Step 4, se ela julgar
   necessário usar `web_fetch`).
4. Compilar a resposta em `squads/marca-design-amparo/output/referencias-visuais.md`
   antes de prosseguir para o Step 4. Se o usuário não tiver nenhuma
   referência, registrar isso explicitamente — não é uma falha do
   checkpoint, é uma resposta válida.

## Output Format

```markdown
# Referências Visuais — Amparo

## Referências Fornecidas pelo Usuário
[descrição livre, URLs, nomes de marcas/apps, ou "nenhuma referência
específica fornecida pelo usuário"]

## Notas de Interpretação
[se aplicável: o que o runner entendeu como intenção por trás da
referência, para Flávia não precisar reinterpretar do zero]
```

## Output Example

```markdown
# Referências Visuais — Amparo

## Referências Fornecidas pelo Usuário
Usuário mencionou gostar da paleta de cores de apps de bem-estar mental
(tons pastel/frios) mas pediu para não parecer "genérico demais". Também
citou o link https://example.com/ong-referencia como exemplo de tom
visual acolhedor que considera bem-sucedido, sem necessariamente copiar a
paleta exata. Não há logo específico que o usuário queira usar como base
direta.

## Notas de Interpretação
Interpretação: o usuário busca um tom emocional similar a apps de
bem-estar (calma, acolhimento), mas com identidade visual própria e
distintiva do Amparo — não uma cópia ou "mais um app de bem-estar". Flávia
deve tratar isso como direção de tom, não como restrição de paleta exata.
```

## Output Example (caso sem referências)

```markdown
# Referências Visuais — Amparo

## Referências Fornecidas pelo Usuário
Nenhuma referência visual específica fornecida pelo usuário. Usuário
optou por confiar no framework estratégico de Flávia (brandkit) e na
pesquisa calibrada de Renata para guiar as direções de identidade.

## Notas de Interpretação
Sem restrição externa de referência — Flávia tem liberdade total dentro
dos limites já estabelecidos pelo brief (Step 1) e pela pesquisa de
Renata (Step 2).
```

## Veto Conditions

Reject and redo if ANY of these are true:
1. O usuário não foi explicitamente perguntado sobre referências visuais
   antes do checkpoint ser encerrado.
2. O documento salvo não distingue claramente entre "referência fornecida"
   e "nenhuma referência" — uma resposta ambígua não pode ser registrada
   como se fosse uma das duas sem confirmação.

## Quality Criteria

- [ ] A pergunta aceitou explicitamente texto livre, URLs ou descrição de
      imagens como formatos de resposta válidos.
- [ ] Caso o usuário não tenha referências, isso está registrado de forma
      explícita e não ambígua no arquivo de saída.
- [ ] O arquivo é salvo em `output/referencias-visuais.md` antes de o Step
      4 iniciar.
