# Brief — 2026-08-04-discovery-foundation

## Identificação

- Revisão: `0`
- Owner: `Orchestrator` ainda não designado
- Trilha proposta: `discovery`
- Fontes de entrada:
  - [`manifesto`](../../../product/manifesto.md)
  - [`contexto de produto`](../../../product/product-context.md)
  - [`backlog de research`](../../../discovery/research-backlog.md)
  - [`plano de validação`](../../../discovery/validation-plan.md)

## Objetivo

Escolher uma pergunta P0 que reduza uma incerteza material sobre o problema e
preparar um plano de discovery para aprovação humana. Esta sessão não executa o
experimento nem assume uma resposta.

## Contexto

O produto propõe uma representação viva de software que preserve conhecimento
de domínio, arquitetura, comportamentos, decisões e relações para pessoas e
agentes. A hipótese principal afirma que modelagem prévia melhora a qualidade do
software e o contexto oferecido a agentes de IA, mas público, problema e custo
da modelagem ainda não foram validados.

## Classificação

### [FATO]

- O repositório está em discovery e não contém uma implementação do produto.
- Não há stack, modelo canônico, banco, provedor de IA ou arquitetura técnica
  aceitos.
- O manifesto define que o modelo deve permanecer independente do código.

### [HIPÓTESE]

- Existe um segmento para o qual reconstruir contexto arquitetural gera custo
  frequente e percebido.
- Uma modelagem viva pode compensar o esforço adicional de criá-la.
- Uma Spec estruturada pode melhorar a atuação de LLMs em uma tarefa real.

### [DECISÃO]

- A primeira pergunta P0, o segmento inicial e o método ainda exigem decisão
  humana.

### [RISCO]

- Começar pela solução ou formato de modelo antes de confirmar o problema.
- Medir preferência declarada em vez de comportamento real.
- Interpretar uma resposta de LLM sem rubrica e baseline como evidência.

### [PERGUNTA]

- Qual pergunta P0 deve ser investigada primeiro: segmento, custo do problema,
  aceitação de modelagem ou contexto para IA?

## Limites

- Inclui: seleção da primeira pergunta e preparação de plano para approval.
- Não inclui: entrevistas, protótipo, POC, escolha de stack, definição de
  modelo canônico ou implementação.

## Resultado e evidência esperados

Uma escolha humana registrada de uma pergunta P0, acompanhada de um plano que
define método, participantes ou material, evidência e sinais de apoio ou
invalidação.

## Handoff

- Próximo papel: humano responsável pela direção de produto.
- Condição de avanço: selecionar uma pergunta P0; o `Orchestrator` então
  prepara `plan.md`, submete ao `Challenger` e solicita approval em arquivo.
