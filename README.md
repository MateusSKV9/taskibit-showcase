<h1 align="center">✅ Taskibit ✅</h1>

<p align="center">
  Plataforma Full-Stack de Alta Performance para Gerenciamento de Produtividade, Hábitos, Metas e Organização Pessoal.
</p>

<p align="center">
  <a href="https://taskibit.vercel.app/"><strong>📍 Acesse a Aplicação em Produção 📍</strong></a>
</p>

<p align="center">
  <img src="/images/1.png" alt="Taskibit Dashboard Overview" width="100%" border="1px solid black" />
</p>

---

## ℹ️ Sobre o Projeto

O **Taskibit** é um ecossistema completo de produtividade desenvolvido para centralizar o gerenciamento de tarefas, hábitos recorrentes, metas de médio/longo prazo, anotações rápidas e etiquetas em uma única interface fluida e integrada.

O projeto foi concebido sob conceitos rigorosos de **Engenharia de Software**, servindo como um ambiente avançado para consolidar padrões modernos de renderização, sincronização otimista de dados, segurança em autenticação e arquitetura modular escalável.

> 🔒 **Nota de Propriedade Intelectual:** Por motivos de direitos autorais e proteção de código contra engenharia reversa ou plágio, este repositório público funciona exclusivamente como a **documentação arquitetural oficial e portfólio técnico** do projeto. O código-fonte original está mantido de forma segura em um ambiente privado.

### 🎯 Principais Objetivos

- **Centralizar** informações essenciais de produtividade diária e semanal.
- **Facilitar o acompanhamento** do progresso real através de dashboards visuais.
- **Oferecer uma UX intuitiva** inspirada em quadros Kanban adaptáveis.
- **Aplicar as melhores práticas** do ecossistema moderno do Next.js (Server Actions, Híbrido, PPR/Cache).

---

## 🧱 Arquitetura de Software & Design Patterns

A aplicação rejeita os padrões genéricos de organização de código e adota uma estrutura totalmente **orientada a domínios de negócio (Feature-Driven Architecture)**, isolando as responsabilidades de forma estrita.

### 👥 Fluxo de Dados Unificado (Full-Stack Next.js)

Em vez de depender de uma arquitetura tradicional com APIs REST expostas, o Taskibit utiliza o poder das **Server Actions** integradas ao ecossistema do React 19 para unificar as camadas do cliente e do servidor em uma camada RPC fortemente tipada.

```text
[Camada Client Components]
       │ (Chamada Direta via RPC / React Hooks)
       ▼
[Camada Server Actions] ─── (Validação com Zod Schema)
       │
       ▼
[Prisma ORM Client] ─── (Tipagem Automática Estática)
       │
       ▼
[Supabase PostgreSQL Cloud Database]

```

### 📂 Organização Modular por Domínio (`features/`)

Cada módulo encapsula seu próprio ciclo de vida técnico (esquemas, componentes locais, lógica utilitária e sub-APIs):

```text
features/
├── auth/          # Autenticação Integrada (Supabase Auth)
├── tasks/         # Gestão de Tarefas, Subtarefas & Kanban Flow
├── habits/        # Monitoramento e Indicadores de Hábitos Recorrentes
├── goals/         # Acompanhamento de Metas de Evolução e Progresso
├── notes/         # Quadro Descentralizado de Anotações em Kanban
├── tags/          # Gerenciamento Dinâmico de Etiquetas Customizadas
└── columns/       # Estruturas Dinâmicas de Agrupamento das Colunas

```

**Estrutura interna padrão de cada funcionalidade:**

```text
feature/
├── api/          # Chamadas e mutações específicas
├── components/   # Componentes exclusivos do domínio
├── schemas/      # Validações estruturadas (Zod)
├── utils/        # Formatadores e helpers locais
└── index.ts      # Ponto de exportação pública da feature

```

## 🛠️ Engenharia de Performance e UX Aplicada

- **📱 PWA Nativo (Progressive Web App):** Implementação manual da especificação PWA sem dependências externas. Conta com suporte a `manifest.json` otimizado para instalação no Android/iOS/Desktop, suporte a ícones mascaráveis (_maskable icons_) e estratégias de Service Worker nativo para execução em modo standalone.
- **⚛️ Optimistic UI (`useOptimistic`):** Otimização radical na experiência do usuário. Ações de alternância de status, marcação de hábitos e movimentação de blocos Kanban refletem na tela instantaneamente antes mesmo da resposta do servidor ser concluída.
- **⚡ Skeleton Loading & React Suspense:** Implementação de layouts esqueleto nativos (vias `loading.tsx` e `Suspense`) espelhados com a estrutura exata de quadros, gráficos e cards. Elimina flashes de carregamento e reduz o CLS (Cumulative Layout Shift) durante o streaming de Server Components.
- **📱 Design Totalmente Responsivo & Mobile-First:** Interface adaptada para qualquer tamanho de tela, contando com padrões de navegação exclusivos para mobile (como bottom bar tátil no formato app nativo) e scroll horizontal otimizado para o Kanban em telas reduzidas.
- **🧭 Controle de Cache & Navegação Otimizada:** Uso estratégico de primitivos de controle de cache (`no-store`/`no-cache`) combinado a estratégias de invalidação reativa em tempo de execução via `revalidatePath` e sincronização via `router.refresh()`.

---

## 🧠 Recursos Avançados Utilizados

### Funcionalidades do Framework

