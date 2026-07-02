# Nuvemshop + Asaas — Pesquisa Técnica para E-commerce
> Documento gerado em 01/07/2026 | Fonte: dev.nuvemshop.com.br + docs.asaas.com

---

## 1. Visão Geral da Plataforma

- **Dev Hub:** https://dev.nuvemshop.com.br
- **Portal de Parceiros:** https://partners.nuvemshop.com.br
- **API Docs Asaas:** https://docs.asaas.com

### Tipos de Aplicativos

| Tipo | Descrição | Requisito |
|------|-----------|-----------|
| **Incorporado** | Roda dentro do painel admin via iframe | Nimbus obrigatório |
| **Externo (Standalone)** | Roda fora do admin, independente | OAuth 2 |

### Ferramentas do Ecossistema

| Ferramenta | Função |
|-----------|--------|
| **API Nuvemshop** | REST pública para dados da loja |
| **NubeSDK** | Toolkit storefront/checkout (Web Workers) |
| **Nexo** | Comunicação app incorporado ↔ admin |
| **Nimbus** | Design system open-source |
| **Templates** | Boilerplates React + Node.js com auth |

### ⚠️ Prazos Críticos — NubeSDK
- **05/06/2026** ✅ NubeSDK obrigatório na homologação
- **30/08/2026** Novas instalações bloqueadas sem SDK
- **30/10/2026** Início da deprecação de apps legados

---

## 2. Autenticação Nuvemshop (OAuth 2)

### Fluxo Authorization Code

```bash
# Passo 1 — Redirecionar lojista para autorização
https://www.tiendanube.com/apps/{app_id}/authorize

# Passo 2 — Trocar code por token
curl -X POST "https://www.tiendanube.com/apps/authorize/token" \
  -d "client_id=APP_ID" \
  -d "client_secret=CLIENT_SECRET" \
  -d "code=CODE_RECEBIDO"
```

### Resposta
```json
{
  "access_token": "88a2fdd17e10327ed96f4f2dc96b00bca60dfe60",
  "token_type": "bearer",
  "scope": "write_products",
  "user_id": 2093261
}
```

### Características
- Token **não expira** — válido até desinstalação ou revogação
- `user_id` = ID da loja (obrigatório em todos os requests)
- Mudança de escopos exige reinstalação do app

### Headers Obrigatórios
```
Authorization: Bearer {access_token}
User-Agent: NomeDoApp (email@dominio.com)
Content-Type: application/json  ← apenas em POST/PUT
```

### Escopos Principais

| Escopo | Acesso |
|--------|--------|
| `read_products` / `write_products` | Produtos e categorias |
| `read_orders` / `write_orders` | Pedidos |
| `read_customers` / `write_customers` | Clientes |
| `read_shipping` / `write_shipping` | Envios |
| `read_payments` / `write_payments` | Pagamentos |
| `write_scripts` | Scripts no storefront (requer NubeSDK) |

---

## 3. API REST Nuvemshop

### Base URLs
```
https://api.nuvemshop.com.br/v1/{store_id}/
https://api.tiendanube.com/v1/{store_id}/
```

### Endpoints Principais

```bash
# Produtos
GET    /products
POST   /products
GET    /products/{id}
PUT    /products/{id}
DELETE /products/{id}
POST   /products/{id}/variants

# Categorias
GET    /categories
POST   /categories

# Pedidos
GET    /orders
GET    /orders/{id}
PUT    /orders/{id}
POST   /orders/{id}/fulfill

# Clientes
GET    /customers
POST   /customers
GET    /customers/{id}
PUT    /customers/{id}

# Cupons
GET    /coupons
POST   /coupons
DELETE /coupons/{id}

# Webhooks
GET    /webhooks
POST   /webhooks
DELETE /webhooks/{id}

# Scripts (storefront)
GET    /scripts
POST   /scripts
DELETE /scripts/{id}

# Loja
GET    /store
PUT    /store
```

### Criar Produto — Exemplo
```bash
curl -X POST \
  -H 'Authorization: Bearer ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (email@dominio.com)' \
  -d '{"name": "Produto Teste", "price": "99.90", "stock": 100}' \
  https://api.nuvemshop.com.br/v1/STORE_ID/products
```

### Webhooks — Eventos Disponíveis
```
app/installed, app/uninstalled
order/created, order/updated, order/paid, order/cancelled
product/created, product/updated, product/deleted
customer/created, customer/updated
```
> ⚠️ Webhooks LGPD são **obrigatórios** para homologação no Brasil

