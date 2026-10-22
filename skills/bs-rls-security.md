---
name: bs-rls-security
description: Use when the user asks about "RLS", "Row Level Security", "segurança", "permissões", "papéis", "roles", "política de acesso", "autenticação", "unauthorized", "acesso negado", "proteger rota", "middleware de auth", "RBAC", "policy" or any security/authorization task.
---

# BS Informática — RLS & Security Skill

## Objetivo
Garantir que toda implementação de segurança e controle de acesso do ERP BS Informática siga as melhores práticas de RLS no Supabase.

## Regras de Ouro — NUNCA VIOLAR

1. **Frontend nunca é autoridade** para preços, totais, estoque, status ou permissões
2. **Papel obtido do servidor:** sempre ler de `profiles.role` via query autenticada — nunca confiar em valor enviado pelo cliente
3. **`company_id` em toda query:** nunca deixar vazar dados entre empresas
4. **Operações críticas via RPC** com `SECURITY DEFINER` + `search_path = public` fixo
5. **Idempotência:** toda operação crítica (pagamento, movimentação) deve ter `idempotency_key`

## Funções Auxiliares de RLS (já criadas na migration)

```sql
-- Retorna company_id do usuário autenticado
public.current_company_id() → uuid

-- Retorna papel do usuário autenticado
public.current_app_role() → app_role
```

## Papéis e Permissões por Módulo

| Módulo | viewer | attendant | technician | stock_manager | cashier | manager | owner |
|---|---|---|---|---|---|---|---|
| Dashboard (leitura) | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Clientes (CRUD) | 🔍 | ✅ | 🔍 | 🔍 | 🔍 | ✅ | ✅ |
| Abertura de OS | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ✅ |
| Diagnóstico | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ |
| Orçamento | ❌ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ |
| Aprovação de Desconto | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |
| Estoque (ver) | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Estoque (ajustar) | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ |
| Compras | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ |
| Vendas | ❌ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ |
| Pagamentos | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ |
| Caixa | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ |
| Entrega c/ saldo | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |
| Reabrir OS | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |
| Usuários/Permissões | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |
| Configurações | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |

✅ = acesso total | 🔍 = somente leitura | ❌ = sem acesso

## Implementação no Frontend (React)

### Hook de Permissões
```typescript
// Criar hook usePermissions()
const { role, companyId, can } = usePermissions()

// Uso nos componentes
if (!can('manage_inventory')) return <AccessDenied />
```

### Proteger Rotas
```typescript
// Wrapper de rota protegida
<RequireAuth role={['manager', 'owner']}>
  <UsersPage />
</RequireAuth>
```

### Ocultar Elementos por Papel
```typescript
// Botão visível somente para papéis autorizados
{can('approve_discount') && <Button>Aprovar Desconto</Button>}
```

## Políticas RLS por Tabela

### Tabelas Públicas (anon key)
```sql
-- products, services: leitura pública de itens ativos
SELECT: is_active = true (anon e authenticated)
INSERT/UPDATE/DELETE: somente admin (role IN ('owner','manager'))
```

### Tabelas de Empresa (authenticated)
```sql
-- customers, service_orders, etc.
SELECT: company_id = current_company_id()
INSERT: company_id = current_company_id() AND current_app_role() != 'viewer'
UPDATE/DELETE: depende do papel (ver tabela acima)
```

### Tabelas Críticas (via RPC apenas)
```sql
-- inventory_movements, payments: somente via SECURITY DEFINER functions
-- Nunca permitir INSERT/UPDATE/DELETE direto do cliente
```

## Checklist de Segurança (aplicar em toda feature)
- [ ] Rotas protegidas com `RequireAuth`
- [ ] Elementos UI ocultos/desabilitados para papéis sem acesso
- [ ] Queries Supabase sem `company_id` hardcoded — sempre via `current_company_id()`
- [ ] Operações críticas via RPC (não INSERT/UPDATE direto)
- [ ] `idempotency_key` em pagamentos e movimentações
- [ ] Auditoria registrada para ações sensíveis
- [ ] Arquivos privados acessados via URL temporária (não URL pública permanente)
- [ ] Senhas de dispositivos nunca armazenadas em texto claro

## Auditoria Automática
Para ações que exigem auditoria, chamar RPC que registra em `audit_logs`:
```typescript
await supabase.rpc('audit_action', {
  p_action: 'deliver_with_pending_debt',
  p_entity_type: 'service_orders',
  p_entity_id: serviceOrderId,
  p_before_data: { payment_status: 'pending' },
  p_after_data: { delivery_status: 'delivered', justification: texto }
})
```
