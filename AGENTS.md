# Instruções para agentes

## Ponto de partida obrigatório

Antes de agir, leia nesta ordem:

1. [`README.md`](README.md);
2. [`docs/product/manifesto.md`](docs/product/manifesto.md);
3. [`docs/product/product-context.md`](docs/product/product-context.md);
4. [`docs/agents/workflow.md`](docs/agents/workflow.md);
5. a sessão ativa em [`docs/agents/sessions/`](docs/agents/sessions/).

O contexto do chat complementa arquivos; não substitui fonte canônica,
aprovação ou evidência.

## Regras inegociáveis

- Classifique afirmações relevantes como fato, hipótese, decisão, risco,
  pergunta ou evidência.
- Não converta hipótese em fato nem decisão humana em inferência própria.
- Não escolha stack, banco, modelo canônico, integração de IA ou arquitetura
  técnica sem evidência, ADR e approval humana.
- Não inicie delivery sem brief, plano, challenge e approval correspondente à
  mesma revisão.
- Não trate conversa como approval; use `approvals/`.
- Quem produz não revisa nem conclui a própria entrega.
- Não declare concluído quando houver gate humano, bloqueio de review ou
  evidência pendente.
- Mantenha o `session.yaml` coerente com os artefatos e respeite o owner de cada
  campo de estado.
- Em trabalho paralelo, respeite task sheet, tags e allowlist de paths.

## Escolha de trilha

Use [`docs/agents/tracks.md`](docs/agents/tracks.md):

- `discovery` para pergunta de produto, pesquisa, experimento ou exploração de
  modelagem;
- `full` para futura mudança transversa de implementação ou decisão
  arquitetural;
- `light` não está ativa.

Se houver dúvida, pare em `brief` e peça que o humano aprove a trilha e o
escopo. Não encurte a cerimônia por conta própria.

## Processo mínimo

1. Criar ou atualizar uma sessão usando os templates.
2. Produzir brief e plano com entradas, saídas e evidências esperadas.
3. Enviar para `Challenger`.
4. Aguardar approval humana em arquivo.
5. Executar somente as tasks autorizadas.
6. Solicitar review independente nos eixos de aderência e qualidade.
7. Registrar conclusão e destino de cada aprendizado.

## Autonomia

Dentro de um plano aprovado, agentes podem pesquisar, editar artefatos
autorizados, executar verificações locais e corrigir inconsistências locais.
Pare e solicite decisão humana para alteração de escopo, risco material,
decisão arquitetural, serviços externos, credenciais, custos, Git remoto,
commit, PR, merge, deploy, dados compartilhados ou ação irreversível.

## Qualidade documental

- Use links relativos para fontes internas.
- Declare lacunas em vez de preenchê-las com suposições.
- Mantenha arquivos curtos, específicos e atualizados.
- Registre evidência suficiente para uma pessoa independente repetir a
  interpretação.
- Consulte [`docs/agents/artifact-contracts.md`](docs/agents/artifact-contracts.md)
  antes de criar um artefato de sessão.
