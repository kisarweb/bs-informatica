---
name: bs-homepage
description: Use when the user asks about "home", "homepage", "página inicial", "apresentação", "index", "landing page", "hero carrossel", "antes e depois", "b2b parceiros", "modal de contato", "como chegar", "faq", "footer", "rodapé institucional", "slides de equipamentos" or similar institutional landing page tasks.
---

# BS Informática — Homepage Skill (Página Inicial de Apresentação)

## Objetivo
Implementar a **Home Page Institucional** da BS Informática (rota `./` ou `/`). Esta página é uma vitrine de autoridade técnica, zelo e credibilidade. **Não exibe diretamente o catálogo de produtos**, funcionando como porta de entrada e direcionando o visitante para as páginas dedicadas de **Produtos** (`/produtos`), **Serviços** (`/servicos`) e canais de contato.

---

## 1. Estrutura de Seções da Home

```
[ Header / Navbar Superior ]
  ├── Logo BS Informática
  ├── Link "Produtos" (navega para /produtos em nova página)
  ├── Link "Serviços" (navega para /servicos em nova página)
  ├── Link Âncora "Como Chegar" (scroll suave para #como-chegar)
  └── Botão CTA / WhatsApp Rápido

[ Seção 1: Hero Carousel de Equipamentos ]
  ├── Slides com fotos de equipamentos de alta complexidade
  ├── Transição automática temporizada (tempo longo, ex: 6 a 8s)
  ├── Controles manuais (setas esquerda/direita + indicadores/bullets)
  ├── Copywriting de alto impacto: dificuldade técnica, cuidado e garantia
  └── CTAs de direcionamento

[ Seção 2: Antes e Depois — Desmontagem e Restauração ]
  ├── Galeria ou slider comparativo (Equipamento Desmontado vs. Restaurado)
  ├── Copy enfatizando método laboratorial, química de limpeza, solda de precisão
  └── Botão "Baixar Apresentação e Tabela de Serviços em PDF" (download de arquivo anexo)

[ Seção 3: Parcerias Corporativas B2B ]
  ├── Copy voltado a lojistas, assistências parceiras, revendas de bikes elétricas e integradores
  ├── Proposta de valor: laboratório terceirizado, SLA ágil, garantia e laudo técnico
  └── Botão centralizado que abre MODAL FLUTUANTE de Contato B2B

[ Seção 4: Como Chegar e Atendimento Presencial ]
  ├── Imagem em destaque: `img-como-chegar.jpg` (fachada / mapa / localização)
  ├── Endereço completo, telefone fixo, celular e horário de funcionamento
  ├── Ícones com links externos (target="_blank"): Instagram, Facebook, WhatsApp direto
  └── Botão de contato local / identificador `id="como-chegar"`

[ Seção 5: FAQ — Perguntas e Respostas Frequentes ]
  ├── Acordeão interativo (shadcn/ui Accordion)
  └── Respostas sobre diagnósticos, prazos, formas de pagamento e garantias

[ Seção 6: Rodapé Institucional (Footer) ]
  ├── Links rápidos (Home, Produtos, Serviços, Como Chegar, FAQ, Admin)
  ├── Informações institucionais e canais oficiais
  └── Copyright: "2026 desenvolvido por infocapibaribe.com"
```

---

## 2. Componentes Recomendados

```
src/
├── pages/
│   └── HomePage.tsx                       # Página principal integrada
├── components/home/
│   ├── HomeNavbar.tsx                     # Header fixo com links e âncoras
│   ├── HeroCarousel.tsx                   # Carrossel com autoplay + manual
│   ├── BeforeAfterSection.tsx             # Desmontagem, restauração e botão download PDF
│   ├── B2BPartnerSection.tsx              # Seção corporativa + trigger do modal
│   ├── B2BContactModal.tsx                # Modal flutuante de formulário B2B
│   ├── LocationContactSection.tsx         # img-como-chegar.jpg + dados + redes (target="_blank")
│   ├── FaqSection.tsx                     # Accordion de perguntas frequentes
│   └── HomeFooter.tsx                     # Rodapé com links e copyright 2026
```

---

## 3. Diretrizes de Copywriting e Tom de Voz

1. **Dificuldade Técnica Real:** Demonstrar autoridade técnica sem ser pedante. Falar sobre microeletrônica, reconstrução de trilhas, osciloscópio, estações de retrabalho BGA, baterias e controladores de bikes elétricas, inversores de alta potência.
2. **Cuidado e Respeito ao Patrimônio:** Transmitir segurança ao cliente. Equipamentos caros exigem protocolo antiestático (ESD), ferramentas adequadas e proteção integral.
3. **Garantia Incondicional de Serviço:** Deixar explícito que os consertos acompanham garantia formal, laudo de entrega e rastreabilidade total por Ordem de Serviço.
4. **Tom de Voz:** Seguro, técnico, transparente e acolhedor. Seguir os arquivos anexos `tom-de-voz.md` e `sobre-a-empresa.md`.

---

## 4. Regras de Interação Críticas

- **Produtos e Serviços:** Os links do menu para "Produtos" e "Serviços" devem direcionar para **páginas inteiras separadas** (`/produtos` e `/servicos`), **nunca modais**.
- **Formulário B2B:** O botão da seção de empresas parceiras **DEVE abrir uma página flutuante (modal dialog)** sobre a própria Home, sem recarregar a tela.
- **Redes Sociais:** Instagram, Facebook e WhatsApp devem ter obrigatoriamente `target="_blank"` e `rel="noopener noreferrer"`. O link do WhatsApp deve acionar a API oficial (`https://wa.me/55...`) abrindo uma nova conversa direta com a BS Informática.
- **Download do PDF:** O botão na seção "Antes e Depois" deve acionar o download do arquivo PDF entregue anexo ao projeto Lovable.
- **Copyright Obrigatório:** Rodapé com `Copyright © 2026 desenvolvido por infocapibaribe.com`.
