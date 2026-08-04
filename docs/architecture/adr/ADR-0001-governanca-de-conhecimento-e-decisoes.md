# ADR-0001: Governar conhecimento e decisões como artefatos versionados

## Status

Proposta de bootstrap em 2026-08-04. Requer approval humana em arquivo antes de
ser considerada aceita.

## Contexto

O produto pretende fazer do modelo do sistema a referência primária para
pessoas e agentes. Essa proposta falha se hipóteses, aprovações, decisões,
evidências e aprendizados permanecerem em conversas efêmeras ou forem
confundidos entre si.

O repositório começa em discovery e ainda não possui código, ferramenta de
gestão externa ou modelo técnico definido. Precisamos de uma forma simples,
portátil e auditável de preservar o motivo de decisões sem antecipar stack.

## Decisão

O repositório versionará o conhecimento relevante em Markdown e YAML legíveis
por pessoas. A hierarquia de autoridade será:

1. manifesto e contexto de produto aprovados;
2. ADRs aceitos;
3. artefatos de sessão aprovados;
4. specs e resultados de experimentos vinculados a uma sessão;
5. código, testes e documentação de implementação futura.

Essa ordem não transforma documentos em fatos imutáveis. Um artefato superior
continua podendo ser substituído por uma decisão humana registrada, sem apagar
o histórico.

Todo registro deve classificar conteúdo como:

- **fato:** informação verificável com fonte;
- **hipótese:** afirmação a ser testada;
- **decisão:** escolha humana aprovada, com contexto e consequências;
- **risco:** possibilidade de impacto negativo ainda sem resolução;
- **pergunta aberta:** incerteza que orienta research;
- **evidência:** observação, fonte, experimento ou resultado que suporta ou
  enfraquece uma afirmação.

Os contratos de cada artefato ficam em
[`docs/agents/artifact-contracts.md`](../../agents/artifact-contracts.md).

## Alternativas consideradas

### Usar somente conversas e contexto do agente

É rápido no início, mas não é auditável, dificulta revisão humana e contradiz o
objetivo do produto de preservar contexto além de uma conversa.

### Adotar já uma ferramenta externa como fonte de backlog

Pode ser apropriado mais tarde, mas escolhe integração e fluxo de trabalho antes
de validar o público e o problema. Nesta fase, introduziria uma segunda fonte de
verdade sem benefício comprovado.

### Usar um grafo ou banco de dados desde o início

Pode ser necessário para a plataforma, mas seria uma decisão técnica prematura.
Arquivos versionados são suficientes para validar o processo de conhecimento e
para preservar sua evolução.

## Consequências

- Sessões devem conter links para suas fontes e evidências.
- Aprovação humana precisa existir em arquivo; chat não é substituto.
- Agentes não podem converter hipótese em decisão nem atualizar um ADR aceito
  silenciosamente.
- Uma mudança de decisão exige novo ADR que referencia o anterior como
  substituído, em vez de apagar contexto.
- A equipe aceita o custo inicial de escrever artefatos para medir se esse custo
  se paga em compreensão, qualidade e continuidade.

## Critérios para revisão

Esta decisão deve ser revisada quando houver evidência de que:

- o formato de arquivos não suporta os vínculos necessários;
- uma ferramenta externa se torna a fonte de trabalho mais adequada;
- a POC exige um armazenamento estruturado para o modelo canônico;
- o custo de manutenção excede o valor observado nos experimentos.

## Registro de bootstrap

Este ADR foi preparado junto da base documental inicial, antes de existir uma
sessão aprovada. Ele não autoriza por si só a adoção da governança: a primeira
sessão que chegar a `awaiting-approval` deve referenciá-lo explicitamente e
registrar, no bloco **ADRs e decisões de governança avaliados** do approval, a
decisão humana de aceitá-lo, revisá-lo ou rejeitá-lo.
