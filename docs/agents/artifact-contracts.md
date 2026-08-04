# Contratos de artefatos de sessão

## Princípios

Uma sessão existe para produzir conhecimento rastreável, não para aparentar
progresso. Cada artefato deve ter owner, revisão, links de entrada e um estado
claro. Campos não conhecidos devem ser marcados como `unknown`, nunca
preenchidos por inferência.

Os templates em [`templates/`](templates/) implementam estes contratos. Se
template e esta página divergirem, a sessão deve ser bloqueada e a divergência
precisa ser corrigida antes do handoff.

## Convenções comuns

Todo artefato de sessão informa, quando aplicável:

- `sessionId` e `revision`;
- owner ou papel responsável;
- fontes de entrada e evidências;
- itens classificados como `[FATO]`, `[HIPÓTESE]`, `[DECISÃO]`, `[RISCO]` ou
  `[PERGUNTA]`;
- links para artefatos que ele atualiza ou dos quais depende;
- próximo handoff ou razão de bloqueio.

## Brief

**Produzido por:** `Orchestrator` com apoio de `Research/Product`.

**Propósito:** transformar uma solicitação em objetivo delimitado e verificável.

**Deve conter:** contexto, pergunta ou objetivo, resultado esperado, não-escopo,
fatos, hipóteses, decisões que exigem humano, riscos iniciais e trilha sugerida.

**Não pode:** aprovar escopo, escolher solução técnica ou inventar evidência.

## Plano

**Produzido por:** `Orchestrator`.

**Propósito:** decompor o brief em tarefas independentes, com owners, ordem,
evidência esperada e allowlist de paths.

**Deve conter:** baseline, critérios de entrada e saída, dependências, tags de
domínio, matriz de conflito quando houver paralelismo e perfil de verificação.

**Não pode:** pular o challenge, atribuir a mesma tarefa a dois owners ou
autorizar mudança externa.

## Challenge

**Produzido por:** `Challenger` independente.

**Propósito:** testar o plano contra escopo, premissas, evidências ausentes,
efeitos reversíveis, fronteiras e critérios de sucesso.

**Deve conter:** veredito (`pass`, `revise` ou `block`), achados priorizados,
evidência de cada achado e retorno esperado.

**Não pode:** reescrever o produto, implementar a solução ou aprovar o próprio
plano.

## Approval

**Produzido por:** humano responsável; pode ser preparado pelo `Orchestrator`.

**Propósito:** registrar autorização explícita para seguir para a próxima fase.

**Deve conter:** pacote aprovado, revisão, escopo autorizado, riscos aceitos,
gates humanos ainda pendentes, data e identidade do aprovador.

**Não pode:** ser substituído por texto de chat, ser inferido de silêncio ou
aprovar material que não referencia.

## Task sheet

**Produzido por:** `Orchestrator`; executado por um owner de `Delivery`,
`Research/Product` ou `Modeling/Architecture`.

**Propósito:** tornar uma unidade de trabalho independente e verificável.

**Deve conter:** ID, objetivo, owner, entradas, saída, critérios de aceite,
allowlist de paths, dependências, riscos e evidência requerida.

**Não pode:** ampliar o escopo aprovado, editar paths fora da allowlist ou
alterar estado de sessão que pertença a outro owner.

## Review

**Produzido por:** `Reviewer` que não produziu a entrega revisada.

**Propósito:** avaliar dois eixos separadamente:

1. aderência ao brief, plano e approval;
2. qualidade, consistência, rastreabilidade e evidência.

**Deve conter:** baseline avaliado, resultados por eixo, bloqueios, pedidos de
ajuste, gates humanos e veredito.

**Não pode:** implementar correções, fechar a sessão com bloqueio aberto ou
declarar aprovado um gate humano ausente.

## Conclusion

**Produzido por:** `Concluder`, distinto de quem executou e revisou.

**Propósito:** fechar ou pausar uma sessão sem perder decisões, evidências,
resultados, riscos e próximos passos.

**Deve conter:** objetivo, resultado, evidências, decisões confirmadas,
hipóteses alteradas, gates pendentes e destino de cada aprendizado.

O destino de um aprendizado é um de:

- `practice`;
- `promote-to-ADR`;
- `promote-to-skill`;
- `research-backlog`;
- `discard`.

**Não pode:** ocultar resultado negativo, declarar sessão concluída com gate
obrigatório em aberto ou modificar decisão aceita sem o artefato apropriado.

## Evidência e rastreabilidade

Uma afirmação relevante deve poder responder:

1. Qual é a fonte?
2. Em que sessão foi usada ou produzida?
3. É fato, hipótese, decisão, risco ou pergunta?
4. Quem aprovou a mudança de estado, quando aplicável?
5. Qual documento precisa ser atualizado se a afirmação mudar?

Se essas perguntas não puderem ser respondidas por links e conteúdo local, a
afirmação é um item de backlog de documentação, não uma base para decisão.
