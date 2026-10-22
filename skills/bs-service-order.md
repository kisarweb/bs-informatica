---
name: bs-service-order
description: Use when the user asks to "create service order", "OS", "ordem de serviço", "abrir OS", "receber equipamento", "abertura de ordem", "fluxo de OS", "timeline de status", "diagnóstico", "orçamento", "aprovação do cliente", "fila técnica", "work queue" or similar service order workflow tasks.
---

# BS Informática — Service Order (OS) Skill

## Objetivo
Implementar o fluxo completo de Ordem de Serviço da BS Informática, desde o recebimento do equipamento até a entrega ao cliente.

## Regras de Negócio Críticas

### Estados da OS (seguir esta ordem obrigatoriamente)
```
scheduled → received → triage → awaiting_diagnosis → diagnosing →
awaiting_estimate → awaiting_customer_approval → approved →
awaiting_parts → in_repair → testing → quality_control →
ready_for_delivery → delivered
```
Estados alternativos: `cancelled`, `unrepairable`, `abandoned`

### Regras de Transição
1. **TODA** mudança de estado gera linha em `service_order_status_history` (append-only — nunca editar)
2. Não permitir pular etapas sem permissão especial e `reason` registrado
3. Reparos com orçamento exigem `approved` antes de avançar para `in_repair`
4. `delivered` só pode ser aplicado após registrar `delivered_to` e comprovante
5. Entrega com saldo financeiro pendente: bloquear por padrão (exceção requer papel `owner`/`manager` + justificativa auditada)

## Telas a Implementar

### 1. Abertura de OS (`/admin/service-orders/new`)
- Buscar ou criar cliente (busca por nome/telefone/CPF/email)
- Selecionar ou cadastrar equipamento vinculado ao cliente
- Campos obrigatórios: `reported_problem` (mín. 5 chars), `equipment_id`, `customer_id`
- Campos opcionais: `priority` (low/normal/high/urgent), `promised_at`, `accessories_received[]`, `initial_condition`, `customer_notes`, `assigned_technician_id`
- Gerar número único por empresa (prefixo configurável + sequencial)
- Exibir comprovante imprimível com QR Code após criação

### 2. Lista de OS (`/admin/service-orders`)
- DataTable com: número OS, cliente, equipamento, status (badge colorido), prioridade, prazo, técnico
- Filtros: status, prioridade, técnico, período, cliente
- Ordenação: prazo, prioridade, data de abertura
- Cards de resumo: abertas, atrasadas, aguardando aprovação, prontas para entrega

### 3. Detalhe da OS (`/admin/service-orders/:id`)
**Componentes da página:**
- `OSHeader`: número, cliente, equipamento, status atual, prioridade, técnico, prazo
- `OSTimeline`: histórico visual de status com timestamps e responsável
- `OSDiagnosticTab`: formulário e listagem de diagnósticos
- `OSEstimateTab`: orçamentos versionados com aprovações
- `OSPartsTab`: peças consumidas e reservadas
- `OSPaymentTab`: pagamentos vinculados
- `OSDeliveryTab`: informações de entrega
- `OSWarrantyTab`: garantias emitidas
- `OSAttachmentsTab`: fotos e documentos
- `OSAuditTab`: histórico completo de alterações

### 4. Diagnóstico
- Campos: `symptoms`, `tests_performed[]`, `identified_faults[]`, `probable_cause`, `recommended_actions[]`, `parts_required[]`, `measurements[]`
- Upload de fotos (Supabase Storage → bucket `attachments`)
- Status: `draft` → `completed` / `inconclusive`
- Vinculado ao técnico autenticado

### 5. Orçamento Versionado
- Criar nova versão ao editar escopo/preço após aprovação
- Itens: tipo (`labor`/`part`/`consumable`/`other`), descrição, qtd, preço unit., desconto
- Totais calculados pelo **backend** via RPC — nunca pelo frontend
- Status: `draft → sent → approved | rejected | expired | superseded`
- Aprovação: registrar método, data, evidência, nome do aprovador
- **NUNCA** inferir aprovação por visualização

### 6. Fila de Trabalho (`/admin/work-queue`)
- Visualizações: Kanban por status ou Lista por prioridade/prazo
- Filtros: técnico, status, prioridade, prazo prometido
- Indicador de tempo parado (colorido: verde/amarelo/vermelho)
- Drag-and-drop de prioridade (registra alteração no histórico)

## Componentes React Necessários
- `ServiceOrderForm` — formulário de abertura
- `StatusBadge` — badge colorido por status
- `PriorityBadge` — badge de prioridade
- `OSTimeline` — timeline de transições
- `DiagnosticForm` — formulário de diagnóstico
- `EstimateBuilder` — construtor de orçamento
- `ApprovalDialog` — modal de aprovação/recusa
- `WorkQueue` — fila técnica (Kanban/Lista)

## Segurança
- Frontend nunca é autoridade para status, preços ou permissões
- Transições de status via RPC Supabase com validação de papel
- Validar que `equipment_id` pertence ao `customer_id` da OS
- Registrar `changed_by` em todo `service_order_status_history`
