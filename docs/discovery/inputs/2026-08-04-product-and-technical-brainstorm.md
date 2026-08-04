# Brainstorming de produto e direção técnica — 2026-08-04

## Status e uso

Este documento preserva o contexto fornecido pelo product owner em 2026-08-04.
Ele é material de entrada para discovery: descreve intenções, propostas e
hipóteses; não registra decisões de arquitetura, requisitos aceitos ou
capacidades entregues.

A síntese rastreável deste input será distribuída entre:

- [`../../product/product-specification.md`](../../product/product-specification.md);
- [`../../product/capability-map.md`](../../product/capability-map.md);
- [`../technical-context.md`](../technical-context.md);
- [`../system-representation-concept.md`](../system-representation-concept.md);
- [`../system-model-candidate.md`](../system-model-candidate.md).

## Matriz de rastreabilidade

Cada bloco abaixo preserva o status de **proposta** ou **hipótese** até receber
evidência e approval.

- **Nome maior que “modelagem” e candidatos LSR/SKM/CSM** → conceito provisório
  e critérios de nomenclatura em
  [`../system-representation-concept.md`](../system-representation-concept.md);
  gap G-009 e RQ-012.
- **Visão desktop, local-first, Tauri, Rust, React, SQLite, JSON e bibliotecas**
  → direção técnica candidata em [`../technical-context.md`](../technical-context.md);
  gaps G-005/G-006, RQ-013 e EXP-006.
- **Core, grafo, persistência, Context Builder, IA, MCP, parsers e plugins** →
  limites e perguntas técnicas em [`../technical-context.md`](../technical-context.md);
  gaps G-007/G-008/G-010 e RQ-015.
- **Fluxos de produto, workspace, IA, geração, importação, plugins e runtime**
  → estágios e fluxos em [`../technical-context.md`](../technical-context.md);
  experiência candidata em [`../../product/experience-map.md`](../../product/experience-map.md).
- **Project, Workspace, Domain, Module, Component, Behavior, Relationship e
  Constraint** → vocabulário não canônico em
  [`../system-model-candidate.md`](../system-model-candidate.md); gap G-003.
- **Fronteiras contra IDE, Git, CI/CD, cloud e no-code** → especificação de
  produto e limites em [`../../product/product-specification.md`](../../product/product-specification.md)
  e [`../technical-context.md`](../technical-context.md).
- **Fases, capacidades e telas** → capabilities, backlog e mapa de experiência
  em [`../../product/capability-map.md`](../../product/capability-map.md),
  [`../product-backlog.md`](../product-backlog.md) e
  [`../../product/experience-map.md`](../../product/experience-map.md).

## Conceito que precisa de nome

“Modelagem” parece pequeno demais, pois remete a UML, diagramas e engenharia de
software tradicional. A intenção é uma representação canônica, viva e
semanticamente rica do sistema, da qual diagramas, código, documentação, testes
e contexto para agentes são projeções.

Nomes sugeridos para pesquisa:

- Living System Representation (LSR);
- System Knowledge Model (SKM);
- Canonical System Model (CSM).

O objetivo é encontrar um conceito durável, comparável a termos que moldaram
categorias de produto como Git Repository, Workspace, DOM ou Virtual DOM.

## Direção técnica proposta

### Visão de arquitetura

O produto é imaginado como uma aplicação desktop multiplataforma para pensar e
representar software. Não deve ser uma IDE tradicional, editor UML, plataforma
low-code ou dependente de um provedor de IA.

Princípios propostos:

- local-first e offline-first quando possível;
- multiplataforma, modular, extensível e orientada a plugins;
- open source;
- independente de linguagem e de provedores de IA;
- arquitetura explícita, legível e sustentável no longo prazo.

### Stack candidata

- **Runtime desktop:** Tauri 2, para empacotamento, janela nativa, filesystem,
  IPC, integração com sistema operacional, segurança e desempenho.
- **Camada nativa:** Rust, candidata a Core Engine, Graph Engine, persistência,
  runtime de plugins, APIs nativas, tarefas em segundo plano, integração Git e
  futuros parsers. A intenção é não misturar lógica de UI nessa camada.
- **Frontend:** React e TypeScript, por ecossistema, compatibilidade com canvas,
  editor, command palette e bibliotecas de docking.
- **Canvas:** React Flow para nós, relacionamentos, zoom, pan e visualizações
  customizadas.
- **Editor embarcado:** Monaco para especificações, scripts, prompts e futura
  DSL.