---

## 4. NubeSDK — Storefront e Checkout

### Instalação
```bash
npm install @tiendanube/nube-sdk-types
npm install @tiendanube/nube-sdk-jsx
```

### Estrutura Principal
```typescript
import type { NubeSDK } from "@tiendanube/nube-sdk-types";

export function App(nube: NubeSDK) {
  nube.on("evento", handler);           // escutar eventos
  nube.send("ação", modifier);          // disparar ações
  nube.render("slot_name", component);  // renderizar UI
  nube.getState();                      // ler estado atual
  nube.getBrowserAPIs();                // storage, navegação
  nube.clearSlot("slot_name");          // limpar slot
}
```

### Eventos — Carrinho

| Evento | Direção | Descrição |
|--------|---------|-----------|
| `cart:update` | Loja→App | Carrinho atualizado |
| `cart:validate` | App→Loja | Validar carrinho |
| `cart:add` | App→Loja | Adicionar item |
| `cart:add:success` / `cart:add:fail` | Loja→App | Resultado |
| `cart:remove` | App→Loja | Remover item |
| `cart:remove:success` / `cart:remove:fail` | Loja→App | Resultado |

### Eventos — Checkout

| Evento | Direção | Descrição |
|--------|---------|-----------|
| `checkout:ready` | Loja→App | Nova página de checkout |
| `order:update` | Loja→App | Pedido concluído (success) |
| `order:add:tracking_statuses` | App→Loja | Adicionar rastreio |

### Eventos — Frete

| Evento | Direção | Descrição |
|--------|---------|-----------|
| `shipping:update` | Loja→App | Método de envio alterado |
| `shipping:select` | App→Loja | Selecionar frete por código |
| `shipping:update:label` | App→Loja | Customizar labels de frete |

### Eventos — Cupons

| Evento | Direção |
|--------|---------|
| `coupon:add` / `coupon:remove` | App→Loja |
| `coupon:add:success` / `coupon:add:fail` | Loja→App |

### Eventos — Navegação

| Evento | Descrição |
|--------|-----------|
| `location:updated` | Mudança de página (product, category, home) |
| `quickbuy:open` / `quickbuy:close` | Modal de compra rápida |

### Configuração do Script
```typescript
nube.send("config:set", () => ({
  config: {
    has_cart_validation: true,
    disable_shipping_more_options: false
  }
}));
```

### UI Slots — Checkout

| Slot | Páginas |
|------|---------|
| `before_main_content` | start, payment |
| `after_main_content` | start, payment |
| `after_line_items` | start, payment |
| `after_line_items_price` | start, payment |
| `after_contact_form` | start |
| `after_address_form` | start |
| `after_billing_form` | start |
| `before_payment_options` / `after_payment_options` | payment |
| `before_shipping_form` / `after_shipping_form` | start |
| `after_shipping_description` | start |

### UI Slots — Storefront
> ⚠️ Funciona apenas com tema **Patagonia**. Outros temas usam modelo legado.

| Slot | Páginas |
|------|---------|
| `before_main_content` | home, product, category, search |
| `after_product_detail_name` | product |
| `before_product_detail_add_to_cart` | product |
| `after_product_detail_add_to_cart` | product |
| `before_quick_buy_add_to_cart` | home, category, search |
| `after_product_grid_item_name` | home, category, search |
| `product_grid_item_image_top_left` / `_top_right` | home, product, category, search |
| `product_grid_item_image_bottom_left` / `_bottom_right` | home, product, category, search |
| `before_start_checkout_button` | home, product, category, search |

### UI Slots — Fixos (Overlays)

| Slot | Descrição |
|------|-----------|
| `corner_top_left` / `corner_top_right` | Cantos superiores |
| `corner_bottom_left` / `corner_bottom_right` | Cantos inferiores |
| `modal_content` | Dialog/modal (fecha com ESC ou clique fora) |

### Exemplo — Validação de Carrinho
```typescript
export function App(nube: NubeSDK) {
  nube.send("config:set", () => ({
    config: { has_cart_validation: true }
  }));

  nube.on("cart:update", ({ cart }) => {
    const isValid = cart.items.length >= 1;
    nube.send("cart:validate", () => ({
      cart: {
        validation: isValid
          ? { status: "success" }
          : { status: "fail", reason: "Carrinho vazio!" }
      }
    }));
  });
}
```

