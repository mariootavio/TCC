# AMPARO — Design System

> Documento de referência completo do sistema de identidade visual e verbal da AMPARO. Qualquer decisão de UI, copy ou componente deve derivar daqui — nunca usar hex, fonte, espaçamento ou tom de voz fora do que está documentado abaixo.

---

## 1. Identidade do Projeto

| Campo | Valor |
|---|---|
| Nome do projeto | AMPARO |
| Nome nas lojas (App Store / Google Play) | Amparo |
| Slogan oficial | "Você não está sozinha." *(definitivo — nunca alterar)* |
| Tipo | TCC — Ciência da Computação |
| Base legal | Lei Maria da Penha (nº 11.340/2006) e LGPD (nº 13.709/2018) |

**Essência:** Proteção que cabe no bolso, sem se anunciar.

**Conceito criativo:** "O colo que protege sem esconder quem é protegido" — o símbolo da marca abraça, mas nunca oculta a figura humana em seu interior. Toda decisão de produto deve honrar essa tensão: proteger sem esconder, cuidar sem infantilizar, ser discreto sem ser invisível para quem precisa.

---

## 2. Missão, Visão e Valores

**Missão:** Oferecer apoio jurídico e emocional qualificado para mulheres que enfrentam violência, com acolhimento humanizado, orientação segura e ações concretas que promovam proteção, autonomia e reconstrução de vida com dignidade.

**Visão:** Ser referência nacional em apoio integral à mulher em situação de violência, unindo excelência técnica, empatia e inovação para transformar realidades e construir uma sociedade mais justa, segura e respeitosa para todas.

**Valores:**

| Valor | Comportamento concreto |
|---|---|
| Segurança acima de tudo | Protegemos a vida e a integridade em cada ação |
| Discrição radical | Preservamos sigilo com responsabilidade absoluta |
| Autonomia da usuária | Respeitamos escolhas e fortalecemos decisões informadas |
| Rigor técnico e legal | Atuamos com precisão, atualização e ética em tudo que fazemos |

---

## 3. Personalidade e Tom de Voz

**Traços de personalidade** (pares de tensão — nunca resolver só para um lado):

| Traço | Explicação |
|---|---|
| Discreta, mas presente | Apoio silencioso, que está sempre por perto |
| Séria, mas acolhedora | Confiança construída com respeito e empatia |
| Firme, mas gentil | Segurança que protege sem intimidar |
| Técnica, mas humana | Conhecimento que entende pessoas |

**Tom de voz — Diz / Não diz:**

| Diz | Não diz |
|---|---|
| Proteção que faz sentido. | O melhor de todos. |
| Cuidado que acompanha. | Promoção imperdível. |
| Soluções que simplificam. | Sem risco nenhum. |
| Confiança que fica. | Complicado e burocrático. |

**Regra de tom:** o AMPARO nunca promete garantias absolutas (ex.: nunca dizer "100% seguro" ou "total proteção garantida") — isso é irresponsável dado o contexto de risco real dos usuários. A voz é sempre precisa, nunca inflada.

---

## 4. Personas

### Marina — usuária primária *(nome fictício, síntese de pesquisa)*
- **Contexto:** 32 anos, mãe solo, mora em cidade média. Vive situação de violência psicológica e busca apoio com discrição.
- **Medos centrais:** não ser levada a sério; ter sua história exposta ou julgada.
- **Necessidades:** acolhimento empático e sigiloso; informações claras sobre seus direitos e próximos passos.

### Carlos / Ana — guardião *(nome fictício, síntese de pesquisa)*
- **Contexto:** parceiro(a), familiar ou amigo(a) próximo(a). Quer apoiar, mas não sabe como agir sem invadir ou piorar a situação.
- **Medos centrais:** dizer ou fazer algo que cause mais dano; ser visto como intrometido ou parcial.
- **Necessidades:** orientações práticas e seguras; entender limites e formas de apoiar de verdade.

**Tensão de design:** a mesma marca precisa falar duas línguas — discrição para quem protege sua história, clareza imediata para quem pode agir. Nenhuma interface deve resolver essa tensão escolhendo só um lado.

---

## 5. Sistema Cromático

### Cor primária

| Nome | Hex | RGB |
|---|---|---|
| Vinho Amparo | `#954B6E` | 149, 75, 110 |

### Cores secundárias

