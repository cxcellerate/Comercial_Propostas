---
name: criar-contrato-prestacao-servicos
description: Use quando uma proposta comercial da CXcellerate for aprovada/fechada e for preciso gerar o contrato de prestação de serviços, ou quando pedirem "gerar contrato", "fazer o contrato do cliente X", "formalizar a proposta", "minuta de contrato". Requer pasta do cliente em Clientes/ com proposta e dossiê.
---

# Criar Contrato de Prestação de Serviços — CXcellerate

## Visão geral

Gera a **minuta de contrato de prestação de serviços** da CXcellerate em HTML com papel timbrado da marca, a partir de uma proposta comercial aprovada. Direito brasileiro (Código Civil, arts. 593+; LGPD), **nunca** molde americano/common law.

**Use SEMPRE o template** `contrato-template.html` (mesma pasta desta skill). Ele já contém: timbrado (faixa lateral + aba degradê + marca d'água em cada página A4), qualificação completa da CX Cellerate Ltda, cláusulas fixas da casa e rodapé de contatos. **Não invente layout nem redija contrato do zero.**

## Processo

1. **Ler os insumos** na pasta do cliente (`Clientes/<Empresa> - <AAAA-MM-DD>/`): proposta aprovada (**sempre a versão mais recente** — maior `vN` no nome), `dossie-*.md` (CNPJ, endereço, representantes) e `_index.md` (**fonte de verdade do que foi FECHADO** — valor, desconto e forma de pagamento negociados prevalecem sobre as opções da proposta, mesmo que a forma fechada nem conste dela).
2. **Copiar o template** para `Clientes/<Empresa> - <AAAA-MM-DD>/contrato-<cliente>-prestacao-servicos.html` (`<cliente>` em minúsculas, sem acentos, espaços viram hífens — ex.: `contrato-padaria-trigal-prestacao-servicos.html`).
3. **Substituir TODOS os tokens `{{...}}`** (tabela abaixo) com dados da proposta/dossiê. `{{DATA_PROPOSTA}}` = data na capa da proposta; se não constar, usar a data da pasta do cliente.
4. **QUALQUER dado desconhecido** (CPF, CEP, e-mail de notificações, testemunhas, local/data, materiais, fornecedores...): deixar `<mark>[descrição do campo]</mark>` — vira destaque magenta a preencher antes da assinatura. Nunca inventar.
5. **Atualizar o `_index.md`** do cliente com o arquivo e pendências.
6. **Avisar sempre:** minuta gerada por IA — revisar com advogado antes de celebrar.

## Tokens do template

| Token | Conteúdo | Exemplo (Izalab) |
|---|---|---|
| `{{TITULO_CONTRATO}}` | Objeto resumido (título do h1) | Desenvolvimento de Website e Configuração de E-mail Corporativo |
| `{{DATA_PROPOSTA}}` | Data da proposta (aparece 4×) | 22/06/2026 |
| `{{CLIENTE_NOME_CURTO}}` | Nome fantasia do cliente | Izalab Material Hospitalar |
| `{{CONTRATANTE_RAZAO}}` | Razão social (aparece 2×) | Izalab Material Hospitalar Ltda |
| `{{CONTRATANTE_CNPJ}}` | CNPJ do cliente | 10.744.411/0001-45 |
| `{{CONTRATANTE_ENDERECO}}` | Endereço completo com CEP | Praça Saiqui, 58, Sala 301... |
| `{{CONTRATANTE_REPRESENTANTE_NOME}}` | Representante legal (aparece 2×) | Barbara Souza de Moraes |
| `{{CONTRATANTE_REPRESENTANTE_CPF}}` | CPF ou `<mark>[CPF do(a) representante]</mark>` | — |
| `{{OBJETO_ITENS_HTML}}` | `<li>` por serviço contratado (a, b, c…) | site 10 páginas; painel; SEO/GEO/AEO; e-mail |
| `{{OBJETO_COMPLEMENTOS_HTML}}` | `<li>` 1.2+ — exclusões (opcionais da proposta ficam FORA, contratáveis por aditivo) e limites (ex.: sem e-commerce/ERP) | — |
| `{{PRAZO_TEXTO}}` | Prazo total por extenso | 8 (oito) semanas, sendo 6 de produção e 2 de margem |
| `{{CRONOGRAMA_LINHAS_HTML}}` | `<tr>` por etapa da proposta | PRD+Design 2 sem; Dev 3 sem... |
| `{{VALOR_TOTAL_TEXTO}}` | Valor **CHEIO** (sem desconto) por extenso + o que compreende — o desconto aparece só em 3.2/3.3 | R$ 8.000,00 (oito mil reais), compreendendo... |
| `{{PAGAMENTO_LINHAS_HTML}}` | `<tr>` apenas da(s) forma(s) FECHADA(S) na negociação, com valor final calculado | PIX à vista 10% desc → R$ 7.200,00 |
| `{{PAGAMENTO_COMPLEMENTO}}` | Item 3.3 — condições (desconto vinculado, parcela na assinatura) e SEMPRE terminar com o fallback padrão: "Não realizado o pagamento nessa condição, prevalece o valor integral do item 3.1, em condições de pagamento formalizadas por termo aditivo entre as partes." | — |
| `{{MATERIAIS_KICKOFF}}` | Materiais que o cliente entrega até o kickoff (premissas da proposta) | logo, produtos, domínio... |
| `{{FORNECEDORES_LINHAS_HTML}}` | `<tr>` por fornecedor pago direto pelo cliente | Workspace, Cloudflare, Registro.br |
| `{{EMAIL_NOTIFICACOES_CONTRATANTE}}` | E-mail oficial ou `<mark>[...]</mark>` | — |

## Padrões da casa (já fixos no template — NÃO alterar sem ordem da Thaís)

- **Garantia:** 90 dias, incondicional; régua de defeito = PRD aprovado (cláusula 8).
- **Prazo:** conta do kickoff COM materiais entregues; atraso do cliente prorroga automaticamente (cláusula 2).
- **Pagamento padrão:** PIX à vista com 10% de desconto; desconto vinculado ao pagamento na assinatura. Mora: multa 2% + juros 1% a.m. + IPCA.
- **Propriedade:** entregas/domínio/dados/contas = cliente após quitação; componentes de base CXcellerate = licenciados perpétuos não exclusivos (cláusula 9). Projetos com apps: código-base é da CXcellerate, ver memória `padroes-comerciais-cxcellerate`.
- **LGPD:** cliente = controlador; CXcellerate = operadora durante a execução (cláusula 10).
- **PRD com aprovação tácita:** sem manifestação do cliente em 5 dias úteis após solicitação formal, o PRD considera-se aprovado (cláusula 7.3).
- **Responsabilidade e força maior (cláusula 12 — incluída pós-parecer de 10/07/2026):** obrigação de MEIO (projeções da proposta não são garantia de resultado); responsabilidade da CXcellerate limitada ao valor pago; sem danos indiretos/lucros cessantes; força maior inclui indisponibilidade de plataformas de terceiros.
- **Confidencialidade recíproca (cláusula 13):** 2 anos após o término.
- **Numeração:** Disposições Gerais = cláusula 14ª · Foro = cláusula 15ª.
- **Foro:** Santo André/SP. **Contratada:** CX Cellerate Ltda, CNPJ 65.230.554/0001-20, rep. Thaís Kurünzi (CPF 852.603.042-68).
- **2 testemunhas** (título executivo extrajudicial, art. 784 CPC).
- **Cliente pediu para alterar cláusula fixa** (garantia, foro, propriedade...): gerar a minuta com o padrão da casa, registrar o pedido como pendência no `_index.md` e escalar a decisão à Thaís. Não bloquear a geração, não atender o pedido.

## Checklist final

- [ ] Todos os tokens `{{...}}` substituídos (buscar `{{` no arquivo — zero ocorrências)
- [ ] Valores conferem com a proposta E com o que foi fechado no `_index.md` (desconto negociado prevalece)
- [ ] Opcionais da proposta listados como FORA do objeto (1.2)
- [ ] Pendências em `<mark>` e listadas no `_index.md`
- [ ] Aviso de revisão por advogado dado ao usuário

## Erros comuns

| Erro | Correção |
|---|---|
| Redigir contrato do zero ou usar molde em inglês/common law | Sempre copiar o template desta pasta |
| Usar valores da proposta ignorando a negociação final | O que foi fechado (`_index.md`/conversa) prevalece |
| Incluir os serviços opcionais no objeto | Opcionais ficam na exclusão (1.2), por aditivo |
| Inventar CPF, e-mail ou testemunhas | Campo desconhecido = `<mark>[...]</mark>` |
| Alterar garantia/foro/propriedade "para agradar o cliente" | Padrões da casa; só a Thaís autoriza mudança |
| Editar o arquivo com Write/Edit sem cuidado com os base64 | As linhas da logo/marca d'água são gigantes; substituir tokens via replace pontual |
