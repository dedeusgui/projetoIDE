# Living Model

> Um ambiente para pensar, projetar e evoluir software a partir de um modelo
> vivo — antes da implementação.

## Estado do projeto

O projeto está em **discovery de produto**. Ainda não há stack, arquitetura
técnica, modelo canônico, integração de IA ou MVP implementado. O propósito
atual é reduzir incertezas sobre o problema, o público e a menor experiência
capaz de validar a hipótese central.

## Ideia central

O código descreve uma implementação. O sistema deve existir independentemente
do código, em uma representação estruturada que pessoas e agentes de IA possam
consultar, discutir e evoluir.

Leia o [manifesto](docs/product/manifesto.md) e o
[contexto de produto](docs/product/product-context.md) antes de propor uma
decisão ou alteração.

## Como navegar

- [Perguntas de research](docs/discovery/research-backlog.md): incertezas
  priorizadas que precisam de evidência.
- [Plano de validação](docs/discovery/validation-plan.md): experimentos e sinais
  de decisão para as hipóteses atuais.
- [ADR-0001](docs/architecture/adr/ADR-0001-governanca-de-conhecimento-e-decisoes.md):
  como decisões e conhecimento serão versionados.
- [Workflow de agentes](docs/agents/workflow.md): papéis, fases, gates e
  artefatos de uma sessão.
- [Instruções para agentes](AGENTS.md): ponto de entrada operacional para
  qualquer pessoa ou agente que atuar no repositório.

## Princípios de trabalho

1. O modelo e suas decisões explícitas são o ativo principal; código é uma
   projeção de implementação.
2. Hipótese não é fato, e conversa não é aprovação.
3. Pessoas mantêm a autoridade sobre decisões de produto e arquitetura.
4. Evidências, decisões e riscos devem permanecer rastreáveis em arquivos.
5. O escopo só cresce quando uma hipótese ou experimento justificar esse custo.

## Próxima ação

Abra a sessão-semente em
[`docs/agents/sessions/2026-08-04-discovery-foundation/`](docs/agents/sessions/2026-08-04-discovery-foundation/)
e escolha, com aprovação humana, a primeira pergunta de discovery a investigar.
