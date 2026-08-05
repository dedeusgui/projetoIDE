# Inventário documental — visão 0.5

**Status:** evidência de trabalho (2026-08-04).  
**Objetivo:** o que fica, o que corrige e o que falta para a documentação 0.5.

## Legenda

| Ação | Significado |
|------|-------------|
| manter | útil; alinhar só se contradizer a visão 0.5 |
| corrigir | desalinhado com a intenção atual do product owner |
| prematuro | útil depois; marcar limite (ex.: telas) |
| gap | falta na 0.5 |

## Product

| Arquivo | Ação | Nota |
|---------|------|------|
| [`manifesto.md`](../product/manifesto.md) | manter | Crença “modelo antes do código” ainda vale; reforçar agente-implementa na visão 0.5, não no manifesto ainda |
| [`product-context.md`](../product/product-context.md) | corrigir | Hipótese fraca demais (“contexto para agentes”); MVP/fora-do-MVP empurra geração/agentes para longe demais vs visão |
| [`product-specification.md`](../product/product-specification.md) | corrigir | Norte atual = exportar contexto; visão 0.5 = modelar → agente implementa |
| [`capability-map.md`](../product/capability-map.md) | corrigir | “Geração de código / agentes” só pós-MVP; marcar como candidatura antiga vs visão |
| [`experience-map.md`](../product/experience-map.md) | prematuro | Telas candidatas sem visão de sistema acordada — rebaixar a “rascunho antigo / não guia a 0.5” |

## Discovery

| Arquivo | Ação | Nota |
|---------|------|------|
| [`research-backlog.md`](research-backlog.md) | manter | RQ P0 ainda válidas; acrescentar perguntas de drift/loop |
| [`validation-plan.md`](validation-plan.md) | manter | EXP-001+ ainda fazem sentido |
| [`technical-context.md`](technical-context.md) | manter | Continua candidato; não é stack adotada |
| [`system-model-candidate.md`](system-model-candidate.md) | corrigir / estender | Base boa; falta vocabulário do core (Behavior, Scope, Language Extension) |
| [`system-representation-concept.md`](system-representation-concept.md) | manter | Termo provisório ok |
| [`gap-register.md`](gap-register.md) | corrigir | Incluir gaps de drift, branches, autoridade modelo↔código |
| [`next-session.md`](next-session.md) | manter | Pesquisa de problema continua; visão 0.5 não substitui entrevistas |
| [`product-backlog.md`](product-backlog.md) | prematuro | Backlog de entrega sem visão fechada — só candidato |
| [`inputs/2026-08-04-…`](inputs/2026-08-04-product-and-technical-brainstorm.md) | manter | Input histórico; não é canônico |

## Agents / arquitetura

| Arquivo | Ação | Nota |
|---------|------|------|
| Workflow, roles, templates, ADR-0001 | manter | Processo do repo; fora do escopo de produto 0.5 |
| Sessão `discovery-foundation` | manter | Concluded; base documental anterior |

## Gaps da 0.5 (antes desta entrega)

1. Doc curto de **visão de produto** (modelar → agente implementa; editor secundário).
2. **Core de modelagem** legível (conceitos + grafo/JSON + universal vs linguagem).
3. **Perguntas abertas** explícitas (drift, branches, colaboração, como pedir implementação).
4. **Notas de pesquisa** que validam/desafiam a tese (web + repo).
5. Alinhamento dos docs product que ainda dizem “só exportar contexto”.

## Saídas desta entrega

- [`../product/vision-0.5.md`](../product/vision-0.5.md)
- [`modeling-core-0.5.md`](modeling-core-0.5.md)
- [`open-questions-vision-0.5.md`](open-questions-vision-0.5.md)
- [`research-notes-vision-0.5.md`](research-notes-vision-0.5.md)
