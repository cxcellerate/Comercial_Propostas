---
name: pesquisar-cliente-proposta
description: Use quando receber um pedido de orçamento, briefing ou referência de site/serviço de um cliente e precisar pesquisar quem é a empresa antes de propor. Dispara em "fazer orçamento", "montar proposta", "pesquisar o cliente", "quem é essa empresa", "cliente quer um site/CRM/tráfego", ou ao colar o texto do pedido de um prospect.
---

# Pesquisar Cliente e Montar Proposta

## Overview
Workflow de **duas fases** para nunca enviar proposta no escuro: primeiro descobrir quem é o cliente e o que ele realmente precisa; só depois (com as respostas dele em mãos) montar a proposta de serviço.

**Princípio:** proposta sem pesquisa é chute. A Fase 2 NÃO começa antes de o cliente devolver as respostas das perguntas da Fase 1.

## Entrada
A pessoa cola o **texto do pedido do cliente** (livre), por exemplo:
> "Tânia quer um orçamento de site-vitrine para a Izalab Material Hospitalar. Referência: enzipharma.com.br. Quer email corporativo, 10 contas."

Extraia desse texto: contato (quem pediu), empresa, o que foi pedido, referências/links citados e requisitos explícitos (ex: "10 contas de email").

## Pasta do cliente (OBRIGATÓRIO — antes de salvar qualquer arquivo)

Todo arquivo do cliente (dossiê, propostas base e v2) vai para **uma pasta dedicada**, criada no início da Fase 1:

```
Clientes/<Empresa> - <AAAA-MM-DD>/
```

- `<Empresa>` = nome real da empresa (ex: `Izalab Material Hospitalar`).
- `<AAAA-MM-DD>` = data da proposta/atendimento (ordena cronologicamente).
- Pasta-mãe `Clientes/` fica na raiz da área comercial (`CXcellerate Comercial/`).
- **Não** misture arquivos do cliente na raiz nem com assets compartilhados (logo, PNGs decorativos, deck institucional).
- Inclua um `_index.md` curto listando os arquivos e o contexto do cliente.

---

## FASE 1 — Pesquisa + Devolutiva

Faça pesquisa real na web (WebSearch/WebFetch). Não invente dados; o que não achar, marque como "a confirmar".

### 1. Quem é a empresa + entorno
Ramo de atuação, porte, localização, tempo de mercado, sócios/responsáveis (se públicos). E principalmente o **entorno**, que é o que vai gerar as perguntas certas:
- **Modelo de negócio:** como a empresa ganha dinheiro / como vende (varejo, atacado, cotação, assinatura, licitação...).
- **Canais de venda:** privado, varejo, e-commerce, e/ou **setor público (licitação/pregão/SUS)** — busque por "<empresa> licitação/pregão".
- **Abrangência:** local, regional ou nacional (define SEO local x nacional).
- **Concorrentes** diretos e como eles se posicionam online.
- **Exigências do setor** (ex: ANVISA/AFE em saúde, OAB em advocacia, etc.).
- **Presença digital atual:** o que já existe e o que falta.

Identifique as **dores prováveis** a partir disso.

### 2. Domínios (passo-assinatura)
- A empresa tem site? Qual o domínio oficial?
- Quais **outros domínios** a empresa tem (variações `.com`, `.com.br`, lojas)?
- Existe domínio **muito parecido/homônimo** que possa ser confundido? Liste-o e **diferencie** explicitamente.
  - Ex: `izalaboratorio.com.br` parece a Izalab, **mas é um laboratório — empresa diferente.**

**Verificação de registro — OBRIGATÓRIA (nunca pule):**
- Para **todo** domínio citado, sugerido ou candidato, confirme o status de registro em:
  - `https://registro.br/busca-dominio/` (domínios `.br`), **ou**
  - `https://who.is/whois/<dominio>` (ex: `https://who.is/whois/izalab.com.br`)
- Ao verificar, **reporte o titular** quando o domínio estiver registrado (revela homônimos/concorrentes/squatters).
- **NUNCA recomende um domínio sem antes confirmar que está DISPONÍVEL.** Se estiver registrado, diga quem é o dono e sugira **outra** opção — também já verificada. Domínio não verificado = marque "a confirmar", nunca afirme.

### 3. Redes sociais
Instagram, LinkedIn (empresa e sócios), Facebook, YouTube, etc. **Traga os links.** Anote frequência/atividade se relevante.

### 4. Entregável 1 — "Quem é a empresa + O que podemos oferecer"
Monte um dossiê e **salve-o automaticamente como arquivo `.md`** dentro da **pasta do cliente** `Clientes/<Empresa> - <AAAA-MM-DD>/` (ex: `dossie-<empresa>.md`), além de mostrá-lo no chat. O dossiê contém:
- **Perfil da empresa** (achados das etapas 1–3, com links)
- **Domínios** (oficiais + parecidos diferenciados)
- **O que podemos oferecer** — mapeie cada oferta a uma dor real do cliente:

| Oferta | Quando faz sentido |
|--------|--------------------|
| **Site** | vitrine/catálogo, institucional ou e-commerce |
| **SEO / GEO / AEO** | ser achado no Google, em IA generativa e em assistentes de busca |
| **CRM** — CXcellerate **ou** Máquina de Resultados | organizar leads/atendimento e fidelizar |
| **Social media + tráfego pago** | gerar demanda e presença |
| **Email corporativo** | profissionalizar comunicação (qtde de contas conforme pedido) |

Inclua apenas as ofertas pertinentes ao pedido — mas registre as adjacentes como upsell.

### 5. Perguntas para o cliente (devolutiva)
**As perguntas são DERIVADAS da análise do entorno (etapa 1), não um template.** Para cada lacuna ou particularidade que você descobriu sobre AQUELA empresa, gere uma pergunta específica. O cliente só deve responder o que você não conseguiu deduzir da pesquisa.

Como derivar:
- Achou que ela vende por **licitação**? → pergunte se o site deve apoiar canal público, privado ou os dois.
- É **atacado/B2B**? → pergunte se mostra preço ou trabalha por **cotação/orçamento**.
- **Revende marcas**? → pergunte quais fabricantes/exclusividades e se já existe catálogo/SKUs.
- Setor com **regulação** (ANVISA, OAB...)? → pergunte se quer destacar certificações no site.
- Tem **homônimos**? → pergunte sobre marca/identidade para diferenciar.
- Pediu **N e-mails**? → pergunte os setores/nomes das contas e se migra histórico.

**Baseline mínimo** (sempre incluir, adaptado): objetivo do site (aquisição / vitrine-catálogo / venda-ecommerce / institucional); produto/serviço principal e quantidade; atende por e-mail e WhatsApp; concorrentes/funcionalidades de referência; possui domínio, redes e logo.

**Pare aqui.** Entregue dossiê + perguntas e aguarde a devolutiva do cliente.

---

## FASE 2 — Proposta de Serviço (.html)

Inicia **somente** quando a pessoa trouxer as respostas do cliente.

**Use SEMPRE o template padrão** `proposta-template.html` (mesma pasta desta skill). É um deck **horizontal** (scroll lateral) em `.html` único, tema **dark**, com a identidade **CXcellerate**: logo girada na barra lateral (clicável, volta à capa), navegação por setas/teclado e animação de entrada. Não invente layout novo: copie o template para `Clientes/<Empresa> - <AAAA-MM-DD>/proposta-<cliente>.html` (a **mesma pasta do dossiê**) e **substitua todos os tokens `{{...}}`** pelo conteúdo.

**Os 9 slides** (já vêm montados, com imagens decorativas padrão embutidas em base64):
1. **Capa** — `{{TITULO_PROPOSTA}}`, `{{SUBTITULO}}`, `{{CLIENTE}}`, `{{CONTATO}}`, `{{DATA}}`, `{{PROPONENTE}}`
2. **Diagnóstico** (resumo do dossiê) — `{{DIAGNOSTICO}}` (parágrafos `<p>…</p>`)
3. **Objetivo** (respostas do cliente) — `{{OBJETIVOS}}` (itens `<li>…</li>`)
4. **Escopo incluído** — `{{ESCOPO_INCLUIDO}}` (bloco `.numbered` ou `<li>`)
5. **Escopo opcional / upsell** — `{{ESCOPO_OPCIONAL}}` (`.grid3` de `.card` ou `<li>`)
6. **Cronograma** — `{{CRONOGRAMA}}`
7. **Investimento** (2 colunas, `align-items:start`) — **esquerda:** `{{INVESTIMENTO}}` (tabela de valores em `width:100%` + total em `.stat`) e `{{ARGUMENTO_VALOR}}` (bloco de argumento de valor — **só no v2**, vazio na base); **direita:** `{{FORMAS_PAGAMENTO}}` (card "Formas de pagamento" e, se houver, card "Pagamento para fornecedores" empilhado abaixo); `{{OBS_INVESTIMENTO}}`
8. **Premissas** (o que o cliente deve enviar) — `{{PREMISSAS}}` (itens `<li>…</li>`)
9. **Próximos passos** — `{{FRASE_FINAL}}` (ex.: "acelerar"/"começar"), `{{PROXIMOS_PASSOS}}` (`<li>`), `{{ARGUMENTO_FINAL}}` (toque final na dor — **só no v2**, vazio na base), `{{VALIDADE}}`, `{{CONTATO_PROPONENTE}}`

