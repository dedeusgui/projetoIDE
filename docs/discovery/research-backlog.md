# Backlog de research

## Como usar

Cada item deste backlog é uma pergunta aberta, não um requisito. Uma sessão de
discovery deve selecionar uma pergunta, definir evidências aceitáveis e registrar
o resultado em sua conclusão. Duas perguntas podem ser agrupadas em uma única
investigação somente se o brief explicar a dependência, o plano separar as
evidências e o approval autorizar o agrupamento. Itens só podem ser rebaixados,
desdobrados ou encerrados com evidência vinculada.

Prioridade `P0` significa que a resposta altera a continuidade do discovery.
`P1` altera a forma do MVP, mas não impede investigar o problema. `P2` fica para
depois de uma hipótese de valor validada.

## P0 — problema e público

### RQ-001 — Qual segmento sente o problema com maior intensidade?

Investigar desenvolvedores individuais, tech leads, arquitetos, equipes de
produto e times que usam agentes de IA com frequência. A resposta precisa
identificar contexto, frequência, consequência e alternativa atual de cada
segmento.

**Decisão desbloqueada:** primeiro público de entrevistas e protótipo.

### RQ-002 — Qual trabalho perdido queremos reduzir?

Separar custos de reconstruir contexto, retrabalho arquitetural, documentação
obsoleta, revisão de mudanças feitas por IA e onboarding. Não assumir que todos
ocorrem juntos.

**Decisão desbloqueada:** problema prioritário e mensagem de valor.

### RQ-003 — Pessoas modelariam antes de implementar?

Investigar quando uma etapa de modelagem é percebida como ajuda, burocracia ou
duplicação do código. Comparar projetos greenfield, legados e mudanças locais.

**Decisão desbloqueada:** limite aceitável de esforço de modelagem.

## P0 — hipótese de contexto para IA

### RQ-004 — Que contexto uma LLM realmente precisa?

Comparar uma tarefa representativa executada com código/documentação dispersos e
com uma Spec estruturada. Medir fidelidade às regras, perguntas necessárias,
retrabalho de revisão e tempo para atingir uma resposta utilizável.

**Decisão desbloqueada:** primeiro formato de contexto a prototipar.

### RQ-005 — O que torna uma representação semanticamente útil?

Identificar o menor conjunto de conceitos que permite expressar domínio,
responsabilidades, regras, relações, fluxos e decisões sem reproduzir UML
cerimonial.

**Decisão desbloqueada:** escopo de uma POC de modelo interno.

## P1 — experiência de modelagem

### RQ-006 — Como o usuário cria e refina um modelo?

Avaliar se o caminho começa por problema, domínio, casos de uso, fluxos,
componentes, texto livre ou uma combinação guiada. Investigar onde um canvas
ajuda e onde ele apenas desenha informação sem significado.

**Decisão desbloqueada:** fluxo inicial de experiência do MVP.

### RQ-007 — Como o modelo evidencia inconsistências?

Determinar quais erros são realmente valiosos: relação inválida, regra ausente,
responsabilidade ambígua, dependência circular, decisão não registrada ou
divergência entre implementação e modelo.

**Decisão desbloqueada:** primeiras validações do modelo.

## P1 — evolução e interoperabilidade

### RQ-008 — Como o modelo evolui sem travar o projeto?

Investigar versionamento, compatibilidade, granularidade de mudanças e autoria
de decisões. O modelo precisa aceitar evolução gradual sem exigir remodelagem
total.

**Decisão desbloqueada:** requisitos de persistência e compatibilidade.

### RQ-009 — Quais saídas do modelo geram valor imediato?

Comparar exportação de contexto para agentes, documentação, teste, diagramas e
scaffolding. Não presumir geração de código como a saída mais valiosa.

**Decisão desbloqueada:** primeiro formato de exportação.

## P2 — ecossistema

### RQ-010 — Que extensões são essenciais ao núcleo?

Investigar quais pontos de extensão precisam existir desde o início e quais
podem permanecer internos no MVP: linguagens, frameworks, visualizações,
provedores de IA, estilos arquiteturais e pipelines.

**Decisão desbloqueada:** limites do núcleo e futura arquitetura de plugins.

### RQ-011 — Qual modelo de propriedade e colaboração é esperado?

Verificar expectativas sobre arquivos locais, repositório, histórico,
compartilhamento, permissões e abertura do formato.

**Decisão desbloqueada:** direção de produto para dados e colaboração após MVP.

## P2 — identidade e direção técnica

### RQ-012 — Qual nome explica o conceito sem reduzir o produto a diagrama?

Comparar `System Representation`, LSR, SKM e CSM em clareza, neutralidade de
paradigma, associação com UML e capacidade de acomodar múltiplas projeções.

**Decisão desbloqueada:** termo oficial de produto e a promoção, ou não, de um
futuro `SYSTEM_MODEL.md`.

### RQ-013 — Que requisitos justificam uma aplicação desktop local-first?

Investigar necessidades reais de offline, privacidade, filesystem, desempenho,
portabilidade e distribuição do primeiro segmento antes de escolher runtime ou
camada nativa.

**Decisão desbloqueada:** experimento técnico comparando opções de runtime.

### RQ-014 — Que projeções de UX ajudam a criar uma representação?

Avaliar o valor de explorer, canvas, inspector e feedback de validação em
comparação com fluxos textuais ou listas sobre o mesmo conhecimento.

**Decisão desbloqueada:** menor superfície de experiência para uma POC ou MVP.

### RQ-015 — O que precisa ser extensível desde o início?

Identificar casos concretos para linguagens, frameworks, visualizações,
providers e validações antes de definir Core, plugins ou SDK.

**Decisão desbloqueada:** fronteira inicial entre Core e extensibilidade.
