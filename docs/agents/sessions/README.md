# Sessões de agentes

## Objetivo

Uma sessão é a unidade versionada de trabalho colaborativo entre pessoas e
agentes. Ela mantém contexto, estado, evidências e decisões fora do chat.

As sessões deste repositório usam o contrato definido em
[`../artifact-contracts.md`](../artifact-contracts.md) e o fluxo descrito em
[`../workflow.md`](../workflow.md).

## Estrutura

Cada sessão fica em uma pasta com nome:

```text
AAAA-MM-DD-descricao-curta/
```

Estrutura mínima:

```text
AAAA-MM-DD-descricao-curta/
├── session.yaml
├── brief.md
├── plan.md
├── challenge.md
├── approvals/
│   └── approval-<revisao>.md
├── tasks/
├── reviews/
│   └── review.md
└── conclusion.md
```

Uma sessão em fase inicial pode não ter todos os arquivos. O `session.yaml`
deve declarar a fase real e listar arquivos ausentes como trabalho pendente; a
ausência nunca autoriza pular um gate.

## Estado de sessão

`session.yaml` é o índice operacional. Ele registra:

- identificador, trilha, fase e revisão;
- objetivo e baseline;
- owners e tarefas pendentes;
- approvals, evidências e riscos;
- perfil de verificação;
- gates humanos pendentes.

Cada gate humano tem ID e referencia a approval e condição de origem, sua
revisão, owner, fase de avaliação, status e evidência de resolução.

Somente o `Orchestrator` atualiza `phase`, `revision` e `pendingTasks`. O papel
que emite um handoff propõe a transição e anexa evidências; o `Orchestrator`
persiste o estado somente depois de validar o pacote e reconciliar tarefas.

## Ciclo de vida

1. Criar `session.yaml` e `brief.md`.
2. Produzir `plan.md` e, quando necessário, task sheets.
3. Registrar `challenge.md`; devolver para revisão se o veredito não for `pass`.
4. Registrar approval humana antes de iniciar execução.
5. Executar tarefas dentro das allowlists e manter evidências.
6. Produzir revisão independente nos dois eixos.
7. Registrar `conclusion.md`, incluindo aprendizados e gates pendentes.

O estado `concluded` só é válido quando não há bloqueio de revisão e todos os
gates requeridos foram resolvidos ou transferidos explicitamente para uma nova
sessão aprovada.

## Sessão-semente

[2026-08-04-discovery-foundation](2026-08-04-discovery-foundation/) inicia o
discovery deste produto. Ela está deliberadamente antes de approval: contém
perguntas prioritárias, mas não pressupõe que uma pessoa tenha autorizado uma
solução ou experimento específico.