### Exemplo — Tracking de Pedido
```typescript
nube.send("order:add:tracking_statuses", () => ({
  order: {
    tracking_statuses: [
      {
        type: "packed",  // "packed" | "shipped" | "shipping_failure"
        title: "Pedido embalado e pronto para envio",
        timestamp: new Date().toISOString()
      },
      {
        type: "shipped",
        title: "Enviado via transportadora",
        timestamp: new Date().toISOString()
      }
    ]
  }
}));
```

---

## 5. Nexo — Comunicação com Admin (Apps Incorporados)

```bash
npm install @tiendanube/nexo
```

### Inicialização
```typescript
import nexo from "@tiendanube/nexo";
const instance = nexo.create({ clientId: "SEU_APP_ID", log: true });
export default instance;
```

### Helpers Disponíveis

| Helper | Retorno | Descrição |
|--------|---------|-----------|
| `connect(nexo)` | `Promise<void>` | Aguardar admin pronto |
| `iAmReady(nexo)` | `void` | Notificar app renderizado |
| `getSessionToken(nexo)` | `Promise<string>` | JWT para backend |
| `getStoreInfo(nexo)` | `Promise<StoreInfo>` | id, nome, URL, país, moeda |
| `getIsMobileDevice(nexo)` | `Promise<boolean>` | Detectar mobile |
| `goTo(nexo, path)` | `void` | Navegar no admin |
| `syncPathname(nexo, path)` | `void` | Sincronizar rota com URL |
| `navigateExit(nexo)` | `void` | Sair do app |
| `getFeatureStatus(nexo, key)` | `Promise<StoreFeatureResponse>` | Feature por plano |
| `runWithUpsell({...})` | `Promise<void>` | Ação atrás de upsell |

### Exemplo Completo — App Incorporado
```typescript
import { ErrorBoundary, connect, iAmReady, create } from "@tiendanube/nexo";

const nexo = create({ clientId: "SEU_APP_ID", log: true });

const App = () => {
  const [isConnect, setIsConnect] = useState(false);

  useEffect(() => {
    connect(nexo).then(() => {
      setIsConnect(true);
      iAmReady(nexo);
    });
  }, []);

  if (!isConnect) return <div>Conectando...</div>;

  return (
    <ErrorBoundary nexo={nexo}>  {/* OBRIGATÓRIO */}
      <BrowserRouter>
        {/* seu app */}
      </BrowserRouter>
    </ErrorBoundary>
  );
};
```

---

## 6. Templates de Aplicativo

| Template | Stack | Uso |
|---------|-------|-----|
| `integrated` | React + Express + Node.js | App incorporado ao admin |
| `external` | React + Express + Node.js | App externo/standalone |

### Setup
```bash
git clone https://github.com/TiendaNube/app-templates-nodejs-express-react
cp .env.example .env
# Preencher: APP_ID, CLIENT_SECRET, APP_URL
```

---

## 7. Funcionalidades Admin — Mapeamento

| Funcionalidade | Status | Como Obter |
|----------------|--------|-----------|
| **Faturamento** | ⚠️ Parcial | Relatórios nativos. Fiscal via Asaas/Bling/Tiny |
| **Gestão Financeira** | ⚠️ Parcial | Relatórios de vendas, cohort, exportação. DRE/fluxo de caixa via ERP externo |
| **Notas Fiscais NFS-e** | ❌ Não nativo | Integrar com Asaas (recomendado), Bling ou Tiny |
| **Open API** | ✅ Nativo | REST completa + OAuth 2 |
| **Estoque** | ✅ Nativo | Campo `stock` em produtos/variantes. Ações em massa no plano Impulso+ |
| **Print Route** | ❌ Não nativo | Construir via API: buscar pedidos → gerar PDF externamente |

---

## 8. Transporte e Logística — Mapeamento

| Funcionalidade | Status | Detalhe |
|----------------|--------|---------|
| **Rastreamento** | ✅ Nativo | Nuvem Envio: Correios, Jadlog, Loggi. NubeSDK: `order:add:tracking_statuses` |
| **Romaneio** | ⚠️ Parcial | Nuvem Envio Collect centraliza operação. Formal: construir via API |
| **Callback / Webhook** | ✅ Nativo | Obrigatório para homologação. Eventos de pedido, pagamento, envio |
| **Regras de Frete** | ✅ Nativo | Por região, peso, valor. NubeSDK: `shipping:update:label`, `shipping:select` |
| **Transportadoras** | ✅ Nativo + Apps | Nuvem Envio: Correios, Jadlog, Loggi + 30+. Apps: Melhor Envio, Frenet (160+) |

