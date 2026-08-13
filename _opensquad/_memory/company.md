# Perfil do Projeto

**Nome:** Amparo
**Slogan:** "Você não está sozinha"

## Descrição

Aplicativo de denúncia de violência doméstica contra mulheres, desenvolvido como TCC (trabalho de conclusão de curso).

## Problema central

Mulheres em situação de violência doméstica enfrentam barreiras reais para pedir ajuda: medo do agressor, dependência emocional e financeira, falta de informação sobre seus direitos, vergonha, e ausência de ferramentas discretas e seguras adaptadas ao contexto brasileiro. A subnotificação é um dos maiores obstáculos ao combate efetivo da violência.

## Solução

O Amparo é uma plataforma mobile completa que combina proteção imediata (emergência), documentação segura, rede de apoio pessoal e acesso a profissionais — tudo com design discreto e centrado na segurança da usuária.

## Público-alvo

- Mulheres em situação de risco
- Órgãos e autoridades (polícia, ONGs, assistência social)
- Banca e avaliadores acadêmicos

## Tom de voz

Acolhedor, empático, seguro e claro — linguagem sensível ao tema, sem jargão técnico para o público final.

## Identidade Visual e Design System (FINALIZADO — NÃO ALTERAR)

A identidade visual e o design system do Amparo já foram criados, aprovados
e publicados. Estão em `brand/` (raiz do projeto):

- `brand/design-system.md` — especificação completa (cores hex, tipografia,
  espaçamento, componentes, ícones, linguagem fotográfica, princípios de
  segurança).
- `brand/LogoAmparo.svg` (+ `.png`/`.jpg`) — logotipo vetorial oficial.
- `brand/manual-amparo.pdf` — manual de identidade visual completo.

**Regra vinculante para toda squad e todo agente deste projeto:** estes
arquivos são a fonte única da verdade e estão travados (locked). Nunca
gerar, propor ou sugerir uma cor, fonte, logotipo, espaçamento, ícone ou
tom de voz diferente do documentado em `brand/`. Qualquer tela, componente,
peça gráfica, landing page ou texto de marca produzido por qualquer squad
deve carregar `brand/design-system.md` (e usar `brand/LogoAmparo.svg` como
logo) antes de gerar output visual — nunca reinventar a partir do zero.

## Apresentação Final da Banca (TCC II — 2026-08-13) — FONTE CONFIRMADA

