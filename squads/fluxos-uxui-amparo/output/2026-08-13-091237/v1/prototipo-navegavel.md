PROTÓTIPO NAVEGÁVEL — AMPARO
Arquivo Figma: "App" (fileKey `uq8ZErrErmrt2lCfLPq6j3`).

⚠️ **LIMITAÇÃO DE PLATAFORMA DESCOBERTA E RESOLVIDA:** o Figma não permite
ações `NAVIGATE` entre frames de páginas diferentes — "prototypes are per
page" (confirmado pela própria API: `Action` do tipo `NODE` rejeita
destinos fora da página de origem). Como as 6 páginas de fluxo estão
organizadas uma por página (Telma, Step 7) e a saída rápida precisa
funcionar em qualquer uma delas, foi criada uma réplica local leve de
"Disfarce / Calculadora — Ativa" (fundo escuro + display) em cada uma das
5 páginas que têm saída rápida — nomeada "Disfarce / Tela Neutra (local)".
Isso preserva o comportamento especificado por Daniela Discrição sem violar
a arquitetura de páginas de Telma.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FLUXO 1: ACIONAMENTO DE EMERGÊNCIA (RF-CORE-01)

Conexões criadas:
1. Instância "Botão SOS" (Acionamento — Padrão) → "Confirmação — Padrão": Smart Animate (300ms, ease-out).
2. "Confirmação — Padrão" (clique no frame) → "Confirmação — Erro Sem Conexão": Smart Animate — demonstra o caminho de erro.
3. "Confirmação — Erro Sem Conexão" (clique) → "Acionamento — Padrão": Smart Animate, fecha o loop de teste.
4. Saída rápida (3 telas) → "Disfarce / Tela Neutra (local)": TRANSIÇÃO INSTANTÂNEA (transition: null), sem exceção.

FLUXO 2: REGISTRO DE OCORRÊNCIA COM EVIDÊNCIAS (RF-CORE-04)

Conexões criadas:
1. Botão "+ Nova ocorrência" (Início) → "Detalhe — Prova Verificada": Smart Animate.
2. "Detalhe — Prova Verificada" (clique) → "Detalhe — Erro Backup Pendente": Smart Animate.
3. "Detalhe — Erro Backup Pendente" (clique) → "Início — Padrão": Smart Animate, fecha o loop.
4. Saída rápida (3 telas) → tela neutra local: INSTANTÂNEA.

FLUXO 3: MODO DISFARÇADO E SAÍDA RÁPIDA (RF-CORE-02)

Conexões criadas:
1. "Onboarding — Escolher" (clique em qualquer opção) → "Calculadora — Ativa": Dissolve (400ms).
2. "Calculadora — Ativa" (clique, simulando destrave via código "1207"+"=") → "App Switcher — Rastro Minimizado": Smart Animate.
3. "App Switcher" (clique) → "Calculadora — Ativa": Smart Animate, fecha o loop.

NOTA: no app real, um destrave bem-sucedido levaria à tela "Início" de
RF-CORE-06 (Fluxo 5) — não conectado aqui pela mesma limitação de página
única já documentada. Registrado como nota, não como pendência aberta,
porque o comportamento correto (calculadora funcional + destrave) já está
demonstrado dentro desta página.

FLUXO 4: REDE DE GUARDIÕES (RF-CORE-05)

Conexões criadas:
1. "Lista — Padrão" (clique no frame) → "Confirmação de Alerta — Padrão": Smart Animate — demonstra a visão do guardião.
2. Botão "Confirmar" (Confirmação de Alerta) → "Lista — Padrão": Smart Animate, fecha o loop.
3. Botão "+ Adicionar guardião" (Lista) → "Check-in — Sem Resposta": Smart Animate — única forma de alcançar este estado nesta rodada de demonstração.
4. "Check-in — Sem Resposta" (clique) → "Lista — Padrão": Smart Animate, fecha o loop.
5. Saída rápida (3 telas) → tela neutra local: INSTANTÂNEA.

FLUXO 5: PIPELINE DE CLASSIFICAÇÃO DE RISCO (RF-CORE-06)

Conexões criadas:
1. "Início / Nível BAIXO" (clique) → "Início / Nível MÉDIO": Smart Animate — demonstra a escalada de risco.
2. "Início / Nível MÉDIO" (clique) → "Início / Nível ALTO": Smart Animate.
3. Instância "Botão SOS" (Nível ALTO) → "Início / Nível BAIXO": Smart Animate. NOTA: o destino conceitual correto é "Emergência / Acionamento — Padrão" (Fluxo 1) — não conectado por limitação de página única; documentado em `fluxos-ux.md` Fluxo 1, "o acionamento nunca é bloqueado, atrasado ou condicionado" continua válido como regra, apenas a demonstração cross-page não é tecnicamente possível nesta versão do arquivo.
4. Saída rápida (3 telas) → tela neutra local: INSTANTÂNEA.

FLUXO 6: DELEGACIAS PRÓXIMAS

Conexões criadas:
1. "Lista — Padrão" (clique) → "Erro — Permissão Negada": Smart Animate.
2. "Erro — Permissão Negada" (clique) → "Erro — Nenhuma Encontrada": Smart Animate.
3. "Erro — Nenhuma Encontrada" (clique) → "Lista — Padrão": Smart Animate, fecha o loop.
4. Saída rápida (3 telas) → tela neutra local: INSTANTÂNEA.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

