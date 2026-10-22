---
name: bs-design-system
description: Use when the user asks to "apply design system", "identidade visual", "design da BS Informática", "seguir o design", "corrigir visual", "melhorar interface", "redesign", "style guide", "cores", "tipografia", "componentes visuais", "layout", "tema" or any visual/styling task.
---

# BS Informática — Design System Skill

## Objetivo
Garantir que toda a interface do sistema BS Informática siga consistentemente a identidade visual da empresa. Esta skill deve ser invocada sempre que houver dúvida sobre estilos, criação de novos componentes ou ajustes visuais.

## Regra Fundamental
> **As imagens de design anexas ao projeto são a fonte de verdade visual.** Se este documento conflitar com as imagens, as imagens prevalecem.

## Stack Visual
- **TailwindCSS** + **shadcn/ui** como base
- **lucide-react** para ícones (somente desta biblioteca)
- **React Router v6** para navegação

## Princípios de Design

### 1. Consistência
- Usar SEMPRE os componentes shadcn/ui como base (Button, Input, Card, Dialog, etc.)
- Nunca criar estilos inline ad-hoc — usar classes Tailwind definidas no tema
- Componentes novos devem herdar do tema configurado

### 2. Identidade BS Informática
- Aplicar cores da marca (primária, secundária, accent) conforme imagens anexas
- Logo da BS Informática: presente em todos os headers
- Não usar cores padrão do shadcn sem customizar para o tema da empresa

### 3. Responsividade Obrigatória
```
mobile: 320px-767px  → foco principal
tablet: 768px-1023px → layout adaptado
desktop: 1024px+     → layout completo
```
- Mobile-first: sempre começar pelo mobile e usar `md:` e `lg:` para expandir
- Sidebar do admin: colapsável no mobile (drawer), fixa no desktop

### 4. Tipografia
- Fonte: conforme design system das imagens anexas
- Hierarquia: H1 (página), H2 (seção), H3 (subseção), body, caption
- **Nunca misturar tamanhos de fonte aleatoriamente**

### 5. Espaçamento
- Grid de 4px: usar múltiplos de 4 (`p-4`, `gap-6`, `mb-8`, etc.)
- Padding de cards: `p-4` (mobile) / `p-6` (desktop)
- Gaps em grids: `gap-4` (mobile) / `gap-6` (desktop)

### 6. Estados Visuais
Todo elemento interativo deve ter:
- **default:** aparência normal
- **hover:** highlight sutil (não agressivo)
- **active/pressed:** feedback de clique
- **disabled:** opacidade 50%, cursor not-allowed
- **loading:** skeleton ou spinner
- **error:** borda vermelha + mensagem de erro abaixo

## Componentes de Status — Paleta de Cores

### Status de OS (usar `Badge` do shadcn customizado)
| Status | Cor sugerida |
|---|---|
| `received` | Azul claro |
| `diagnosing` | Roxo |
| `awaiting_customer_approval` | Laranja |
| `approved` | Verde claro |
| `in_repair` | Azul |
| `ready_for_delivery` | Verde escuro |
| `delivered` | Cinza (concluído) |
| `cancelled` | Vermelho |
| `unrepairable` | Vermelho escuro |

### Status de Pagamento
| Status | Cor |
|---|---|
| Pago | Verde |
| Parcial | Amarelo |
| Pendente | Laranja |
| Vencido | Vermelho |
| Cancelado | Cinza |

### Prioridade de OS
| Prioridade | Cor |
|---|---|
| `low` | Cinza |
| `normal` | Azul |
| `high` | Laranja |
| `urgent` | Vermelho |

## Layout do Dashboard Admin

### Sidebar
```
[Logo BS Informática]
────────────────────
📊 Dashboard
👥 Clientes
🔧 Equipamentos
📅 Agenda
📋 Ordens de Serviço
🔍 Diagnósticos
💰 Orçamentos
⚙️ Fila de Trabalho
📦 Produtos e Estoque
🏭 Fornecedores e Compras
🛠️ Catálogo de Serviços
🛒 Vendas
💳 Caixa
📑 Financeiro
💸 Pagamentos
🚚 Entregas
🛡️ Garantias
📈 Relatórios
👤 Usuários
⚙️ Configurações
🔍 Auditoria
────────────────────
[Avatar] [Nome] [Papel]
```

### Cards de Dashboard
- Ícone grande + valor numérico + label + tendência (↑↓)
- Click abre lista filtrada
- Cores de destaque por tipo (operacional: azul, financeiro: verde, alerta: vermelho)

## Animações e Transições
- Modais: fade + scale (150ms)
- Drawers: slide (200ms)
- Loading states: pulse skeleton
- Hover em cards: `transition-shadow duration-200 hover:shadow-md`
- Hover em botões: `transition-colors duration-150`

## Acessibilidade Mínima
- Todos os botões com `aria-label` descritivo
- Imagens com `alt` text
- Inputs com `id` + `htmlFor` nos labels
- Navegação por teclado funcional em modais e dropdowns
- Contraste mínimo WCAG AA

## Checklist Visual (aplicar em toda nova tela)
- [ ] Logo BS Informática presente no header
- [ ] Cores do design system aplicadas (não padrão shadcn)
- [ ] Mobile-first e responsivo
- [ ] Estados: loading, empty, error implementados
- [ ] Badges de status com cores corretas
- [ ] Tipografia hierárquica consistente
- [ ] Ícones somente de lucide-react
- [ ] Transições suaves nos elementos interativos
