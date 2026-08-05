# Registro de gaps e premissas

## Como usar

Um gap impede promover uma proposta a requisito ou decisão. Cada item precisa de
evidência, owner e destino antes de ser encerrado. A ausência de resposta não
autoriza escolher a opção mais familiar.

## G-001 — Segmento e episódio de problema

**Status:** aberto, crítico.

**Premissa em risco:** desenvolvedores sofrem custo material ao reconstruir
contexto de arquitetura.

**Evidência necessária:** relatos recentes, frequência, consequência,
ferramenta atual e disposição de mudança por segmento.

**Destino:** RQ-001/RQ-002 e EXP-001.

## G-002 — Custo versus valor da representação

**Status:** aberto, crítico.

**Premissa em risco:** a atividade de representar um sistema cria mais clareza
do que burocracia.

**Evidência necessária:** observação de participantes criando uma representação
e identificando lacunas antes de implementar.

**Destino:** RQ-003/RQ-006 e EXP-002.

## G-003 — Vocabulário semântico mínimo

**Status:** aberto, crítico para POC.

**Premissa em risco:** poucos conceitos conseguem representar sistemas
heterogêneos sem virar UML rígida ou texto sem estrutura.

**Evidência necessária:** exemplos de domínios distintos, ambiguidades
registradas e perguntas que a representação consegue responder.

**Destino:** RQ-005 e EXP-004.

## G-004 — Valor do canvas e do inspector

**Status:** aberto.

**Premissa em risco:** um canvas revela relações e lacunas que texto ou lista
não revelam; um inspector torna intenção compreensível.

**Evidência necessária:** comparação de tarefas e compreensão com diferentes
projeções da mesma representação.

**Destino:** RQ-006/RQ-007 e mapa de experiências.

## G-005 — Necessidade de desktop e local-first

**Status:** aberto.

**Premissa em risco:** offline, privacidade, filesystem ou desempenho são
requisitos percebidos pelo primeiro segmento.

**Evidência necessária:** necessidades de uso, dados e distribuição; comparação
com alternativas web/local.

**Destino:** direção técnica antes de selecionar runtime.

## G-006 — Persistência, evolução e interoperabilidade

**Status:** aberto.

**Premissa em risco:** armazenamento local transacional e JSON de exportação
atendem evolução, backup, portabilidade e compatibilidade.

**Evidência necessária:** casos de mudança de representação, histórico,
portabilidade e compartilhamento.

**Destino:** RQ-008/RQ-009 e POC futura.

## G-007 — Contexto para agentes

**Status:** aberto.

**Premissa em risco:** contexto estruturado melhora respostas sem custo de
curadoria desproporcional.

**Evidência necessária:** experimento controlado com tarefas pré-registradas,
rubrica e comparação com fontes dispersas.

**Destino:** RQ-004 e EXP-003.

## G-008 — Extensibilidade e segurança de plugins

**Status:** aberto, pós-POC.

**Premissa em risco:** linguagens, frameworks, visualizações e provedores
precisam de extensibilidade desde o núcleo.

**Evidência necessária:** pelo menos dois casos de extensão reais que não caibam
no Core sem acoplamento indevido, mais modelo de ameaça.

**Destino:** RQ-010 e futura proposta de SDK.

## G-009 — Terminologia durável

**Status:** aberto.

**Premissa em risco:** um nome pode carregar a identidade do produto sem reduzir
o conceito a diagrama, grafo ou implementação.

**Evidência necessária:** teste de compreensão com pessoas do segmento,
comparação de candidatos e avaliação de neutralidade de paradigma.

**Destino:** `system-representation-concept.md`.

## G-010 — Fronteira entre representação e código

**Status:** aberto, crítico para a visão (elevado na 0.5).

**Premissa em risco:** a representação pode permanecer fonte de verdade sem
sincronização bidirecional prematura ou reconstrução manual inviável.

**Evidência necessária:** escolha explícita entre modos spec-first /
spec-anchored / spec-as-source; protótipos e mudanças controladas com
proveniência.

**Destino:** Q-LOOP-* em `open-questions-vision-0.5.md`; RQ-008/RQ-009;
pesquisa SDD em `research-notes-vision-0.5.md`.

## G-011 — Autoridade e drift após implementação por agente

**Status:** aberto, crítico para a visão.

**Premissa em risco:** “modelar → agente implementa” continua útil depois da
primeira geração, quando humanos editam código ou o agente erra.

**Evidência necessária:** política de produto debatida + cenários de revisão;
depois experimento com usuários do segmento.

**Destino:** visão 0.5; Q-LOOP-001/002; EXP futuros.

## G-012 — Colaboração multi-dev / branches com grafo semântico

**Status:** aberto.

**Premissa em risco:** vários desenvolvedores em branches diferentes conseguem
usar a representação sem merge inviável ou dual source of truth.

**Evidência necessária:** modelo de versionamento da representação; comparação
com docs-as-code / SDD em monorepo.

**Destino:** Q-COLLAB-001/002.