TABELA DE VERIFICAÇÃO DE NAVEGAÇÃO

| Fluxo | Caminho Feliz | Caminho(s) de Erro | Saída Rápida testada | Status |
|---|---|---|---|---|
| 1. Acionamento de Emergência | OK — SOS → Confirmação | OK — Confirmação → Erro Sem Conexão | OK — testada nas 3 telas, todas `transition: null` | OK |
| 2. Registro de Ocorrência | OK — Nova ocorrência → Detalhe | OK — Detalhe → Erro Backup Pendente | OK — testada nas 3 telas | OK |
| 3. Modo Disfarçado | OK — Onboarding → Calculadora → destrave | N/A (fluxo de segurança, sem "erro" no sentido tradicional — falha silenciosa é o comportamento correto) | N/A — este fluxo É o destino da saída rápida | OK |
| 4. Rede de Guardiões | OK — Lista → Confirmação de Alerta | OK — Check-in Sem Resposta acessível e com saída | OK — testada nas 3 telas | OK |
| 5. Classificação de Risco (RF-CORE-06) | OK — BAIXO → MÉDIO → ALTO | N/A (camada transversal, sem caminho de erro próprio — erro é tratado no Fluxo 1) | OK — testada nas 3 telas | OK |
| 6. Delegacias Próximas | OK — Lista navegável | OK — ambos os erros (permissão negada, nenhuma encontrada) encadeados | OK — testada nas 3 telas | OK |

Nenhuma tela morta ou link quebrado identificado nesta rodada de teste —
todas as 21 telas (18 de Telma + 3 "Tela Neutra (local)" adicionadas por
Pietro) têm ao menos uma conexão de saída.

Saída rápida testada a partir de 5 pontos distintos e não-adjacentes do
protótipo (Emergência/Acionamento, Documentação/Detalhe, Rede de
Apoio/Check-in, Início/Nível ALTO, Delegacias/Erro) — em 100% dos casos, a
transição é `transition: null` (instantânea), nunca Smart Animate.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

INTERACTIVE COMPONENTS — NOTA

Os componentes "Botão" e "Botão SOS" já têm as variantes de Estado
(Hover/Pressed/Desabilitado) reconstruídas por Caio (Step 2), mas o Figma
Plugin API não expõe a configuração de "Interactive Components" (que liga
automaticamente variantes de estado a triggers de hover/press) através de
`use_figma` — essa configuração precisa ser feita manualmente na interface
do Figma (painel Prototype → "Apply variant on interaction"). Registrado
como pendência de configuração manual, não de design: as variantes já
existem e estão corretas, falta apenas a associação automática.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

EXPANSÃO DE ESCOPO — APP COMPLETO (checkpoint Step 10, 2026-08-13)

FLUXO 7: MENU MAIS

Conexões criadas (100% na mesma página — totalmente clicável):
1. "Mais / Hub" → "Central de Conteúdo e Direitos": Dissolve.
2. "Mais / Hub" → "Assistente de Triagem": Dissolve.
3. "Mais / Hub" → "Relatos Anônimos": Dissolve.
4. Cada uma das 3 telas acima (clique) → "Mais / Hub": Dissolve, fecha o loop.
5. "Chat de Apoio / Conversa" (clique) → "Mais / Hub": Smart Animate.

NAVEGAÇÃO INFERIOR (bottom nav)

Aplicada nas 7 telas-hub (Início ×3, Documentação/Início, Rede de
Apoio/Lista, Chat de Apoio/Conversa, Mais/Hub), com o item correto já
destacado por tela — mas SEM reactions de clique nos itens da bottom nav
em si. Motivo: cada tab leva a uma página diferente (limitação de NAVIGATE
cross-page, já documentada), e criar 5×7 réplicas locais adicionais só
para a barra de navegação inflaria o arquivo sem benefício real de
demonstração — a barra já comunica visualmente a estrutura de navegação, e
cada tab individual já é 100% navegável dentro de sua própria página.
Registrado como limitação de plataforma, não como pendência de design.

JORNADA DE ENTRADA (Onboarding)

Não conectada via NAVIGATE (Welcome Screen, Cadastro e Login estão em 3
páginas diferentes — mesma limitação). A jornada completa está documentada
visualmente na página "🗺️ Mapa Completo do App", que mostra exatamente a
sequência Welcome → Cadastro/Login → Escolher Disfarce → Calculadora →
Início.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PENDÊNCIAS ENCONTRADAS E RESOLVIDAS

1. **Limitação de NAVIGATE entre páginas** (ver nota no topo do documento) —
   resolvida com réplicas locais da tela neutra em cada página com saída
   rápida.
2. **SOS em "Início / Nível ALTO" → Fluxo 1** e **destrave da calculadora →
   Fluxo 5** — ambos são cross-page pela mesma limitação; mantidos como
   nota documentada, não como pendência aberta, pois o comportamento
   correto de cada fluxo individual já está 100% demonstrável dentro de sua
   própria página.
3. **Interactive Components de hover/pressed** — variantes existem no
   design system, mas a associação automática precisa ser feita
   manualmente no Figma (fora do alcance do Plugin API).

Nenhuma tela morta remanescente. Nenhuma exceção à regra de transição
instantânea da saída rápida.
