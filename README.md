# Living Model

> Um ambiente para modelar o sistema com clareza; o agente implementa a partir
> desse modelo vivo. Código na mão é apoio, não o centro.

## Estado do projeto

O projeto está em **discovery de produto**. Ainda não há stack, arquitetura
técnica, modelo canônico, integração de IA ou MVP implementado. A documentação
está em **visão 0.5**: norte alinhado, core candidato e perguntas abertas —
ainda sem validação com usuários.

## Ideia central

O código descreve uma implementação. O sistema deve existir independentemente
do código, numa representação estruturada (grafo/JSON semântico) que pessoas e
agentes usam — na visão, para **implementar** a partir do modelo, não só para
ler contexto solto de chat.

Comece por:

1. [Visão 0.5](docs/product/vision-0.5.md)
2. [Manifesto](docs/product/manifesto.md)
3. [Contexto de produto](docs/product/product-context.md)

## Como navegar

- [Visão 0.5](docs/product/vision-0.5.md): o que o produto é / não é.
- [Core de modelagem 0.5](docs/discovery/modeling-core-0.5.md): conceitos,
  grafo/JSON, universal vs linguagem.
- [Perguntas abertas](docs/discovery/open-questions-vision-0.5.md): drift,
  branches, agente, valor.
- [Notas de pesquisa 0.5](docs/discovery/research-notes-vision-0.5.md): SDD,
  drift, cruzamento com o repo.
- [Inventário 0.5](docs/discovery/vision-0.5-inventory.md): o que foi
  mantido/corrigido.
- [Perguntas de research](docs/discovery/research-backlog.md): incertezas P0+.
- [Plano de validação](docs/discovery/validation-plan.md): experimentos.
- [Especificação de produto](docs/product/product-specification.md): hipótese e
  critérios de avanço.
- [Mapa de capabilities](docs/product/capability-map.md): discovery / POC / MVP
  candidatos.
- [Mapa de experiências](docs/product/experience-map.md): **prematuro** (não
  guia UX agora).
- [Contexto técnico proposto](docs/discovery/technical-context.md): candidatos,
  não stack adotada.
- [System Representation](docs/discovery/system-representation-concept.md):
  termo provisório.
- [ADR-0001](docs/architecture/adr/ADR-0001-governanca-de-conhecimento-e-decisoes.md)
- [Workflow de agentes](docs/agents/workflow.md) · [AGENTS.md](AGENTS.md)

## Princípios de trabalho

1. O modelo e suas decisões explícitas são o ativo principal; código é uma
   projeção de implementação.
2. Hipótese não é fato, e conversa não é aprovação.
3. Pessoas mantêm a autoridade sobre decisões de produto e arquitetura.
4. Evidências, decisões e riscos devem permanecer rastreáveis em arquivos.
5. O escopo só cresce quando uma hipótese ou experimento justificar esse custo.
6. Visão ≠ POC ≠ MVP.

## Próxima ação

1. Product owner: confirmar ou ajustar a [visão 0.5](docs/product/vision-0.5.md).
2. Escolher 1–2 perguntas abertas + RQ P0 e abrir sessão de research (ver
   [`docs/discovery/next-session.md`](docs/discovery/next-session.md)).
