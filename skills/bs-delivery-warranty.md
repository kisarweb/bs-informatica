---
name: bs-delivery-warranty
description: Use when the user asks about "delivery", "entrega", "retirada", "comprovante de entrega", "garantia", "retorno de garantia", "warranty", "devolução", "cliente foi buscar", "saiu para entrega", "fila de entrega" or similar delivery and warranty tasks.
---

# BS Informática — Delivery & Warranty Skill

## Objetivo
Implementar o módulo de entregas/retiradas e garantias do ERP BS Informática.

## Regras Críticas de Entrega

1. **Uma entrega ativa por OS** — constraint único no banco: `UNIQUE(service_order_id) WHERE status NOT IN ('delivered','cancelled','returned')`
2. **`delivered` exige:** `delivered_to` (nome de quem retirou) + comprovante (foto/assinatura)
3. **Entrega com saldo financeiro pendente:** bloqueada por padrão; exceção requer papel `owner`/`manager` + justificativa auditada
4. OS deve estar em `ready_for_delivery` para criar entrega
5. Ao marcar como `delivered`: atualizar OS para status `delivered`

## Status de Entrega (em ordem)
```
awaiting_repair → in_progress → awaiting_payment → awaiting_pickup 
→ scheduled_for_delivery → out_for_delivery → delivered
```
Alternativos: `returned`, `cancelled`

## Métodos de Entrega
- `store_pickup` — Retirada na loja
- `local_delivery` — Entrega local (motoboy/veículo próprio)
- `courier` — Transportadora

## Telas a Implementar

### 1. Fila de Entrega (`/admin/deliveries`)
**Layout:** Kanban por status ou lista filtrada

**Filtros rápidos (tabs):**
- Aguardando Pagamento
- Aguardando Retirada
- Entrega Agendada
- Saiu para Entrega
- Entregue (histórico)

**Card de cada entrega:**
- Número OS
- Nome do cliente + WhatsApp (link direto para abrir conversa)
- Equipamento
- Método de entrega
- Status de pagamento (pago / pendente R$ X,XX)
- Prazo/horário agendado
- Botão de ação principal (contextual por status)

### 2. Tela de Detalhe/Confirmação de Entrega
**Confirmar Retirada na Loja:**
- Campo: nome completo de quem retirou (obrigatório)
- Campo: documento de identificação (opcional)
- Upload de foto/assinatura como comprovante (Supabase Storage)
- Botão "Confirmar Entrega" → alerta se houver saldo pendente

**Confirmar Entrega Domiciliar:**
- Campos: endereço entregue, nome do destinatário
- Upload de foto do comprovante
- Custo de entrega em centavos

**Bloquear entrega com saldo pendente:**
```
if (payment_status_snapshot !== 'paid') {
  if (!hasPermission('deliver_with_debt')) {
    mostrar alerta e bloquear botão
  } else {
    exigir justificativa textual antes de confirmar
    registrar em audit_logs
  }
}
```

### 3. Agendamento de Entrega
- DateTimePicker para `scheduled_at`
- Confirmar com cliente via WhatsApp (link pré-formatado)
- Status muda para `scheduled_for_delivery`

---

## Módulo de Garantias (`/admin/warranties`)

### Regras
- Garantia vinculada: OS original + cliente + equipamento
- Tipos: `service` (garantia de mão de obra) e `part` (garantia de peça)
- Status: `active → expired → void → claimed`
- Retorno em garantia: cria **nova OS** vinculada à garantia original (campo `related_return_order_id`)
- Não cobrar pela OS de retorno em garantia (marcar como garantia)

### Telas

**Lista de Garantias (`/admin/warranties`):**
- DataTable: número OS origem, cliente, equipamento, tipo, início, vencimento, status
- Filtros: status (ativa/vencida/acionada), tipo, período de vencimento
- Alerta visual para garantias próximas do vencimento (< 7 dias)

**Detalhe da Garantia:**
- Informações da garantia
- Termos e condições
- Histórico de acionamentos
- Botão "Abrir OS de Retorno" → cria nova OS pré-preenchida

**Criação de Garantia (automático ao entregar OS):**
- Popup/modal após confirmar entrega perguntando se deseja emitir garantia
- Campos: tipo, descrição, data fim, termos
- Preencher automaticamente: `start_date = today`, `service_order_id`, `customer_id`, `equipment_id`

## Componentes React Necessários
- `DeliveryQueue` — lista/kanban de entregas
- `DeliveryConfirmDialog` — modal de confirmação de entrega com comprovante
- `DebtWarningAlert` — alerta de saldo pendente
- `WarrantyList` — tabela de garantias
- `WarrantyCard` — card com status e prazo
- `WarrantyExpiredBadge` — badge para garantias vencendo
- `ReturnOrderDialog` — modal de abertura de OS de retorno

## Segurança
- `attendant`, `manager`, `owner` podem confirmar entregas
- Apenas `manager` e `owner` podem entregar com saldo pendente
- Upload de comprovante: bucket `attachments` (privado) — gerar URL temporária para exibição
