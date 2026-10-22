---
name: bs-storefront
description: Use when the user asks about "loja", "e-commerce", "storefront", "catálogo de produtos", "carrinho", "checkout", "loja de serviços", "agendamento de serviço", "histórico de pedidos", "frontend público", "loja pública", "./servicos", "product grid", "cart" or similar public-facing shop tasks.
---

# BS Informática — Storefront Skill (Lojas Públicas)

## Objetivo
Implementar os dois frontends públicos da BS Informática: loja de produtos (`./`) e loja de serviços (`./servicos`). Clientes não precisam de conta para navegar e comprar.

## Estrutura de Pastas
```
./              → Loja de Produtos
./servicos      → Loja de Serviços
```
Ambas compartilham o mesmo projeto Supabase.

## Identidade Visual BS Informática
- Seguir rigorosamente o design system das imagens anexas
- Header com logo da BS Informática em destaque
- Cards de produto/serviço com hover effect e animações suaves
- Cores, tipografia e espaçamentos conforme brand guidelines

---

## 1. Loja de Produtos (`./`)

### Catálogo (`/`)
**Componentes:** `Header`, `CategoryFilter`, `ProductGrid`, `ProductCard`, `CartDrawer`

**ProductCard deve exibir:**
- Imagem do produto (fallback: placeholder com ícone)
- Nome do produto
- Marca
- Preço formatado em R$ BRL
- Botão "Adicionar ao Carrinho"
- Se `quantity <= 0`: opacidade 50%, grayscale, botão "Esgotado" desabilitado

**CategoryFilter:**
- Chips/tabs: Todos, Celular, Controle Remoto, SD Card, Teclado, TV, Fone de Ouvido
- Filtro ativo com destaque visual
- Normalização: `smart-tv → tv`, `headphone → fone-de-ouvido`, etc.

**Dados:** `supabase.from('products').select('id,title,selling_price,image,quantity,category(name)').eq('is_active',true)`

### Carrinho (Drawer lateral)
**Componentes:** `CartDrawer`, `CartItem`
- Slide-in da direita com overlay
- Incrementar/decrementar/remover itens
- Total calculado automaticamente em R$
- Persistência em `localStorage` (chave: `bs_cart`)
- Validação: não adicionar se `quantity <= 0`
- Badge no header com quantidade total de itens

### Checkout (`/checkout`)
**Componentes:** `CheckoutForm`, `OrderSummary`

**Formulários (validar com React Hook Form + Zod):**
```typescript
// Dados do cliente
{ nome: string, email: string, telefone: string }
// Pagamento
{ numero_cartao: string, cvv: string, data_validade: string }
// Entrega
{ cep: string, logradouro: string, numero: string, complemento?: string }
```

**Fluxo:**
1. Validar formulários
2. POST para Edge Function `/functions/v1/storefront-checkout`
3. Mostrar "Processando..." durante requisição (desabilitar botão)
4. Sucesso: salvar em `localStorage['bs_historico']`, limpar carrinho, redirecionar para `/pedidos`
5. Erro 409 (OUT_OF_STOCK): mostrar qual produto está esgotado e quantidade disponível
6. Erro 404: mostrar produto não encontrado
7. Outros erros: mensagem genérica com botão de tentar novamente

### Histórico de Pedidos (`/pedidos`)
**Componentes:** `OrderHistory`, `OrderCard`
- Ler `localStorage['bs_historico']`
- Cada pedido: data/hora em `pt-BR`, lista de produtos, quantidades, total R$
- Design de card limpo com status visual

---

## 2. Loja de Serviços (`./servicos`)

### Catálogo de Serviços (`/servicos`)
**Componentes:** `ServiceHeader`, `ServiceFilter`, `ServiceGrid`, `ServiceCard`

**ServiceCard deve exibir:**
- Nome do serviço
- Descrição curta (truncada com "...")
- Preço em R$
- Duração estimada (ex: "2 horas", "1 dia útil")
- Botão "Contratar" ou "Agendar"

**Dados:** `supabase.from('services').select('*').eq('is_active',true)`

### Checkout de Serviços (`/servicos/checkout`)
**Componentes:** `ServiceCheckoutForm`, `ServiceSummary`

**Campos extras (além dos dados do cliente):**
- Data de agendamento (DatePicker — somente datas futuras)
- Horário (seletor de slots disponíveis)

**Ação:** POST para Edge Function `/functions/v1/storefront-checkout-services`

### Histórico de Serviços (`/servicos/pedidos`)
**Componentes:** `ServiceOrderHistory`, `ServiceOrderCard`
- Status visual do serviço agendado
- Data/hora formatada em pt-BR

---

## Regras Gerais das Lojas
- **Mobile-first:** funcionar perfeitamente em smartphones
- **Performance:** imagens com `loading="lazy"`, skeleton loading durante fetch
- **Acessibilidade:** alt text em imagens, aria-labels nos botões
- **SEO:** meta tags, títulos únicos por página
- **Sem autenticação obrigatória:** cliente compra sem criar conta
- Preços sempre formatados: `new Intl.NumberFormat('pt-BR', { style: 'currency', currency: 'BRL' }).format(valor)`
