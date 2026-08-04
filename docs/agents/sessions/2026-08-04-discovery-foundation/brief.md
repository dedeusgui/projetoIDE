# Brief — 2026-08-04-discovery-foundation

## Identificação

- Revisão: `1`
- Owner: `bootstrap-orchestrator`
- Trilha: `discovery`
- Fontes de entrada:
  - [`manifesto`](../../../product/manifesto.md)
  - [`contexto de produto`](../../../product/product-context.md)
  - [`backlog de research`](../../../discovery/research-backlog.md)
  - [`brainstorming técnico e de produto`](../../../discovery/inputs/2026-08-04-product-and-technical-brainstorm.md)

## Objetivo

Preservar o brainstorming atual e transformá-lo em especificação, capabilities,
backlog, fluxos, direção técnica e modelo conceitual candidatos. O resultado
deve dar continuidade ao discovery sem converter escolhas de produto ou
tecnologia em decisões aceitas.

## Contexto

O projeto propõe uma representação viva de software que preserve conhecimento
de domínio, arquitetura, comportamentos, decisões e relações para pessoas e
agentes. O product owner trouxe uma direção técnica extensa, fluxos conceituais,
fronteiras e um pedido de especificação rica e revisável para orientar o
desenvolvimento com validação humana contínua.

## Classificação

### [FATO]

- O repositório está em discovery e não contém implementação do produto.
- Não há stack, modelo canônico, banco, provedor de IA ou arquitetura técnica
  aceitos.
- O manifesto define que a representação deve permanecer independente do código.

### [HIPÓTESE]

- Modelar um sistema novo e derivar contexto estruturado para agentes pode ser
  a experiência principal capaz de validar a proposta de valor.
- Desktop local-first, canvas, extensibilidade e IA agnóstica podem ser meios
  adequados para a POC, mas ainda precisam de requisitos e evidências.
- Um vocabulário semântico pequeno pode representar sistemas sem reproduzir UML
  cerimonial.

### [DECISÃO]

- `System Representation` será o termo provisório; LSR, SKM e CSM permanecem
  candidatos de pesquisa.
- A direção técnica será registrada como dossiê de discovery, e não como
  arquitetura adotada.
- A especificação usará “modelar um sistema novo do zero e derivar contexto
  estruturado para agentes” como experiência norteadora a validar.

### [RISCO]

- Tratar brainstorming como requisito aceito e criar escopo de IDE, Git,
  CI/CD, cloud ou low-code.
- Fixar stack ou schema antes de validar problema, público e custo de modelagem.
- Confundir fluxos futuros com capacidade de POC ou MVP.

### [PERGUNTA]

- Quais partes da direção proposta são necessárias para validar o problema e
  quais devem ficar fora da primeira POC?

## Limites

- Inclui: documentação de contexto, síntese de produto, UX candidata, backlog,
  direção técnica proposta, gaps e modelo conceitual candidato.
- Não inclui: entrevistas, protótipo, POC, escolha de stack, definição de
  modelo canônico, SDK, integração com IA ou implementação.

## Resultado e evidência esperados

Um conjunto de documentos vinculados ao brainstorming que permita a uma pessoa
independente identificar proposta, hipótese, lacuna, fase, dependência e gate
humano de cada capacidade relevante.

## Handoff

- Próximo papel: `Challenger`.
- Condição de avanço: `plan.md` da revisão `1` precisa definir artefatos,
  fronteiras e critérios de não-decisão.