Tokens que recebem **HTML** (não texto cru): `{{DIAGNOSTICO}}`, `{{OBJETIVOS}}`, `{{ESCOPO_INCLUIDO}}`, `{{ESCOPO_OPCIONAL}}`, `{{CRONOGRAMA}}`, `{{INVESTIMENTO}}`, `{{FORMAS_PAGAMENTO}}`, `{{ARGUMENTO_VALOR}}`, `{{PREMISSAS}}`, `{{PROXIMOS_PASSOS}}`, `{{ARGUMENTO_FINAL}}`, `{{CONTATO_PROPONENTE}}`.

**Tokens de argumento (`{{ARGUMENTO_VALOR}}` e `{{ARGUMENTO_FINAL}}`):** ficam **vazios na base** (`proposta-<cliente>.html`) e só são preenchidos no **v2** via `hard-copy`. Padrão visual: bloco com barra magenta à esquerda —
```html
<blockquote style="margin:22px 0 0;padding:6px 0 6px 18px;border-left:3px solid var(--magenta)">
  <p class="muted" style="margin:0 0 14px;line-height:1.65"><strong style="font-size:22px;color:#fff">Frase-âncora de dor.</strong> Continuação no tom muted…</p>
  <p style="margin:0;line-height:1.65"><strong style="color:var(--magenta)">Número/comparação</strong> que torna o valor irrisório…</p>
</blockquote>
``` Use as classes prontas do template (`.numbered`/`.nrow`/`.n`, `.grid3`/`.card`, `table`, `.stat`, `<ul><li>`) — veja exemplos no `proposta-izalab-apresentacao.html` da CXcellerate, que é a referência viva do modelo.

**Imagens:** o template já traz imagens decorativas abstratas como padrão — mantenha-as salvo se houver imagem mais adequada ao cliente. A diagramação é fixa e **não deve ser quebrada**:
- **Duas colunas** (texto à esquerda + imagem à direita) nos slides Diagnóstico, Opcional e Premissas: `<img …object-fit:contain>` dentro de `.right-graphic` — a imagem aparece **inteira**.
- **Imagem de fundo à direita** nos slides Objetivo, Escopo e Próximos passos: `background-size:contain`, `background-position:right center`, **sem** gradiente cobrindo o lado esquerdo. O título pode ficar por cima (já tem `z-index` maior).
- PNGs decorativos são **transparentes** e se fundem com o fundo `#1a1a1a` — nunca use `cover` (corta a imagem) nem gradiente de "sombra" à esquerda.

**Design:** fixo no template (marca CXcellerate: fundo `#1a1a1a`, cyan `#01E1C4`, blue `#0160F0`, magenta `#FF008C`; magenta para destacar a palavra-chave do título), **sem emojis**. Valores/prazos indefinidos = `[PREENCHER]`. **Não** use as cores do cliente — a proposta é assinada pela CXcellerate.

### Entrega — SEMPRE duas versões (base + hard-copy)

Toda proposta sai em **dois arquivos**, e os **dois** são entregues:

1. **`proposta-<cliente>.html`** — versão **base**: template preenchido com copy neutra e factual. Fica **intacta**.
2. **`proposta-<cliente>-v2.html`** — **cópia** da base com uma **revisão de copy persuasiva** aplicada via skill **`hard-copy`** (invoque `/hard-copy` antes de revisar). Edite **só o v2**, nunca a base.

Como aplicar o hard-copy numa proposta B2B (adapte os princípios, **sem** virar VSL de guru — mantenha o tom profissional CXcellerate, sem gírias/"isso não é a Disney"):
- **Dor primeiro, no Diagnóstico:** abra com a dor semelhante / custo da invisibilidade ("quando o comprador procura, encontra o concorrente — não você").
- **Venda o processo, não o sonho:** troque promessas vagas por o que será feito e o resultado concreto ("gera pedido de orçamento todo dia", "em 8 semanas no ar").
- **Uma frase de impacto (toque na dor):** insira **uma** linha curta e memorável em `<strong class="mag">` no Diagnóstico — é o "marcador" que diferencia o v2 da base.
- **Toque final na dor no Encerramento:** custo de não agir + prazo ("cada semana sem site é orçamento que vai pro concorrente").
- **Anti-hype:** nada de milagre nem comparação de preço exagerada.

