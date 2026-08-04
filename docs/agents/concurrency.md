# Paralelismo e prevenção de conflitos

## Objetivo

Paralelismo é uma tática do `Orchestrator`, não uma substituição para challenge,
approval ou review. Ele só é permitido quando preserva uma única versão coerente
do conhecimento.

## Pré-condições

Antes de iniciar tasks paralelas, o plano deve registrar:

1. uma task com ID e owner único para cada fatia;
2. entradas, saídas e dependências declaradas;
3. allowlist de paths por task;
4. arquivos de estado que só um owner pode editar;
5. matriz de conflitos;
6. critério de reconciliação antes do handoff para review.

Sem esses itens, executar de forma sequencial.

## Arquivos de estado

`session.yaml`, approvals e conclusões são arquivos de coordenação. Uma única
identidade recebe a autoridade de escrita para cada um:

- `Orchestrator` atualiza fase, revisão, owners e tarefas pendentes;
- humano aprovador cria ou atualiza approval;
- `Reviewer` cria revisões;
- `Concluder` cria conclusão e disposition de learnings.

Quem executa delivery pode anexar evidências no artefato de sua task, mas não
avança fase nem remove tarefas de outra pessoa.

## Matriz de conflitos

O plano deve usar este formato quando houver mais de uma task ativa:

```text
Task: D-001
Owner: Research/Product
Allowlist: docs/discovery/interviews/
Depends on: none
Conflicts with: D-003

Task: D-002
Owner: Modeling/Architecture
Allowlist: docs/modeling/examples/
Depends on: none
Conflicts with: none
```

Tasks que compartilham arquivo, dependência não concluída, hipótese ainda não
aprovada ou autoridade de estado são conflitantes. Elas não podem iniciar em
paralelo.

## Tags de domínio

Cada task recebe uma ou mais tags para tornar sua responsabilidade visível:

- `[lm:product]`
- `[lm:research]`
- `[lm:modeling]`
- `[lm:architecture]`
- `[lm:documentation]`
- `[lm:qa]`

As tags não definem ferramenta ou linguagem. Elas descrevem a fronteira de
conhecimento responsável pela entrega.

## Reconciliação

Antes de `delivery → review`, o `Orchestrator` deve:

1. confirmar que cada task pendente tem resultado ou bloqueio explícito;
2. verificar que nenhuma allowlist foi violada;
3. integrar links de evidência no `session.yaml`;
4. comparar a matriz de conflitos com os paths efetivamente alterados;
5. atualizar `pendingTasks` uma única vez;
6. incrementar a revisão se alguma mudança alterar plano, escopo ou dependência.

Se houver discrepância, retornar a task responsável. O reviewer não deve
reconciliar estado em nome do delivery.

## Futuras automações

Hooks ou scripts de handoff só poderão ser introduzidos quando esse processo for
executado manualmente de modo consistente. Uma proposta de automação deve
definir autoridade única por transição, chave de deduplicação por sessão e
revisão, comportamento diante de falhas e testes contra loops.
