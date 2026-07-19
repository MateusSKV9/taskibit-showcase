<h1 align="center">✅ Taskibit ✅</h1>

<p align="center">
  Plataforma Full-Stack de Alta Performance para Gerenciamento de Produtividade, Hábitos, Metas e Organização Pessoal.
</p>

<p align="center">
  <a href="/images/1.png"><strong>📍Acesse a Aplicação em Produção 📍</strong></a>
</p>

<p align="center">
  <img src="path/to/sua/imagem/dashboard.png" alt="Taskibit Dashboard Overview" width="100%" />
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

---

## 🛠️ Engenharia de Performance e UX Aplicada

- **⚛️ Optimistic UI (`useOptimistic`):** Otimização radical na experiência do usuário. Ações de alternância de status, marcação de hábitos e movimentação de blocos Kanban refletem na tela instantaneamente antes mesmo da resposta do servidor ser concluída.
- **🧭 Controle de Cache & Navegação Otimizada:** Uso estratégico de primitivos de controle de cache (`no-store`/`no-cache`) combinado a estratégias de invalidação reativa em tempo de execução via `revalidatePath` e sincronização via `router.refresh()`.
- **📑 Validação e Gestão Avançada de Formulários:** Acoplamento controlado e declarativo entre **React Hook Form** e **Zod**. Garante menor quantidade de re-renderizações e segurança contra injeção de dados inválidos antes que cheguem à camada do Prisma ORM.

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

## 📸 Demonstração da Interface (Visual & Fluxos)

### 📊 Dashboard Central de Métricas e Indicadores

Interface orientada a dados (Data Viz), exibindo o panorama de produtividade semanal através de gráficos lineares, barras empilhadas e medidores estatísticos em tempo real de tarefas, hábitos e metas.

### 📅 Organização de Tarefas (Fluxo Kanban)

Gerenciamento de fluxos dinâmicos por dia da semana com arrasto interativo (Drag and Drop), priorização, subtarefas e rotulação flexível de tags.

### 🔥 Monitoramento Comportamental de Hábitos

Acompanhamento visual de comportamentos que se tornam rotina. Inclui histórico de execução sequencial e cálculos de progresso reativos.

### 📝 Notas Descentralizadas e Metas Estruturadas

Módulos independentes para registros de insights rápidos de código e acompanhamento detalhado de objetivos de médio/longo prazo com ordenação manual.

### 🏷️ Customização de Etiquetas e Perfil

Customização dinâmica de rotulagem com visualização inteligente e automatizada do contraste de acessibilidade (texto branco ou preto) sobre a cor customizada.

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

---

## 📄 Licença

Este projeto está licenciado sob a licença **MIT**.

---
