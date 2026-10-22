---
name: bs-financial
description: Use when the user asks about "financial", "financeiro", "pagamento", "caixa", "contas a pagar", "contas a receber", "venda", "recebimento", "estorno", "parcelas", "PIX", "cartão", "boleto", "fechamento de caixa", "fluxo de caixa", "conciliação" or similar financial tasks.
---

# BS Informática — Financial Management Skill

## Objetivo
Implementar o módulo financeiro completo: vendas, pagamentos, caixa, contas a pagar/receber e relatórios financeiros.

## Arquitetura Financeira — 3 Entidades Distintas

```
Venda (Sale)  →  Conta Financeira (FinancialTransaction)  →  Pagamento(s) (Payment)
```

**REGRAS CRÍTICAS:**
1. Venda, conta financeira e pagamento são **entidades independentes**
2. Pagamentos parciais e múltiplos meios de pagamento são **sempre permitidos**
3. Somente pagamento com `status = confirmed` afeta totais recebidos/pagos
4. Estorno é uma **operação rastreável** — nunca deletar pagamento
5. **Não marcar conta como quitada** antes de validar `SUM(payments.amount_cents WHERE status='confirmed') >= amount_cents`
6. **Não duplicar** ao converter venda/OS em cobrança (checar se já existe antes de criar)
7. Todos os valores em **BIGINT centavos** — nunca ponto flutuante

## Meios de Pagamento
`cash` · `pix` · `debit_card` · `credit_card` · `bank_transfer` · `boleto` · `store_credit` · `other`

## Telas a Implementar

### 1. Vendas (`/admin/sales`)
- Criação: selecionar cliente (opcional), vincular OS (opcional)
- Itens: produto ou serviço, quantidade, preço, desconto por item
- Subtotal, desconto global, encargos, total
- Status: `draft → confirmed → partially_refunded → refunded → cancelled`
- Ao confirmar: gerar `financial_transaction` do tipo `receivable`

### 2. Caixa (`/admin/cash-register`)
- **Abertura:** saldo inicial em centavos, registrar `opened_by` + `opened_at`
- **Somente uma sessão aberta por empresa** (constraint único no banco)
- **Fechamento:** saldo contado, calcular diferença (`counted - expected`)
- Histórico de sessões anteriores (somente leitura)
- Resumo da sessão: entradas, saídas, saldo esperado

### 3. Contas a Receber/Pagar (`/admin/financial`)
- Tabs: A Receber · A Pagar · Vencidas · Pagas
- Filtros: vencimento, categoria, origem (venda/OS/compra/despesa/manual), cliente/fornecedor
- Card de resumo: total a receber, total a pagar, vencidas hoje, vencidas no período
- Criação manual de conta (despesas fixas, receitas avulsas)

### 4. Pagamentos (`/admin/payments`)
- Registro de pagamento vinculado a: `financial_transaction_id` e/ou `sale_id` e/ou `service_order_id`
- Campos: `amount_cents` (int), `method`, `direction` (incoming/outgoing), `idempotency_key` (UUID)
- Parcelas: `installment_number` / `installment_count`
- Referência externa e gateway (opcional)
- **Dialog de confirmação** antes de marcar como `confirmed`
- **Estorno:** criar novo Payment com `direction` oposto + motivo + referência ao original

### 5. Recebimento Vinculado à OS
- Ao acessar aba "Pagamentos" de uma OS, listar pagamentos vinculados
- Botão "Registrar Pagamento" → abre `PaymentDialog`
- Mostrar: total da OS, total pago confirmado, saldo restante
- Bloquear entrega se saldo > 0 (exceto para `owner`/`manager` com justificativa)

### 6. Relatórios Financeiros (`/admin/reports/financial`)
- Distinguir claramente:
  - **Vendas** (valor faturado, competência)
  - **Recebimentos** (caixa entrada confirmada)
  - **Despesas** (caixa saída confirmada)
  - **Saldo a receber** (pendente)
  - **Margem e lucro estimado**
- Filtros: período, categoria, técnico, forma de pagamento
- Exportação autorizada (papel `manager` ou superior)

## Componentes React Necessários
- `SaleForm` — criação de venda com itens
- `PaymentDialog` — modal de registro de pagamento com idempotência
- `CashRegisterWidget` — abertura/fechamento de caixa
- `FinancialSummaryCards` — cards de resumo financeiro
- `TransactionTable` — tabela de contas a pagar/receber
- `PaymentStatusBadge` — badge de status de pagamento
- `RevenueVsExpenseChart` — gráfico receita × despesa

## Validações
- Usar `payment.schema.json` para validar antes de enviar
- `idempotency_key` deve ser gerado no frontend (UUID v4) e enviado com cada pagamento
- Nunca enviar `status=confirmed` ou `paid_at` do frontend — o backend confirma

## Segurança
- `cashier`, `manager`, `owner` podem registrar pagamentos
- `owner` e `manager` podem fazer estornos
- Somente `owner` pode perdoar saldo e entregar com pendência
- RPC Supabase para confirmação de pagamento com verificação de papel
