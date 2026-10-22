---
name: bs-foundation
description: Use when the user asks to "start the project", "set up Supabase", "apply migrations", "configure the foundation", "fase 0", "fundação", "criar projeto", "configurar banco" or similar setup tasks. This skill bootstraps the BS Informática ERP project from zero.
---

# BS Informática — Foundation Setup Skill

## Objetivo
Configurar a base técnica completa do projeto BS Informática ERP antes de qualquer módulo funcional.

## Passos Obrigatórios

### 1. Supabase Project Setup
- Criar projeto Supabase com timezone `America/Fortaleza` e locale `pt-BR`
- Configurar variáveis de ambiente no Lovable:
  - `VITE_SUPABASE_URL`
  - `VITE_SUPABASE_ANON_KEY`

### 2. Aplicar Migration SQL
- Aplicar o arquivo `0001_foundation.sql` no **Supabase SQL Editor** do projeto de desenvolvimento
- O arquivo cria todos os tipos ENUM, tabelas, indexes, funções, triggers e políticas RLS base
- **NUNCA** aplicar direto em produção sem testar antes

### 3. Estrutura de Pastas do Projeto
Criar os três frontends dentro do mesmo repositório:
```
./          → Loja de Produtos (e-commerce público)
./admin     → Dashboard Administrativo (ERP completo)
./servicos  → Loja de Serviços (e-commerce público)
```

### 4. Design System — BS Informática
- Importar e configurar TailwindCSS + shadcn/ui
- Aplicar as cores, tipografia e estilos da identidade visual da BS Informática conforme as imagens de design anexas
- Criar tokens de design no `tailwind.config.ts`:
  - Cores primárias e secundárias da marca
  - Tipografia: fonte principal do design system
  - Bordas arredondadas, sombras e espaçamentos padrão
- Criar componentes base: `Header`, `Sidebar`, `PageLayout`, `Card`, `Badge`, `Button` seguindo a identidade visual

### 5. Layout e Navegação
- **Loja (`./`):** Header com logo BS Informática, navegação por categorias, ícone de carrinho
- **Admin (`./admin`):** Sidebar colapsável com 21 módulos, header com nome do usuário e papel
- **Serviços (`./servicos`):** Header com logo e navegação por categorias de serviço

### 6. Componentes de Formulário Base
Criar componentes reutilizáveis:
- `Input`, `Select`, `Textarea`, `Checkbox`, `DatePicker`, `FileUpload`
- `FormField` com label, erro e tooltip
- `DataTable` com paginação, ordenação e filtros
- `Modal` / `Dialog` para confirmações e formulários
- `Toast` / `Alert` para feedback ao usuário

### 7. Autenticação Admin
- Implementar login email/senha via Supabase Auth
- Proteger todas as rotas `/admin/*` com `RequireAuth` wrapper
- Após login, ler `profiles` para obter `role` e `company_id`
- Redirecionar para `/admin` após autenticação bem-sucedida

### 8. Validação RLS
- Testar com usuários de papéis diferentes: `owner`, `manager`, `technician`, `viewer`
- Confirmar que dados de outras empresas nunca aparecem
- Confirmar que anon key acessa apenas produtos/serviços ativos

## Critérios de Conclusão da Fase
- [ ] Migration aplicada sem erros em ambiente de desenvolvimento
- [ ] Login admin funcional com redirecionamento correto
- [ ] Layout responsivo renderizando nas 3 rotas base
- [ ] Design system da BS Informática aplicado e consistente
- [ ] RLS testado com múltiplos papéis