- **Estado local:** Zustand.
- **Estado assíncrono/remoto:** TanStack Query.
- **Roteamento de workspaces:** TanStack Router.
- **Persistência primária:** SQLite, por ser local, transacional e madura.
- **Interoperabilidade:** JSON para backup, exportação, importação, APIs,
  contexto de IA e comunicação com plugins; não como representação interna.

Tecnologias futuras sob avaliação: Tree-sitter, LSP, CRDTs, Yjs, Petgraph,
extensões SQLite, DuckDB, plugins WASM, gRPC, event sourcing, command pattern e
atualizações de grafo inspiradas em ECS.

### Estrutura e módulos candidatos

Estrutura inicial imaginada:

```text
root/
├── app/
├── core/
├── plugins/
├── docs/
├── specs/
├── prototype/
├── scripts/
├── resources/
└── tests/
```

No frontend, organização feature-first: `components`, `features`, `workspaces`,
`canvas`, `explorer`, `panels`, `hooks`, `stores`, `services`, `commands`,
`plugins` e `utils`.

Módulos conceituais candidatos:

- Project Manager;
- Graph Engine;
- Persistence;
- Plugin Loader;
- Workspace Manager;
- AI Gateway;
- Git Manager;
- Context Builder;
- Command Bus;
- Parser Engine futuro;
- Generator Engine futuro.

## Ideias de capacidade e fluxo

### Atividade central

```text
Criar projeto
→ definir domínios
→ criar módulos
→ modelar comportamentos
→ definir relacionamentos
→ refinar arquitetura
→ validar representação
→ gerar contexto para IA
→ gerar ou revisar código
→ sincronizar representação
→ registrar mudanças
```

O sistema deve permitir aprofundar a representação gradualmente:

```text
Domain → Module → Component → Behavior → Relationship → Constraint → Implementation
```

### Workspaces e explorer

Um Workspace seria uma visão sobre o mesmo projeto: arquitetura, domínio,
backend, frontend, banco, infraestrutura, testes, requisitos ou IA. A
visualização muda, mas a representação subjacente permanece a mesma.

Hierarquia conceitual sugerida:

```text
Project
├── Domains
│   ├── Modules
│   │   ├── Components
│   │   ├── Behaviors
│   │   └── Relationships
│   └── Resources
├── Requirements
├── Architecture
├── Documentation
├── Tests
├── AI Sessions
└── Plugins
```

### IA, código e importação

Um Context Builder futuro reuniria workspace atual, nós selecionados,
arquitetura, requirements, ADRs, documentação, mudanças Git e conversas
anteriores antes de falar com um LLM. Provedores como OpenAI, Anthropic, Gemini,
OpenRouter e modelos locais seriam adaptados por uma abstração comum.

MCP é a direção preferida para futuras integrações com GitHub, Linear, Notion,
documentação, filesystem, Git e plugins.

Agentes futuros poderiam especializar-se em arquitetura, documentação, geração,
testes, review, refactoring e contexto. O início pode conter apenas um agente
generalista.

Importação de código não pertence ao MVP. Uma direção futura seria:

```text
Existing project → parser → Tree-sitter/LSP/AST → semantic analysis
→ System Representation → graph → edição interativa
```

Geração também é futura:

```text
System Representation → Context Builder → AI provider → generated code
→ review → synchronization
```

## Plugins

Plugins devem contribuir linguagens, frameworks, nós visuais, generators,
provedores de IA, exporters, importers, validators, templates e pipelines de
teste. Eles estendem, mas não substituem, um Core pequeno e estável.

Lifecycle desejado:

```text
Startup → discovery → manifest validation → dependency resolution
→ sandbox → initialization → registration → runtime
```

## Fronteiras pretendidas

O produto deve ser responsável por:

- representação de sistemas e conhecimento de projeto;
- modelagem/visualização arquitetural;
- construção de contexto para IA;
- plataforma de plugins;
- grafo, workspaces, validação e persistência local.

O produto não deve substituir:

- Git, GitHub, CI/CD ou gerenciadores de pacote;
- hosting de aplicações ou infraestrutura cloud;
- plataforma no-code;
- IDE de propósito geral.

## Linguagem interna e invariantes desejados

Um futuro `SYSTEM_MODEL.md` deveria descrever conceitos como Project, Workspace,
Domain, Module, Component, Behavior, Relationship e Constraint; relacionamentos
permitidos e invariantes que o Core preserva.

Ainda não foram definidos: representação interna, modelo canônico, SDK de
plugins, camada de IA, persistência do grafo, workspaces, DSL, taxonomia de nós,
sincronização com código, orquestração multiagente, colaboração e segurança de
plugins.