| Nome | Hex | RGB |
|---|---|---|
| Vinho Profundo | `#4B2A3F` | 75, 42, 63 |
| Malva Suave | `#C58DA8` | 197, 141, 168 |
| Areia Acolhedora | `#F2EAE4` | 242, 234, 228 |

### Cores neutras

| Nome | Hex | RGB | Uso |
|---|---|---|---|
| Grafite Leitura | `#333333` | 51, 51, 51 | Texto corrido — nunca preto puro |
| Cinza Silêncio | `#8E8984` | 142, 137, 132 | Legendas, textos de apoio |
| Branco Base | `#FFFFFF` | 255, 255, 255 | Fundos de card, documentos impressos |

### Cores funcionais (uso restrito — nunca decorativo)

| Nome | Hex | RGB | Uso |
|---|---|---|---|
| Alerta SOS | `#C62828` | 198, 40, 40 | Exclusivo do botão de pânico e alertas críticos |
| Confirmação Guardião | `#2E7D6B` | 46, 125, 107 | Exclusivo de confirmações e ações positivas |

**Regras de combinação:**
- Máximo 2 cores de marca por peça (primária + 1 secundária) + 1 neutro de texto.
- Cores funcionais nunca se combinam esteticamente com a paleta principal — têm função de sistema (feedback de interface), não de identidade visual.
- Vinho Amparo em texto só a partir de 24px (H2) para cima — abaixo disso, contraste insuficiente.
- Fundo escuro padrão: Vinho Profundo com texto em Areia Acolhedora.

---

## 6. Tipografia

| Fonte | Categoria | Pesos | Uso |
|---|---|---|---|
| Quicksand | Títulos e destaques | Medium 500 / SemiBold 600 | Títulos, nome da marca, chamadas de propósito |
| Nunito Sans | Corpo de texto | Regular 400 / SemiBold 600 | Texto corrido, subtítulos, legendas, UI |
| Inter | Dados técnicos e legais | Regular 400 / Medium 500 | Trechos jurídicos, tabelas técnicas, citações ABNT |

**Regra de combinação:** Quicksand para títulos + Nunito Sans para corpo é o padrão. Inter só entra em conteúdo técnico/legal — nunca os três pesos misturados na mesma tela.

### Hierarquia tipográfica

| Nível | Fonte | Peso | Tamanho | Entrelinha |
|---|---|---|---|---|
| H1 — Título | Quicksand | SemiBold 600 | 40px / 2.5rem | 1.2x |
| H2 — Subtítulo | Quicksand | Medium 500 | 24px / 1.5rem | 1.3x |
| H3 — Destaque de dado | Nunito Sans | SemiBold 600 | 18px / 1.125rem | 1.4x |
| Corpo | Nunito Sans | Regular 400 | 16px / 1rem | 1.5x |
| Legenda | Nunito Sans | Regular 400 | 12px / 0.75rem | 1.4x |
| Caption jurídico | Inter | Regular 400 | 11px | 1.4x |

---

## 7. Espaçamento e Raios de Borda

### Espaçamento (grid base 8px)

`4px · 8px · 12px · 16px · 24px · 32px · 40px · 48px · 64px · 80px`

### Raios de borda

| Token | Valor | Uso |
|---|---|---|
| `radius-sm` | 8px | Inputs, chips, badges pequenos |
| `radius-md` | 12px | Cards, botões padrão |
| `radius-lg` | 20px | Modais, painéis grandes |
| `radius-pill` | 999px | Botão SOS (circular), avatares |

---

## 8. Componentes

### Botões

| Componente | Especificação |
|---|---|
| CTA primário | Fundo `#954B6E`, texto branco, altura 48px, radius 12px, peso Nunito Sans SemiBold |
| CTA secundário | Fundo transparente, borda 1.5px `#954B6E`, texto `#954B6E`, mesma altura/radius |
| Botão SOS | Fundo `#C62828`, formato circular (radius-pill), ícone branco centralizado, anel de pulso suave |
| Confirmação | Fundo `#2E7D6B`, mesma estrutura do CTA primário |
| Desabilitado | Opacidade 40% sobre a cor original — nunca cinza genérico |

### Estados de interação

| Estado | Regra |
|---|---|
| Hover | Escurecer a cor base em ~10% |
| Pressed/Active | Escurecer em ~15% + escala 98% |
| Focus (acessibilidade) | Anel de foco 2px na cor `#954B6E` a 40% de opacidade, offset 2px |

