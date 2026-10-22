# 📋 Lista de Funcionalidades — InfoCapi Magazine

---

## 🛒 Frontend (Loja Online / E-commerce)

### Catálogo de Produtos
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 1 | Listagem de produtos vindos da API (carregamento assíncrono) | [cartaoProduto.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/cartaoProduto.js), [api.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/api.js) |
| 2 | Exibição de card de produto com imagem, nome, marca, preço e botão de compra | [cartaoProduto.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/cartaoProduto.js) |
| 3 | Indicação visual de produto esgotado (opacidade + grayscale + botão "Esgotado" desabilitado) | [cartaoProduto.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/cartaoProduto.js#L25-L29) |
| 4 | Animação de hover com zoom na imagem do produto | [index.html](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/index.html#L37) |
| 5 | Filtro de produtos por categoria (Todos, Celular, Controle Remoto, SD Card, Teclado, TV, Fone de Ouvido) | [filtrosCatalogo.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/filtrosCatalogo.js) |
| 6 | Normalização de nomes de categorias (aliases: `smart-tv` → `tv`, etc.) | [utilidades.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/utilidades.js#L3-L10) |
| 7 | Formatação de preço em BRL (R$) | [utilidades.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/utilidades.js#L36-L43) |

### Carrinho de Compras
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 8 | Menu lateral deslizante do carrinho (slide-in/slide-out) | [menuCarrinho.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/menuCarrinho.js#L5-L13) |
| 9 | Adicionar produto ao carrinho | [menuCarrinho.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/menuCarrinho.js#L137-L151) |
| 10 | Incrementar quantidade de produto no carrinho | [menuCarrinho.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/menuCarrinho.js#L39-L44) |
| 11 | Decrementar quantidade (remove se chegar a 1) | [menuCarrinho.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/menuCarrinho.js#L46-L55) |
| 12 | Remover produto do carrinho | [menuCarrinho.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/menuCarrinho.js#L32-L37) |
| 13 | Cálculo e atualização automática do preço total | [menuCarrinho.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/menuCarrinho.js#L153-L165) |
| 14 | Persistência do carrinho via LocalStorage | [utilidades.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/utilidades.js#L45-L55) |
| 15 | Validação de estoque antes de adicionar (alerta se esgotado) | [menuCarrinho.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/menuCarrinho.js#L139-L142) |

### Checkout
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 16 | Formulário de dados do cliente (nome, email, telefone) | [checkout.html](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/checkout.html#L29-L63) |
| 17 | Formulário de pagamento (número do cartão, CVV, data de validade) | [checkout.html](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/checkout.html#L64-L101) |
| 18 | Formulário de endereço de entrega (CEP, endereço, número, complemento) | [checkout.html](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/checkout.html#L102-L145) |
| 19 | Resumo dos produtos com quantidades e preço total | [checkout.html](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/checkout.html#L147-L170) |
| 20 | Finalização da compra via API (POST `/api/v1/storefront/checkout/`) | [checkout.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/checkout.js#L29-L76) |
| 21 | Feedback visual durante processamento ("Processando...") | [checkout.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/checkout.js#L49-L51) |
| 22 | Tratamento de erros (estoque insuficiente HTTP 409, erros genéricos) | [checkout.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/checkout.js#L67-L75) |
| 23 | Limpeza do carrinho após compra bem-sucedida | [checkout.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/checkout.js#L64) |

### Histórico de Pedidos
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 24 | Listagem do histórico de pedidos (via LocalStorage) | [pedidos.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/pedidos.js) |
| 25 | Exibição de data/hora de cada pedido formatada em pt-BR | [pedidos.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/pedidos.js#L8-L18) |
| 26 | Detalhamento dos produtos de cada pedido com quantidades | [pedidos.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/pedidos.js#L22-L28) |

### Infraestrutura do Frontend
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 27 | Build com Vite | [vite.config.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/vite.config.js) |
| 28 | Estilização com TailwindCSS | [tailwind.config.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/tailwind.config.js) |
| 29 | Ícones via Font Awesome 6 | [index.html](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/index.html#L8-L14) |
| 30 | Comunicação com API backend via variável de ambiente `VITE_API_BASE_URL` | [api.js](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/src/api.js#L1) |

---

## ⚙️ Backend (Dashboard Administrativo / cpainel)

> **Stack**: Django + Django REST Framework + SQLite · Autenticação JWT · Docker

### Dashboard / Home
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 1 | Dashboard com métricas de produtos (custo total, valor de venda, lucro, quantidade total) | [metrics.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/app/metrics.py#L10-L22) |
| 2 | Métricas de vendas (total pedidos, produtos vendidos, valor total, lucro) | [metrics.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/app/metrics.py#L25-L50) |
| 3 | Gráfico de produtos por categoria | [metrics.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/app/metrics.py#L89-L96) |
| 4 | Gráfico de produtos por marca | [metrics.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/app/metrics.py#L99-L107) |
| 5 | Gráfico de vendas diárias (valor — últimos 7 dias) | [metrics.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/app/metrics.py#L53-L69) |
| 6 | Gráfico de vendas diárias (quantidade — últimos 7 dias) | [metrics.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/app/metrics.py#L72-L86) |
| 7 | Insights de IA (análise e sugestões via OpenAI) | [agent.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/ai/agent.py), [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/app/views.py#L15-L16) |

### Gestão de Produtos
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 8 | Listagem de produtos com paginação (10/página) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/products/views.py#L17-L58) |
| 9 | Busca/filtro por título, número de série, categoria e marca | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/products/views.py#L24-L41) |
| 10 | Ordenação por ID ou título (asc/desc) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/products/views.py#L43-L50) |
| 11 | Criação de produto com seleção encadeada (Fornecedor → Marca → Categoria) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/products/views.py#L61-L109) |
| 12 | Visualização de detalhes do produto | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/products/views.py#L112-L115) |
| 13 | Edição de produto (com seleção encadeada) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/products/views.py#L118-L178) |
| 14 | Exclusão de produto com proteção contra dependências (entradas/saídas vinculadas) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/products/views.py#L181-L208) |
| 15 | Contagem de entradas e saídas por produto na listagem | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/products/views.py#L25-L28) |

### Gestão de Categorias
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 16 | CRUD completo de categorias (Listar, Criar, Detalhar, Editar, Excluir) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/categories/views.py) |
| 17 | Contagem de marcas e produtos por categoria | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/categories/views.py#L22-L25) |
| 18 | Proteção contra exclusão com dependências (marcas/produtos vinculados) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/categories/views.py#L63-L94) |
| 19 | Busca por nome e ordenação | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/categories/views.py#L26-L38) |

### Gestão de Marcas
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 20 | CRUD completo de marcas (Listar, Criar, Detalhar, Editar, Excluir) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/brands/views.py) |
| 21 | Filtro por nome, fornecedor e categoria | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/brands/views.py#L21-L41) |
| 22 | Contagem de produtos por marca | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/brands/views.py#L22) |
| 23 | Proteção contra exclusão com produtos vinculados | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/brands/views.py#L74-L98) |
| 24 | Relacionamento obrigatório com Fornecedor e Categoria | [models.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/brands/models.py#L7-L16) |

### Gestão de Fornecedores
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 25 | CRUD completo de fornecedores (Listar, Criar, Detalhar, Editar, Excluir) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/suppliers/views.py) |
| 26 | Busca por nome e ordenação | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/suppliers/views.py#L15-L29) |

### Gestão de Clientes
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 27 | CRUD completo de clientes (Listar, Criar, Detalhar, Editar, Excluir) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/clients/views.py) |
| 28 | Busca por nome e email | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/clients/views.py#L15-L32) |
| 29 | Modelo de Endereço vinculado ao cliente (CEP, rua, número, complemento, bairro, cidade, estado) | [models.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/clients/models.py#L21-L39) |
| 30 | Rastreamento de total de pedidos e total gasto por cliente | [models.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/clients/models.py#L9-L10) |

### Gestão de Entradas (Inflows)
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 31 | CRUD completo de entradas no estoque | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/inflows/views.py) |
| 32 | Seleção encadeada (Fornecedor → Produto) na criação/edição | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/inflows/views.py#L50-L60) |
| 33 | Recálculo automático do estoque do produto ao criar/editar/excluir entradas | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/inflows/views.py#L76-L141) |
| 34 | Filtro por produto e intervalo de datas | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/inflows/views.py#L19-L40) |
| 35 | Rastreamento de data de esgotamento de estoque (stock_depletion_date) | [models.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/inflows/models.py#L14-L19) |

### Gestão de Saídas / Pedidos (Outflows)
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 36 | Listagem de saídas/pedidos com paginação | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L49-L83) |
| 37 | Criação de pedido multi-produto com carrinho em sessão | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L86-L328) |
| 38 | Seleção de cliente no pedido | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L148-L153) |
| 39 | Adicionar, editar quantidade e remover itens do carrinho (na sessão) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L156-L218) |
| 40 | Validação de estoque em tempo real ao adicionar/editar itens | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L163-L169) |
| 41 | Finalização atômica do pedido (transação DB) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L278-L324) |
| 42 | Edição de pedido existente (com carrinho em sessão e cálculo de estoque disponível) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L337-L619) |
| 43 | Cálculo de estoque efetivo para edição (pool = estoque DB + quantidade original do pedido) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L349-L408) |
| 44 | Exclusão de pedido com recálculo automático de estoque | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L622-L640) |
| 45 | Visualização de detalhes do pedido (com lista de itens e subtotais) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L331-L334) |
| 46 | Filtro de saídas por produto e intervalo de datas | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L56-L77) |

### Sistema FIFO de Estoque
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 47 | Rastreamento FIFO por fornecedor (atribuição automática de supplier nos itens) | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/outflows/views.py#L27-L46) |
| 48 | Signals para atualização automática de depletion dates | [signals.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/inflows/signals.py) |
| 49 | Fallback legado durante migração (quando supplier é NULL) | [signals.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/inflows/signals.py#L68-L80) |

### Inteligência Artificial
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 50 | Agente IA (SGEAgent) para análise de estoque e vendas via OpenAI | [agent.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/ai/agent.py) |
| 51 | Prompts especializados em gestão de estoque (reposição, relatórios, sugestões diárias) | [prompts.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/ai/prompts.py) |
| 52 | Armazenamento de resultados da IA no banco (modelo AIResult) | [agent.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/ai/agent.py#L40) |
| 53 | Exibição do resultado da IA no dashboard | [views.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/app/views.py#L15-L16) |

### Autenticação e Segurança
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 54 | Login/Logout do painel administrativo (Django Auth) | [urls.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/app/urls.py#L10-L11) |
| 55 | Autenticação JWT para APIs (Token Obtain, Refresh, Verify) | [urls.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/authentication/urls.py) |
| 56 | Controle de permissões granular por entidade (`LoginRequiredMixin` + `PermissionRequiredMixin`) | Todas as views do admin |

### APIs REST
| # | Funcionalidade | Endpoint |
|---|---|---|
| 57 | API de Produtos (CRUD) | `GET/POST /api/v1/products/`, `GET/PUT/DELETE /api/v1/products/<id>/` |
| 58 | API de Produtos por Fornecedor | `GET /api/v1/products/by-supplier/<id>/` |
| 59 | API Storefront de Produtos (pública, para o frontend da loja) | `GET /api/v1/storefront/products/?categoria=...` |
| 60 | API de Checkout da Loja (pública, multi-item, atômica) | `POST /api/v1/storefront/checkout/` |
| 61 | API de Categorias (CRUD) | `GET/POST /api/v1/categories/`, `GET/PUT/DELETE /api/v1/categories/<id>/` |
| 62 | API de Categorias por Fornecedor | `GET /api/v1/categories/by-supplier/<id>/` |
| 63 | API de Marcas (CRUD) | `GET/POST /api/v1/brands/`, `GET/PUT/DELETE /api/v1/brands/<id>/` |
| 64 | API de Marcas por Fornecedor | `GET /api/v1/brands/by-supplier/<id>/` |
| 65 | API de Marcas por Fornecedor + Categoria | `GET /api/v1/brands/by-supplier/<id>/category/<id>/` |
| 66 | API de Fornecedores (CRUD) | `GET/POST /api/v1/suppliers/`, `GET/PUT/DELETE /api/v1/suppliers/<id>/` |
| 67 | API de Clientes (CRUD) | `GET/POST /api/v1/clients/`, `GET/PUT/DELETE /api/v1/clients/<id>/` |
| 68 | API de Endereços do Cliente | `GET/POST /api/v1/clients/<id>/addresses/` |
| 69 | API de Entradas (Listar/Criar, Detalhar) | `GET/POST /api/v1/inflows/`, `GET /api/v1/inflows/<id>/` |
| 70 | API de Saídas (Listar/Criar, Detalhar) | `GET/POST /api/v1/outflows/`, `GET /api/v1/outflows/<id>/` |
| 71 | API de Autenticação JWT | `POST /api/v1/authentication/token/`, `/refresh/`, `/verify/` |

### Webhook / Notificações
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 72 | Serviço de notificação via Webhook (webhook.site) | [notify.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/services/notify.py) |

### Infraestrutura
| # | Funcionalidade | Arquivo(s) |
|---|---|---|
| 73 | Containerização com Docker + Docker Compose | [Dockerfile](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/Dockerfile), [docker-compose.yml](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/docker-compose.yml) |
| 74 | Banco de dados SQLite | [db.sqlite3](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/db.sqlite3) |
| 75 | Fixtures para dados iniciais | [fixture_sqlite.json](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/fixture_sqlite.json) |
| 76 | Cron job configurado | [cron](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/cron) |
| 77 | Django Admin integrado | [urls.py](file:///c:/Repositorios/ideias-de-apps/infocapi-magazine/cpainel/app/urls.py#L8) |

---

## 📊 Resumo Quantitativo

| Área | Quantidade |
|---|---|
| **Funcionalidades do Frontend (Loja)** | 30 |
| **Funcionalidades do Backend (Dashboard)** | 47 |
| **Total de Funcionalidades** | **77** |
| Modelos de Dados | 8 (Product, Category, Brand, Supplier, Client, Address, Inflow, Outflow + OutflowItem + AIResult) |
| Endpoints de API REST | 15+ |