### Nuvem Envio — Nativo
- Gestão de fretes, etiquetas e rastreamento no painel
- Sem mensalidade — saldo pré-pago por etiqueta
- 77% das entregas em até 2 dias (2024)

---

## 9. Integração Asaas — Pagamentos e NFS-e

### Sobre o Asaas
- Fintech regulada pelo **Banco Central do Brasil**, certificada **PCI-DSS**
- API Docs: https://docs.asaas.com
- Sandbox: https://sandbox.asaas.com

### Autenticação Asaas
```
Header: access_token: SUA_API_KEY
Sandbox: https://api-sandbox.asaas.com/v3/
Produção: https://api.asaas.com/v3/
```

### 9.1 Meios de Pagamento
- PIX, Boleto, Cartão de crédito/débito, TED
- Parcelamento, link de pagamento, split de pagamentos
- Assinaturas recorrentes, cofre de cartão, antecipação de recebíveis

### Criar Cliente
```bash
POST /v3/customers
{
  "name": "Nome do Cliente",
  "cpfCnpj": "12345678901",
  "email": "cliente@email.com",
  "phone": "11999999999",
  "externalReference": "NUVEMSHOP_CUSTOMER_ID"
}
```

### Criar Cobrança
```bash
POST /v3/payments
{
  "customer": "cus_ID",
  "billingType": "PIX",
  "value": 150.00,
  "dueDate": "2026-07-15",
  "description": "Pedido #12345",
  "externalReference": "NUVEMSHOP_ORDER_12345",
  "discount": { "value": 10, "dueDateLimitDays": 0 },
  "interest": { "value": 2 },
  "fine": { "value": 5 }
}
```

> Dica: Use `externalReference` com o ID do pedido Nuvemshop para rastreamento.

### 9.2 Notas Fiscais (NFS-e)
> Apenas para Pessoa Jurídica. Informações fiscais configuradas previamente na conta.

#### Fluxo de Emissão
```
1. GET  /v3/municipalities/{id}/settings   → Configurações da prefeitura
2. POST /v3/municipalities/{id}/settings   → Criar config municipais
3. GET  /v3/municipalities/{id}/services   → Listar serviços municipais
4. POST /v3/invoices                       → Agendar nota fiscal
5. POST /v3/invoices/{id}/authorize        → Emitir antecipadamente
```

#### Agendar Nota Fiscal
```bash
POST /v3/invoices
{
  "payment": "pay_ID_COBRANCA",
  "serviceDescription": "Venda de produto",
  "observations": "Pedido Nuvemshop #12345",
  "externalReference": "NUVEMSHOP_ORDER_12345",
  "value": 150.00,
  "deductions": 0,
  "effectiveDate": "2026-07-15",
  "municipalServiceId": "203561",
  "municipalServiceName": "Comércio de mercadorias",
  "updatePayment": false,
  "taxes": {
    "retainIss": false,
    "iss": 2.0,
    "cofins": 0,
    "csll": 0,
    "inss": 0,
    "ir": 0,
    "pis": 0
  }
}
```

#### Status Possíveis da NFS-e
```
SCHEDULED              → Agendada
SYNCHRONIZED           → Enviada para a prefeitura
AUTHORIZED             → Emitida com sucesso ✅
PROCESSING_CANCELLATION → Cancelamento em processamento
CANCELED               → Cancelada
CANCELLATION_DENIED    → Cancelamento negado
ERROR                  → Erro na emissão
```

> ⚠️ **Breaking Change:** A partir de **30/06/2026** novas regras de PIS/COFINS (NT-007)
> para Regime Normal. Use `"useTaxSystemReformNT007": true` para antecipar.

#### Emissão Automática em Assinaturas
```bash
POST /v3/subscriptions/{id}/invoiceSettings
{
  "effectiveDatePeriod": "ON_PAYMENT_CONFIRMATION",
  "receivedOnly": true,
  "municipalServiceId": "203561",
  "taxes": { ... }
}
```