**Fórmulas validadas (use no `{{ARGUMENTO_VALOR}}` e `{{ARGUMENTO_FINAL}}`):**
- **Âncora de valor (Investimento) — encolher o preço + custo da ausência.** Frase-âncora de dor em destaque (branco, maior) + comparação que torna o valor irrisório:
  - *"**Estar fora do digital também tem preço** — só que esse você paga sem perceber: todo comprador que pesquisa seu nome, não acha nada e fecha com o concorrente que aparece. Essa conta roda todo dia, de graça pra eles."*
  - *"**R$ X por dia**, durante 1 ano, é menos que um lanche na padaria da esquina, para o seu negócio deixar de ser invisível. Um único pedido fechado no ano inteiro já devolve o site inteiro — e ainda sobra."* (divida o preço total por 365 para achar o "R$ X/dia").
  - Regra: **uma** comparação só (R$/dia + "um pedido paga"). Empilhar 3-4 comparações liga o "modo planilha" e o cliente questiona cada número.
- **Toque final (Próximos passos / Encerramento) — urgência que vem do mercado, não do vendedor:**
  - *"Cada mês sem site é mais um mês de busca indo para o concorrente — e o espaço nas IAs, hoje aberto, sendo ocupado. Quanto antes a `<empresa>` entrar, mais cedo passa a ser encontrada e recomendada."*
  - *"Enquanto a decisão espera, o comprador não. `<canais do cliente>` estão pesquisando fornecedor hoje — e fechando com quem aparece. Em N semanas a `<empresa>` entra no digital pronta para ser encontrada, comparada e escolhida. O melhor dia para começar era no mês passado. O segundo melhor é **hoje**."*
  - **Sem escassez fabricada** ("últimas vagas", contagem regressiva): numa proposta B2B queima credibilidade. A urgência real (o comprador pesquisando agora) já basta.

**Verificação obrigatória da entrega** (prova de que os dois arquivos diferem): a frase-marcador deve aparecer **0× na base** e **1× no v2**:
```
grep -c "<trecho único da frase-marcador>" proposta-<cliente>.html        # esperado: 0
grep -c "<trecho único da frase-marcador>" proposta-<cliente>-v2.html     # esperado: 1
```

---

## Quick Reference (checklist)
**Fase 1**
- [ ] Criei a pasta `Clientes/<Empresa> - <AAAA-MM-DD>/` (todos os arquivos do cliente vão nela)
- [ ] Extraí contato, empresa, pedido, referências e requisitos do texto
- [ ] Quem é a empresa + dores do nicho
- [ ] Domínios oficiais + parecidos diferenciados
- [ ] Cada domínio citado/sugerido VERIFICADO no registro.br ou who.is (com titular se registrado)
- [ ] Nenhum domínio recomendado sem confirmar disponibilidade
- [ ] Links das redes sociais
- [ ] Dossiê salvo como `.md` dentro da pasta do cliente (além do chat)
- [ ] Dossiê com ofertas mapeadas às dores
- [ ] Perguntas para o cliente — e PAREI para aguardar resposta

**Fase 2**
- [ ] Recebi as respostas do cliente
- [ ] Copiei o `proposta-template.html` e substituí TODOS os tokens `{{...}}` (9 slides)
- [ ] Tokens de HTML preenchidos com as classes prontas do template
- [ ] Imagens inteiras (`contain`, sem `cover` nem gradiente cortando à esquerda) — diagramação não quebrada
- [ ] Marca CXcellerate preservada (fundo `#1a1a1a`, sem cores do cliente, sem emojis)
- [ ] Campos indefinidos marcados como `[PREENCHER]`
- [ ] Gerei a versão **base** `proposta-<cliente>.html` (copy neutra, intacta) — `{{ARGUMENTO_VALOR}}` e `{{ARGUMENTO_FINAL}}` **vazios**
- [ ] Invoquei `/hard-copy` e gerei o **`-v2.html`** com a revisão persuasiva (edição só no v2) — argumentos de valor/urgência preenchidos no `{{ARGUMENTO_VALOR}}`/`{{ARGUMENTO_FINAL}}`
- [ ] Frase-marcador verificada: **0×** na base, **1×** no v2 (`grep -c`)
- [ ] Entreguei os **dois** arquivos (base + v2)

## Erros comuns
- **Pular a pesquisa e ir direto pra proposta** → a Fase 2 depende da devolutiva; não antecipe.
- **Confundir a empresa com um homônimo** → sempre cheque domínios parecidos e diferencie.
- **Recomendar domínio sem verificar** → erro grave; sempre confirme em registro.br/who.is antes de sugerir. Registrado = mostre o titular e ofereça outra opção verificada.
- **Inventar dados** → o que não achou é "a confirmar", nunca chute.
- **Oferecer tudo sem mapear à dor** → cada oferta precisa de um "por quê" ligado ao cliente.
- **Imagem cortada ou com gradiente de "sombra"** → use `object-fit:contain` (duas colunas) ou `background-size:contain` (fundo à direita); nunca `cover` nem gradiente cobrindo o lado esquerdo da imagem.
- **Trocar o design pelo do cliente** → o deck é dark `#1a1a1a` da CXcellerate; nunca aplique a paleta do cliente.
