# Candidato de modelo conceitual

## Status

Este é um vocabulário para explorar significado. Não é um `SYSTEM_MODEL.md`
canônico, schema, grafo, banco de dados, API ou taxonomia definitiva.

**Síntese 0.5 (ler primeiro):** [`modeling-core-0.5.md`](modeling-core-0.5.md)
— inclui Scope, Behavior, LanguageExtension e a direção grafo/JSON.

## Conceitos candidatos

### Project

Unidade de organização de conhecimento sobre um sistema. Um Project contém
representações, fontes, decisões e projeções relacionadas, mas não precisa
coincidir com um repositório de código.

### System Representation

Conjunto estruturado de afirmações sobre um sistema. É a referência candidata
para as projeções do produto, sem determinar como será persistida.

### Element

Algo relevante para entender o sistema. Domain, Module, Component, Resource,
Service ou Data Store podem futuramente ser especializações, mas não são tipos
fixados agora.

### Relationship

Conexão com significado explícito entre elementos ou outros conceitos. Uma linha
visual sem intenção, fonte ou tipo compreensível não satisfaz esse conceito.

### Responsibility

Intenção ou obrigação atribuída a um elemento. Responde “por que isso existe e
o que precisa preservar?”.

### Rule

Comportamento, condição ou política que o sistema deve respeitar. Pode ser
ligada a elemento, relação, fluxo ou fronteira.

### Flow

Sequência observável de interações, decisões e resultados. Não precisa ser
processo executável nem workflow de uma tecnologia.

### Boundary

Limite de responsabilidade, contexto ou integração. Não pressupõe microserviço,
processo, pacote, plugin ou divisão de código.

### Decision

Escolha humana com contexto, alternativas, consequência e proveniência.

### Hypothesis, Risk e Evidence

Conhecimento ainda não aceito: afirmação testável, possibilidade de impacto e
fonte/resultado que fortalece ou enfraquece uma afirmação.

### View

Projeção selecionada da mesma System Representation para uma intenção, como
arquitetura, domínio, requisitos ou teste. View não cria uma segunda fonte de
verdade.

### Export

Projeção portátil de um recorte de conhecimento para pessoa, agente ou
ferramenta. Export não substitui a representação de origem.

## Invariantes conceituais candidatos

1. Elementos e relações relevantes precisam de significado explícito.
2. Uma projeção deve poder apontar para a informação que a originou.
3. Decisões, hipóteses, riscos e evidências não podem ser confundidos.
4. Views podem reorganizar ou filtrar conhecimento, mas não duplicar autoridade.
5. Exports não se tornam a fonte de verdade após serem gerados.
6. O modelo precisa acomodar evolução sem assumir um paradigma de programação.
7. Pessoas mantêm autoridade sobre decisões que alteram significado ou escopo.

## Perguntas que permanecem abertas

- Qual granularidade de Element é útil para o primeiro segmento?
- Quais Relationship precisam de tipos e quais podem começar como significado
  livre estruturado?
- Como representar proveniência e evolução sem criar burocracia?
- Quais invariantes são universais e quais pertencem a plugin ou framework?
- Como versionar, persistir e compatibilizar mudanças?
- Quando Domain, Module, Component, Behavior e Constraint devem ser conceitos
  próprios em vez de especializações?

## Critério para promoção

Um futuro `SYSTEM_MODEL.md` só pode existir depois que exemplos de sistemas,
pesquisa com usuários, experimentos de contexto e uma decisão humana definirem
sua autoridade, escopo, compatibilidade e relação com persistência e plugins.