Opções de `effectiveDatePeriod`:
- `ON_PAYMENT_CONFIRMATION` — após pagamento confirmado
- `ON_PAYMENT_DUE_DATE` — no vencimento
- `BEFORE_PAYMENT_DUE_DATE` — X dias antes do vencimento
- `ON_NEXT_MONTH` — no mês seguinte

### 9.3 Webhooks do Asaas

Até **10 URLs** configuráveis. Header de autenticação: `asaas-access-token`.

#### Eventos Principais
```
PAYMENT_CREATED     → Cobrança criada
PAYMENT_RECEIVED    → Pagamento recebido ✅
PAYMENT_CONFIRMED   → Pagamento confirmado
PAYMENT_OVERDUE     → Cobrança vencida
PAYMENT_REFUNDED    → Estorno realizado
INVOICE_AUTHORIZED  → NFS-e emitida com sucesso ✅
INVOICE_CANCELED    → NFS-e cancelada
```

#### Payload de Exemplo
```json
{
  "id": "evt_123456789",
  "event": "PAYMENT_RECEIVED",
  "dateCreated": "2026-07-01 14:30:00",
  "payment": {
    "id": "pay_080225913252",
    "customer": "cus_000005913252",
    "value": 150.00,
    "netValue": 148.35,
    "billingType": "PIX",
    "status": "RECEIVED",
    "externalReference": "NUVEMSHOP_ORDER_12345"
  }
}
```

> ⚠️ Asaas guarda eventos por **14 dias**. Fila pausa após 15 falhas consecutivas.

---

## 10. Arquitetura da Integração Nuvemshop + Asaas

### Diagrama de Fluxo
```
CLIENTE FINAL
     │
     ▼
NUVEMSHOP (Storefront + Admin)
     │ Webhook: order/created, order/paid
     ▼
SEU BACKEND (Node.js)
     ├── Recebe webhooks Nuvemshop
     ├── Chama API Asaas
     ├── Recebe webhooks Asaas
     └── Atualiza Nuvemshop
     │
     ├──► ASAAS (Pagamentos + NFS-e)
     │
     └──► BANCO DE DADOS
          (nuvemshop_order_id ↔ asaas_payment_id)
```

### Fluxo Completo — Pedido
```
1. Cliente finaliza pedido na Nuvemshop
2. Webhook Nuvemshop → backend (order/created)
3. Backend cria/busca cliente no Asaas (POST /v3/customers)
4. Backend cria cobrança no Asaas (POST /v3/payments)
5. Link PIX/Boleto enviado para o cliente
6. Cliente paga
7. Webhook Asaas → backend (PAYMENT_RECEIVED)
8. Backend atualiza pedido Nuvemshop (PUT /orders/{id})
9. Backend agenda NFS-e no Asaas (POST /v3/invoices)
10. Webhook Asaas → backend (INVOICE_AUTHORIZED)
11. NFS-e enviada por email para o cliente
```

### Variáveis de Ambiente
```env
# Nuvemshop
NUVEMSHOP_APP_ID=seu_app_id
NUVEMSHOP_CLIENT_SECRET=seu_client_secret
NUVEMSHOP_ACCESS_TOKEN=token_da_loja
NUVEMSHOP_STORE_ID=id_da_loja

# Asaas
ASAAS_API_KEY=sua_api_key
ASAAS_ENVIRONMENT=sandbox
ASAAS_SANDBOX_URL=https://api-sandbox.asaas.com/v3
ASAAS_PRODUCTION_URL=https://api.asaas.com/v3
ASAAS_WEBHOOK_TOKEN=token_validacao_asaas

# App
PORT=3000
DATABASE_URL=sua_connection_string
```

### Modelo de Dados Sugerido (SQL)
```sql
CREATE TABLE integrations (
  id                    UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  nuvemshop_order_id    VARCHAR NOT NULL UNIQUE,
  nuvemshop_customer_id VARCHAR,
  asaas_payment_id      VARCHAR,
  asaas_customer_id     VARCHAR,
  asaas_invoice_id      VARCHAR,
  payment_status        VARCHAR DEFAULT 'pending',
  invoice_status        VARCHAR DEFAULT 'pending',
  amount                DECIMAL(10,2),
  created_at            TIMESTAMP DEFAULT NOW(),
  updated_at            TIMESTAMP DEFAULT NOW()
);

CREATE INDEX idx_nuvemshop_order ON integrations(nuvemshop_order_id);
CREATE INDEX idx_asaas_payment ON integrations(asaas_payment_id);
```