### Inputs

- Altura 48px · Radius 8px · Borda 1px `#8E8984`, foco muda borda para `#954B6E`
- Placeholder em Nunito Sans Regular, cor `#8E8984`

### Cards

- Radius 12px · Sombra `0 2px 8px rgba(0,0,0,0.06)` · Padding interno 16px · Fundo branco sobre tela `#F2EAE4`

---

## 9. Sistema de Ícones

**Especificação:** grid 24x24px · traço 1.5pt · cantos arredondados 2pt · estilo linear (outline, nunca preenchido).

**Galeria funcional:**
Botão do Pânico · Modo Disfarçado · Chat Sigiloso · Registro de Evidências · Rede de Guardiões · Proteção · Localização em Tempo Real · Alertas Inteligentes · Check-in Seguro · Relatórios e Insights · Conteúdo de Apoio · Configurações.

**Regra:** todos os ícones compartilham exatamente o mesmo peso de traço, raio de canto e estilo — nunca misturar ícones outline com preenchidos na mesma tela. Sem imagery literal de violência (sem armas, sem símbolos agressivos) — ícones devem transmitir calma e clareza mesmo para quem não conhece o app.

---

## 10. Linguagem Fotográfica

**Diretriz central:** sempre o "depois", nunca o "durante". Fotografia retrata superação, nunca vitimização.

- **Evitar:** sombras dramáticas, isolamento visual, expressões de medo, ambientes escuros, poses de defesa.
- **Buscar:** luz natural, conexão genuína, dignidade, diversidade real (idade, etnia, corpo), momentos cotidianos de confiança e serenidade.
- Nunca mostrar conteúdo de tela do celular visível nas fotos (evita parecer anúncio de produto genérico).

---

## 11. Princípios Inegociáveis (checklist de segurança)

Toda funcionalidade, tela ou peça de comunicação deve passar por este filtro antes de ser aprovada:

- [ ] **Segurança by design** — isso pode colocar a vítima em risco?
- [ ] **Discrição total** — o app revela sua função real em algum momento sem consentimento?
- [ ] **Anonimato** — algum fluxo obriga identificação da vítima?
- [ ] **Apagamento rápido** — dados sensíveis podem ser apagados com um toque?
- [ ] **LGPD** — coleta o mínimo de dados possível, com máxima proteção?
- [ ] **Offline-first** — funcionalidades críticas (SOS, registro local) funcionam sem internet?

Se qualquer item falhar, a funcionalidade não deve ser implementada como está — precisa ser redesenhada.

---

## 12. Funcionalidades Centrais (RF-CORE) — referência de produto

| Código | Nome | Descrição |
|---|---|---|
| RF-CORE-01 | Botão do Pânico / SOS | Emergência com localização em tempo real. Funciona com tela bloqueada. |
| RF-CORE-02 | Modo Disfarçado | Camuflagem de ícone e tela inicial. Troca sem desinstalar. |
| RF-CORE-03 | Chat com Profissional | Canal sigiloso com psicólogos/assistentes sociais. Apagamento em 1 toque. |
| RF-CORE-04 | Registro de Evidências | Texto, foto, áudio e vídeo criptografados, com metadados para uso legal. |
| RF-CORE-05 | Rede de Guardiões | Pessoas de confiança com alertas bidirecionais. |

---

## 13. Regras de Uso do Logotipo (texto — sem asset visual neste documento)

- Nunca distorcer a proporção original.
- Nunca alterar a cor fora da paleta oficial.
- Nunca separar o símbolo externo da figura humana interna.
- Nunca adicionar sombra, brilho, contorno ou gradiente.
- Nunca aplicar sobre fundo que reduza o contraste.
- Nunca reposicionar símbolo e wordmark de forma diferente do padrão.
- Nunca substituir a tipografia do wordmark por outra fonte.
- Nunca rotacionar o símbolo fora do eixo vertical.

---

## 14. Referências Legais e Acadêmicas

- Lei Maria da Penha — nº 11.340/2006, especialmente Art. 5º, 7º e 12º
- LGPD — nº 13.709/2018, especialmente Art. 11 (dados sensíveis) e Art. 46 (segurança)

---

*"Você não está sozinha."*
