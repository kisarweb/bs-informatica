---
name: bs-inventory
description: Use when the user asks about "inventory", "estoque", "produto", "peças", "SKU", "movimentação", "entrada de estoque", "saída de estoque", "reserva", "saldo", "custo médio", "compra", "fornecedor", "purchase order", "recebimento de mercadoria", "ajuste de estoque" or similar stock management tasks.
---

# BS Informática — Inventory & Stock Management Skill

## Objetivo
Implementar o gerenciamento completo de produtos, estoque, fornecedores e compras do ERP BS Informática.

## Regras de Negócio Críticas — NUNCA VIOLAR

1. **Estoque nunca negativo** por padrão (bloquear a nível de banco)
2. **Reserva ≠ Consumo:** `reserved` não altera `on_hand`; apenas o consumo efetivo altera
3. **Saldo disponível:** `available = quantity_on_hand - quantity_reserved`
4. **Toda operação de saldo + movimento na MESMA transação PostgreSQL**
5. **Movimentações são imutáveis:** nunca editar/excluir — corrigir com movimento compensatório
6. **Idempotência:** usar `idempotency_key` em toda movimentação
7. **Ajustes exigem motivo e papel autorizado** (`stock_manager` ou superior)

## Tipos de Movimentação
```
purchase           → entrada de compra
service_consumption → consumo em OS (diminui on_hand, libera reserved)
sale               → venda de balcão
customer_return    → devolução de cliente
supplier_return    → devolução a fornecedor
adjustment_in      → ajuste positivo (requer motivo)
adjustment_out     → ajuste negativo (requer motivo)
transfer_in        → transferência entre locais (entrada)
transfer_out       → transferência entre locais (saída)
loss               → perda/avaria (requer motivo)
reservation        → reservar para OS/venda (não altera on_hand)
reservation_release → liberar reserva (não altera on_hand)
```

## Telas a Implementar

### 1. Produtos (`/admin/products`)
- DataTable com: SKU, nome, categoria, tipo, saldo disponível, custo médio, preço de venda, status
- Busca por SKU, código de barras, nome
- Filtros: categoria, tipo de produto, compatibilidade com equipamento, status (ativo/inativo)
- Formulário de criação/edição:
  - SKU (único por empresa, padrão `^[A-Za-z0-9._/-]+$`)
  - Nome, descrição, categoria, tipo (`part`/`consumable`/`resale`/`tool`)
  - Unidade de medida (`unit`/`meter`/`gram`/`milliliter`/`liter`/`pack`)
  - Categorias de equipamento compatíveis (multi-select)
  - Marca, número de peça do fabricante
  - Custo (centavos) e preço de venda (centavos)
  - Estoque mínimo e máximo
  - Flags: rastrear série, rastrear lote, rastrear validade
  - Upload de até 5 imagens (Supabase Storage → `product-images`)

### 2. Saldo de Estoque por Local (`/admin/products/:id/stock`)
- Tabela: local de estoque, `on_hand`, `reserved`, `available`, custo médio
- Botões: Ajuste, Transferência, Ver Histórico de Movimentações

### 3. Movimentações (`/admin/inventory`)
- Histórico completo append-only com filtros
- Colunas: data, tipo, produto, local, quantidade, custo unit., origem, usuário
- **Nunca exibir botão Editar ou Excluir** em movimentações

### 4. Locais de Estoque (`/admin/inventory/locations`)
- CRUD de locais (ex: Prateleira A, Estoque Fundo, Bancada Técnica)
- Único por empresa (constraint `UNIQUE(company_id, name)`)

### 5. Fornecedores (`/admin/suppliers`)
- CRUD completo: nome, CNPJ, contato, email, telefone, endereço, condições de pagamento, notas
- Proteção contra exclusão se tiver compras vinculadas

### 6. Pedidos de Compra (`/admin/purchases`)
- Status: `draft → sent → partially_received → received → cancelled`
- Itens: produto, quantidade pedida, quantidade recebida, custo unitário
- Recebimento: parcial ou total
  - Ao receber: INSERT em `inventory_movements` com tipo `purchase`
  - Atualiza `quantity_received` nos itens
  - Se `quantity_received == quantity_ordered`: marca item como completo
  - Se todos os itens completos: status `received`

### 7. Alertas de Estoque Mínimo
- Dashboard card: "X itens abaixo do mínimo"
- Lista filtrada de produtos com `available < minimum_stock`
- Opção de gerar pedido de compra automático

## Componentes React Necessários
- `ProductForm` — formulário de produto com upload de imagens
- `StockBalanceTable` — saldo por local
- `MovementHistory` — histórico de movimentações (somente leitura)
- `AdjustmentDialog` — dialog de ajuste com motivo obrigatório
- `TransferDialog` — transferência entre locais
- `PurchaseOrderForm` — pedido de compra com itens
- `ReceivingForm` — formulário de recebimento parcial/total
- `StockAlertBadge` — badge de alerta de estoque mínimo

## Validações de Schema
Usar `product.schema.json` e `inventory-movement.schema.json` para validar formulários antes de enviar ao Supabase.

## Segurança
- Somente `stock_manager`, `manager` e `owner` podem criar ajustes
- `technician` pode apenas visualizar saldo e fazer reservas via OS
- Toda movimentação registra `performed_by` (UUID do usuário autenticado)
