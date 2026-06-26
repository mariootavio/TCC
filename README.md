# Amparo

> "Você não está sozinha."

Amparo é um aplicativo mobile de denúncia e proteção contra a violência doméstica, desenvolvido como Trabalho de Conclusão de Curso (TCC). Este repositório reúne toda a documentação acadêmica, pesquisa, identidade visual, design de UX/UI e ferramentas de apoio usadas na construção do projeto.

## O problema

Mulheres em situação de violência doméstica enfrentam barreiras reais para pedir ajuda: medo do agressor, dependência emocional e financeira, falta de informação sobre seus direitos, vergonha e ausência de ferramentas discretas e seguras adaptadas ao contexto brasileiro.

- Estima-se que **61% das vítimas não denunciam** (subnotificação) — DataSenado.
- Em 2025, o Brasil registrou **1.568 feminicídios**, novo recorde histórico — FBSP.
- **64–66% dos feminicídios** ocorrem dentro da própria residência da vítima.
- Apenas **24%** das brasileiras dizem conhecer bem a Lei Maria da Penha.

A subnotificação não reflete ausência de violência — reflete ausência de um canal acessível, seguro e discreto para denunciar.

## A solução

O Amparo é uma plataforma mobile que combina:

- **Emergência** — acionamento rápido em situação de risco.
- **Documentação segura de evidências** — registro de provas protegido contra acesso do agressor.
- **Rede de apoio pessoal** — contatos de confiança acionáveis em poucos toques.
- **Acesso a profissionais e órgãos competentes** — polícia, ONGs e assistência social.
- **Modo discreto** — design e fluxos pensados para não expor a usuária: saída rápida em 1 toque, notificações neutras e atenção ao rastro deixado no histórico do aparelho.

O design segue uma abordagem trauma-informada (paleta calma, sem imagética de alarme ou de violência) e princípios de acessibilidade (WCAG 2.2 AA).

## Público-alvo

- Mulheres em situação de risco
- Órgãos e autoridades (polícia, ONGs, assistência social)
- Banca e avaliadores acadêmicos do TCC

## Estrutura do repositório

```text
squads/
  tcc-documentacao/        # Pesquisa acadêmica, dados, legislação, benchmarking e redação do TCC
  design-ux-ui-amparo/     # Identidade visual, design system, UX e UI de alta fidelidade no Figma
_opensquad/
  _memory/company.md       # Perfil e contexto central do projeto Amparo
dashboard/                 # Escritório Virtual — visualização em tempo real da execução dos squads
skills/                    # Skills reutilizáveis (geração de imagens, publicação, templates, etc.)
```

## Como o projeto é construído

O desenvolvimento do Amparo — pesquisa, documentação acadêmica e design — é orquestrado com **Opensquad**, um framework de squads de agentes de IA. Cada squad reúne agentes especialistas que colaboram em um pipeline com checkpoints de aprovação:

- **Documentação TCC** (`tcc-documentacao`) — pesquisa dados sobre violência doméstica no Brasil, legislação aplicável (Lei Maria da Penha e correlatas), benchmarking de apps similares (PenhaS, Circle of 6, bSafe), constrói a argumentação de defesa e consolida tudo em monografia (DOCX/PDF) seguindo as normas ABNT vigentes.
- **Design UX/UI** (`design-ux-ui-amparo`) — define identidade visual de marca, design system, arquitetura de informação, fluxos de UX (com foco em segurança e discrição) e telas de alta fidelidade com protótipo navegável no Figma.

### Comandos principais

Abra esta pasta no seu IDE com o Claude Code e digite:

```text
/opensquad
```

Para executar um squad diretamente:

```text
/opensquad execute o squad tcc-documentacao
/opensquad execute o squad design-ux-ui-amparo
```

### Escritório Virtual

Interface visual 2D que mostra os agentes trabalhando em tempo real:

```bash
npx serve squads/<nome-do-squad>/dashboard
```

Depois abra `http://localhost:3000` no navegador.

---

*Projeto acadêmico (TCC). Dados e fontes de pesquisa em `squads/tcc-documentacao/pipeline/data/research-brief.md`.*