---

## 11. Homologação e Publicação de Apps

### Processo
1. Criar app no Portal de Parceiros
2. Desenvolver com NubeSDK (obrigatório desde 05/06/2026)
3. Testar em loja demo
4. Submeter pedido de homologação
5. Enviar **diagrama de sequência** + **vídeo demo**
6. Validação pela equipe Nuvemshop
7. Ajustes e revalidação
8. Publicação na App Store

### Requisitos Obrigatórios

| Requisito | Obrigatoriedade |
|-----------|-----------------|
| NubeSDK (sem DOM, sem jQuery) | ✅ Obrigatório |
| ErrorBoundary (Nexo) | ✅ Obrigatório |
| Webhooks LGPD (para apps BR) | ✅ Obrigatório |
| Diagrama de sequência | ✅ Obrigatório |
| Vídeo demo com todos os fluxos | ✅ Obrigatório |
| Nimbus design system | ✅ Obrigatório (incorporados) |
| Página de estado vazio | ✅ Obrigatório |
| Página de erro | ✅ Obrigatório |

### Apps ERP, Payments e Shipping
Processo adicional: roteiro de vídeo específico + validação com checklist detalhada.

---

## 12. Roadmap de Implementação com Claude Code

### Fase 1 — Setup e Auth
- [ ] Criar conta no Portal de Parceiros Nuvemshop
- [ ] Criar app e obter `app_id` + `client_secret`
- [ ] Criar loja demo para testes
- [ ] Criar conta Asaas (produção + sandbox)
- [ ] Obter API Key do Asaas
- [ ] Scaffold do backend (Node.js + Express ou Fastify)
- [ ] Implementar fluxo OAuth 2 da Nuvemshop
- [ ] Configurar variáveis de ambiente

### Fase 2 — Integração Core
- [ ] Criar cliente no Asaas ao criar cliente na Nuvemshop
- [ ] Criar cobrança Asaas ao confirmar pedido Nuvemshop
- [ ] Webhook Nuvemshop → processar `order/created` e `order/paid`
- [ ] Webhook Asaas → processar `PAYMENT_RECEIVED`
- [ ] Atualizar status do pedido Nuvemshop após pagamento
- [ ] Banco de dados para mapeamento de IDs

### Fase 3 — NFS-e
- [ ] Configurar informações fiscais na conta Asaas
- [ ] Listar e configurar serviço municipal
- [ ] Agendar NFS-e ao confirmar pagamento
- [ ] Webhook `INVOICE_AUTHORIZED` → enviar por email
- [ ] Tratar erros de emissão (`INVOICE_ERROR`)

### Fase 4 — Storefront (NubeSDK)
- [ ] Instalar e configurar NubeSDK
- [ ] Implementar UI slots desejados
- [ ] Eventos de carrinho e checkout
- [ ] Labels customizadas de frete
- [ ] Tracking de pedido

### Fase 5 — Admin (Nexo — se app incorporado)
- [ ] Inicializar Nexo com clientId
- [ ] Implementar `connect` + `iAmReady`
- [ ] Adicionar `ErrorBoundary` (obrigatório)
- [ ] Sincronização de rotas
- [ ] JWT para requests ao backend

### Fase 6 — Homologação
- [ ] Gerar diagrama de sequência
- [ ] Gravar vídeo demo
- [ ] Submeter para homologação
- [ ] Validar checklist de design (Nimbus)
- [ ] Publicar na App Store

---

## 13. Recursos e Links Úteis

| Recurso | URL |
|---------|-----|
| Dev Hub Nuvemshop | https://dev.nuvemshop.com.br |
| Portal de Parceiros | https://partners.nuvemshop.com.br |
| API Reference Nuvemshop | https://tiendanube.github.io/api-documentation/intro |
| NubeSDK Docs | https://dev.nuvemshop.com.br/docs/applications/nube-sdk/overview |
| Nimbus Design System | https://nimbus.tiendanube.com |
| GitHub Templates | https://github.com/TiendaNube/app-templates-nodejs-express-react |
| Asaas Dev Portal | https://docs.asaas.com |
| Asaas Sandbox | https://sandbox.asaas.com |
| Asaas Status Page | https://status.asaas.com |
| Nuvem Envio | https://www.nuvemshop.com.br/solucoes/nuvem-envio |