- **App Router & Route Groups:** Organização de fluxos e escopos lógicos sem impactar as URLs da aplicação.
- **Server vs. Client Components:** Divisão precisa de carregamento, permitindo que a maior parte da interface seja renderizada no servidor (ganho em performance e SEO).
- **Loading UI & Layouts Aninhados:** Criação de skeletons nativos automáticos durante transições assíncronas do servidor.

### Abstração de Estados por Hooks

- **Nativos:** `useState`, `useEffect`, `useMemo`, `useCallback`, `useContext`.
- **Customizados (Engenharia Interna):** `useDragAndDrop`, `useOptimisticItems`, `useSortedItems`, `usePopup`, `useProgress`, `useTheme`, `useToggle`, `useClickOutside`, `useColumnScroll`, `useTagsMap`.

---

## 🚀 Tecnologias e Ecossistema

### Frontend & Estilização

- **Next.js 15/16** (App Router)
- **React 19**
- **TypeScript** (Tipagem Estática Total)
- **CSS Modules** (Escopo de Estilos Isolado)

### Backend, Infraestrutura & Banco

- **Server Actions** (Camada RPC Segura)
- **Prisma ORM** (Modelagem, Migrations e Queries Autotipadas)
- **Supabase PostgreSQL** (Banco Relacional Cloud)
- **Supabase Auth** (Sessões Seguras e Controle de Acesso)

### Bibliotecas Principais

- `React Hook Form` & `Zod` (Validações estruturadas)
- `@hello-pangea/dnd` (Manipulação fluida do Drag and Drop)
- `date-fns` (Manipulação e formatação de calendários temporais)

### PWA & Recursos Web Nativos

- **Web App Manifest API** (`manifest.json` nativo para experiência standalone)
- **Service Workers** (Gerenciamento de ciclo de vida e suporte à instalação em tela inicial)

---

## 🎓 Contexto Acadêmico & Colaboração

O **Taskibit** foi concebido e desenvolvido como projeto prático no âmbito das disciplinas de **Engenharia de Software I e II**.

Ao longo do desenvolvimento, assumi a liderança da arquitetura técnica, do design de interface (UI/UX) e de grande parte da implementação Full-Stack. O projeto também contou com a colaboração do desenvolvedor **[William Almeida](https://github.com/willalmeid)**, que contribuiu para o desenvolvimento de funcionalidades e etapas importantes da aplicação.

Essa parceria foi fundamental para transformar preceitos teóricos em uma aplicação completa, escalável e alinhada às boas práticas de Engenharia de Software.

---

## 📸 Demonstração da Interface (Visual & Fluxos)

### 📊 Dashboard Central de Métricas e Indicadores

Interface orientada a dados (Data Viz), exibindo o panorama de produtividade semanal através de gráficos lineares, barras empilhadas e medidores estatísticos em tempo real de tarefas, hábitos e metas.

<p align="center">
  <img src="/images/5.png" alt="Taskibit Dashboard Overview" width="90%" />
</p>

### 📅 Organização de Tarefas (Fluxo Kanban)

Gerenciamento de fluxos dinâmicos por dia da semana com arrasto interativo (Drag and Drop), priorização, subtarefas e rotulação flexível de tags.

<p align="center">
  <img src="/images/1.png" alt="Taskibit Kanban de Tarefas" width="90%" />
</p>

### 🔥 Monitoramento Comportamental de Hábitos

Acompanhamento visual de comportamentos que se tornam rotina. Inclui histórico de execução sequencial e cálculos de progresso reativos.

<p align="center">
  <img src="/images/2.png" alt="Taskibit Módulo de Hábitos" width="90%" />
</p>

### 📝 Notas Descentralizadas e Metas Estruturadas

Módulos independentes para registros de insights rápidos de código e acompanhamento detalhado de objetivos de médio/longo prazo com ordenação manual.

<p align="center">
  <img src="/images/4.png" alt="Taskibit Módulo de Anotações" width="48%" />
  <img src="/images/3.png" alt="Taskibit Módulo de Metas" width="48%" />
</p>

### 🏷️ Customização de Etiquetas e Perfil

Customização dinâmica de rotulagem com visualização inteligente do contraste de acessibilidade e modal de perfil.

<p align="center">
  <img src="/images/7.png" alt="Taskibit Painel de Etiquetas" width="48%" />
  <img src="/images/6.png" alt="Taskibit Modal de Perfil" width="48%" />
</p>

### 💀 Feedback Visual com Skeleton Screens

Carregamento progressivo orientado a streaming no servidor (React Suspense), mantendo a fidelidade visual da interface enquanto os dados são recuperados.

<p align="center">
  <img src="/images/skeleton-kanban.png" alt="Taskibit Skeleton Kanban" width="48%" />
  <img src="/images/skeleton-tags.png" alt="Taskibit Skeleton Hábitos" width="48%" />
</p>

### 🌙 Suporte Native Dark Mode

Interface desenvolvida sob diretrizes de UX para redução de fadiga visual em ambientes de baixa luminosidade.

<p align="center">
  <img src="/images/9.png" alt="Taskibit Dark Mode View" width="90%" />
</p>

### 📱 Experiência Mobile & Layout Fluid Responsivo

Navegação intuitiva adaptada para telas menores com barra de atalhos inferior (Bottom Navigation Bar) inspirada em aplicações nativas.

<p align="center">
  <img src="/images/mobile-view.png" alt="Taskibit Mobile View" width="40%" />
</p>

---

## 📄 Licença

Este projeto está licenciado sob a licença **MIT**.

---

<p align="center">
  Projetado e documentado com foco em engenharia de excelência por <strong>Mateus Santos</strong>.
</p>
