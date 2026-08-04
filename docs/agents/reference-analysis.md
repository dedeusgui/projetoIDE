# Análise de referências para o workflow de agentes

## Objetivo

Definir um workflow de agentes adequado à fase de discovery deste projeto,
aproveitando mecanismos comprovados em projetos anteriores sem importar
cerimônia, automação ou decisões que dependam de uma base de código inexistente.

## Proveniência

| Referência | Commit consultado | Documentos principais |
| --- | --- | --- |
| `code-apes` | `8f6c0be26b6e75274d1928892579db3e63837b30` (`main`, sincronizado em 2026-08-04) | `agent.md`, `docs/agents/workflow.md`, `docs/agents/tracks.md`, sessões de agentes |
| `PICK` | `2ca70fdde77785c11a2ed635079e1466588df0bd` (`main`) | `docs/agents/workflow.md`, `docs/agents/routing.md`, `docs/agents/hooks.md` |

O `code-apes` local estava cinco commits atrás de `origin/main` antes da
sincronização. A comparação desta página usa o estado atualizado.

Fontes reproduzíveis:

- `code-apes`: <https://github.com/juninhos-comunidade/code-apes.git>, checkout
  consultado em `/home/dedeusgui/Dev/code-apes`;
- `PICK`: <https://github.com/dedeusgui/PICK>, checkout consultado em
  `/home/dedeusgui/Dev/PICK`.

Os paths locais facilitam rechecagem neste ambiente; os URLs e SHAs permitem
reproduzir a análise fora dele.

## Práticas adotadas

### Contexto e aprovação explícitos

Adotamos do `code-apes`:

- contexto persistido em arquivos de sessão, nunca dependente apenas do chat;
- distinção obrigatória entre `[FATO]` e `[DECISÃO]`;
- aprovação humana registrada em artefato, e não inferida de uma conversa;
- separação entre quem produz, revisa e conclui;
- feedback de aprendizados com destino explícito.

Essas regras protegem a hipótese central do produto: o conhecimento do sistema
deve sobreviver à conversa, à implementação e à troca de agentes.

### Cerimônia proporcional

Adotamos a ideia de trilhas do `code-apes`, mas inicialmente operamos somente:

- `discovery`, para pesquisas, decisões de produto e validações;
- `full`, reservada para mudanças futuras de implementação que cruzem
  fronteiras relevantes.

A trilha `light` permanece proposta, mas inativa até haver uma base de código,
um histórico de risco e critérios objetivos para classificá-la.

### Estado, revisão e paralelismo

Adotamos do PICK:

- estado de sessão versionado, com fase, revisão, baseline e tarefas pendentes;
- revisão independente em dois eixos: aderência ao artefato aprovado e qualidade
  das evidências/entrega;
- tags de domínio e uma matriz de conflitos para trabalho paralelo;
- reconciliação explícita do estado após handoffs.

O PICK registra que handoffs paralelos podem deixar tarefas pendentes
inconsistentes. Por isso, este projeto não permite que dois papéis avancem a
mesma transição nem atualizem o mesmo arquivo de estado sem owner definido.

## Práticas adaptadas

| Referência | Mecanismo | Adaptação neste projeto |
| --- | --- | --- |
| code-apes | `Helper → Documentação → Orchestrator → Challenger → Approval → Team → Reviewer → Concluidor` | No discovery, `Research/Product` e `Modeling/Architecture` substituem o Team de implementação. |
| code-apes | Linear como fonte de verdade de backlog | Não adotado agora. As perguntas e sessões vivem no repositório até selecionarmos uma ferramenta de gestão. |
| PICK | `phase.json` com fingerprint e verificações | Usaremos `session.yaml` legível por humanos; fingerprint e automação só entram quando houver validação reproduzível. |
| PICK | Tags de roteamento por área técnica | Usaremos tags de domínio (`product`, `research`, `modeling`, `architecture`) sem inferir stack. |

## Práticas postergadas

- hooks Cursor para handoff automático;
- scripts de transição de fase;
- validação em CI;
- profiles de verificação de código;
- integração com issues, PRs ou serviços externos;
- uso de agentes em paralelo para implementação.

O PICK exige deduplicação por sessão e revisão para que hooks não criem loops ou
condições de corrida. Sem uma implementação, testes e CI, introduzir esse
mecanismo agora apenas esconderia risco operacional.

## Práticas rejeitadas para esta fase

- tratar confirmação em chat como aprovação;
- permitir que o mesmo agente planeje, produza, revise e conclua uma sessão;
- declarar um gate humano como aprovado por ausência de objeção;
- escolher stack, banco, modelo canônico ou provedor de IA como consequência do
  workflow.

## Riscos a validar

1. **Custo de modelagem:** a representação pode custar mais do que o contexto
   que economiza. Os experimentos de discovery precisam medir esse equilíbrio.
2. **Compreensão por LLM:** uma Spec estruturada só agrega valor se produzir
   respostas mais fiéis do que documentação textual isolada.
3. **Deriva entre modelo e implementação:** o workflow documenta a intenção,
   mas ainda não prova sincronização bidirecional.
4. **Automação prematura:** scripts e hooks podem criar autoridade implícita
   sobre decisões que continuam humanas.
5. **Paralelismo:** múltiplos agentes sem isolamento de paths e dono do estado
   podem introduzir contradições na base de conhecimento.

## Decisão operacional

O núcleo do workflow será portátil e documental. Automação poderá ser proposta
em um ADR futuro somente após existirem artefatos de sessão estáveis, critérios
de verificação reproduzíveis e uma necessidade comprovada de reduzir trabalho
manual.