A apresentação final defendida perante a banca (`AMPARO_TCC_Apresentacao.pdf`)
consolida e CONFIRMA o escopo funcional, a arquitetura técnica e os
requisitos não funcionais do protótipo. A partir desta data, as seções
abaixo ("Funcionalidades Core", "Classificação de Risco (IA/ML)", "Stack
Técnica" e "Requisitos Não Funcionais") são decisões de produto já tomadas
— mesmo nível de vinculação que o design system em `brand/`. Nenhuma squad
deve reabrir esses pontos como se fossem ideias em aberto.

## Funcionalidades Core (RF-CORE) — Confirmadas

| ID | Código | Nome | Descrição |
|---|---|---|---|
| RF-CORE-01 | SOS | Botão de Emergência | Acionamento de emergência com localização em tempo real; funciona com a tela bloqueada. |
| RF-CORE-02 | MD | Modo Disfarçado | Camuflagem total do app como calculadora (ou outro disfarce); combinação própria libera a área protegida. |
| RF-CORE-03 | — | Chat com Profissional de Apoio | Canal sigiloso com psicólogos/assistentes sociais/voluntários, sem exigir denúncia formal prévia. |
| RF-CORE-04 | RE | Registro de Evidências (Ocorrência) | Fotos, áudio, vídeo e texto criptografados, com metadados e hash de integridade em nuvem. |
| RF-CORE-05 | RG | Rede de Guardiões | Contatos de confiança acionáveis antes de qualquer denúncia formal. |
| RF-CORE-06 | — | Classificação de Risco (IA/ML) | Modelo experimental de Machine Learning que classifica o nível de risco da usuária e adapta o comportamento do app. Detalhado na seção abaixo. Apoia — mas não substitui — o julgamento da usuária: é mecanismo de apoio, não diagnóstico determinístico. |

Nota sobre o backlog do brainstorm: a "Ideia 10 — Avaliação de risco
estruturada adaptada ao Brasil (Decision Aid Nacional)", do backlog
priorizado da squad `brainstorm-amparo`, era um questionário estruturado
inspirado no myPlan/Danger Assessment. RF-CORE-06 é a implementação
efetivamente confirmada para o protótipo (classificação automática por ML
a partir de eventos registrados no app, não um questionário respondido
pela usuária) — trata-se de uma decisão de produto já tomada, não uma
ideia a repriorizar. Squads de brainstorm futuras não devem reabrir o
conceito central de RF-CORE-06, apenas complementá-lo (ex.: como
apresentar o resultado da classificação à usuária).

## Classificação de Risco (IA/ML) — RF-CORE-06

Implementada com **Decision Tree Classifier** (biblioteca Scikit-learn),
treinada com dados sintéticos e controlados (nunca dados reais de vítimas
na fase acadêmica).

**Variáveis de entrada (X):**
- Quantidade de agressões verbais
- Quantidade de agressões físicas
- Número de ameaças registradas
- Emergências acionadas
- Frequência das ocorrências em determinados períodos

**Variável de saída (y) — classes de risco:** BAIXO, MÉDIO, ALTO.

**Ações do sistema associadas a cada nível** (definem requisitos de UX que
toda squad de fluxos/protótipo deve tratar como transversais, no mesmo
nível de prioridade dos padrões de segurança/discrição já definidos):

| Nível | Ação do sistema |
|---|---|
| BAIXO | Monitoramento discreto e apresentação de informações educativas para a usuária. |
| MÉDIO | Alerta discreto previamente configurado e apresentação de recursos de apoio. |
| ALTO | Mecanismos de emergência priorizados, acesso rápido a recursos de ajuda e proteção reforçada das evidências. |

**Fluxo de integração:** App (React Native) → Backend (NestJS) → API de IA
(Python) → Classificação de Risco. O acionamento explícito de emergência
(RF-CORE-01) segue regras do sistema separadas das decisões do modelo de
ML — a classificação nunca bloqueia nem atrasa o SOS manual.

## Stack Técnica Confirmada

- **App:** React Native + TypeScript (interface camuflada).
- **Backend:** NestJS — autenticação, regras de negócio, ocorrências, contatos e emergências.
- **Dados:** PostgreSQL (metadados) + armazenamento privado de objetos (fotos, áudios, vídeos, evidências).
- **IA:** serviço Python / Scikit-learn (Decision Tree) para RF-CORE-06.
- **Segurança:** HTTPS/TLS em trânsito, criptografia em repouso, controle de acesso, logs e auditoria, URLs temporárias para acesso a evidências.
- **Conformidade:** alinhamento com a LGPD (minimização de dados, finalidade clara, dados sintéticos priorizados na fase acadêmica).

## Requisitos Não Funcionais Confirmados

- Criptografia end-to-end das evidências.
- Baixa latência: geolocalização em ciclos de 30s.
- Discrição energética — sem drenar bateria e levantar suspeita.
- UX projetada para uso sob alto estresse.
- App offline-first (camadas de proteção funcionam mesmo sem conectividade estável — ver fallback de SOS por SMS/USSD já no backlog do brainstorm).

## Uso pretendido do Opensquad

- Documentação do TCC (monografia, relatórios)
- Pesquisa e análise (referências, benchmarking)
- Desenvolvimento back-end
- Desenvolvimento front-end
- Geração de dashboards no Notion
- UX/UI (Figma) para o app mobile
- Brainstorm com visão geral do projeto (ideias de funcionalidades e fluxos)
- Criação de design system e identidade visual de marca
- Criação de sites e landing pages
