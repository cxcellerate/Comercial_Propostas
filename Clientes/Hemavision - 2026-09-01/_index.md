# HemaVision IVD do Brasil — 2026-09-01

Pasta do cliente (padrão CXcellerate: `Clientes/<Empresa> - <AAAA-MM-DD>/`).
Cliente **já ativo** — o site atual (site.hemavision.com.br) foi feito pela CXcellerate.

## Arquivos

- `dossie-hemavision.md` — dossiê (perfil, domínios, contas de e-mail, mapa de ofertas, pontos a confirmar).
- `proposta-hemavision-v2.html` — **VERSÃO VIGENTE** (enxuta, 5 slides), reestruturada em 01/09/2026
  a pedido da Thaís: Capa · Diagnóstico · Escopo (Serviço 01 EZ Prep no site + Serviço 02 migração
  de e-mail) · Investimento · Próximos passos. Sem cronograma, sem opcionais, sem premissas.
  Títulos sóbrios (sem passada hard-copy). É a que se apresenta.
  Slide final: passos = aprovação + escolha de pagamento; janela de migração **04/08 das 20h às 23h**;
  validade **3 dias**. Slide de investimento sem parágrafo de observação (retirado a pedido da Thaís).
- `proposta-hemavision-01-09-26.pdf` e `Proposta-Hemavision-Daniel-01-09-26.pdf` — export em PDF
  da v2 (mesma coisa nos dois arquivos): **A4 paisagem, 5 páginas, 1 slide por página**, no estilo
  dos decks dos outros clientes (barra lateral com o logo, fundo escuro sangrando até a borda,
  imagens decorativas mantidas). **Diferença dos outros:** o número da página incrementa certinho
  (01…05) em vez de ficar preso em "01". O CSS de impressão está embutido no `proposta-hemavision-v2.html`
  (bloco `@media print` — usa contador CSS por slide), então dá pra reimprimir por Ctrl+P → Salvar
  como PDF (A4, paisagem) ou por Chrome headless `--print-to-pdf`.
- `proposta-hemavision.html` — **versão longa antiga** (9 slides, com diagnóstico expandido,
  cronograma, opcionais e premissas). Mantida como referência; **não** foi sincronizada com a v2.
- `produto-ez-prep.pdf` — material técnico do EZ Prep (fonte do conteúdo da página).
- `lista de emails.txt` — 6 contas individuais + 4 endereços de área (apelidos).

## Escopo e valores (definidos pelo cliente)

| Item | Valor | Observação |
|---|---|---|
| Página do EZ Prep no site | **R$ 650,00** | No padrão visual do EZ COLOR 120; conteúdo a partir do PDF; selo "Protótipo — em registro na ANVISA"; CTA "manifestar interesse" (sem compra). |
| Migração de e-mail p/ Google Workspace | **R$ 300,00** | 6 contas; DNS (MX/SPF/DKIM/DMARC) na zona de hemavision.com.br; migração de mensagens; testes. |
| **Total à CXcellerate** | **R$ 950,00** | Pagamento único. |
| Google Workspace Starter | R$ 32,72/usuário/mês | De R$ 40,90 com 20% off por 12 meses. 6 contas = **R$ 196,32/mês**. 14 dias grátis. Pago direto ao Google. Apelidos de área não consomem licença. |

**Formas de pagamento (R$ 950) — atualizado 01/09/2026, sem desconto no Pix:**
Pix à vista R$ 950,00 · Cartão R$ 950,00 + juros da operadora = total R$ 989,48.
(Removida a opção Pix 50+50 e o desconto de 10% do Pix à vista.)

**Cronograma:** removido do deck. Janela de migração de e-mail agendada: **04/08 das 20h às 23h** (no slide final).

**Validade da proposta:** 3 dias (curta — confirmar com a Thaís se é intencional).

## Opcionais (upsell — não fechados)

- Manutenção mensal do site — R$ 200/mês (mesma faixa da AAT).
- SEO/GEO/AEO da página do EZ Prep — **sob escopo** (Thaís precisa precificar).
- Assinaturas de e-mail padronizadas — **sob escopo** (Thaís precisa precificar).

## Histórico de copy

Na 1ª rodada a v2 teve passada hard-copy (frase-marcador de dor, títulos afiados, âncora de valor
"diária de estande em feira", toque final da janela ANVISA). **A Thaís removeu tudo isso em 01/09/2026**
— quis a proposta "bem simples". A v2 vigente tem títulos sóbrios e sem blocos de argumento.

## Pendências antes de fechar

- [ ] Thaís revisar o deck v2 (vigente) e decidir se a versão longa `proposta-hemavision.html` some,
      é atualizada ou fica só como referência.
- [ ] Precificar os dois opcionais "sob escopo" (se ainda quiser oferecê-los — a v2 não os cita).
- [ ] Confirmar com o cliente: texto aprovado sobre estágio ANVISA do EZ Prep; provedor de e-mail
      atual e volume das caixas; acesso ao DNS (Hostinger) e à área admin do site; contato técnico
      para a janela de DNS.
- [ ] IA gerou a proposta — Thaís valida antes de enviar.

## Encerramento

Commit + push para `origin` = github.com/cxcellerate/Comercial_Propostas.git (repo deste diretório).
