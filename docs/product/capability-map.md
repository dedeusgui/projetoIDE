# Mapa de capabilities candidato

## Como ler

Capabilities abaixo não são requisitos aceitos. Elas agrupam resultados que o
produto pode precisar. O estágio indica quando vale investigar, não promessa
de entrega.

**Visão 0.5:** modelar → agente implementa ([`vision-0.5.md`](vision-0.5.md)).
Capabilities de “só exportar contexto” ou de empurrar agentes só para pós-MVP
descrevem **fases candidatas**, não o limite da visão.

## Discovery

### Entendimento do problema

**Resultado esperado:** identificar segmento, episódio recente, custo de
reconstruir contexto e alternativa atual (incl. chat-IDE).

**Depende de:** entrevistas e evidências de RQ-001/RQ-002.

### Linguagem da System Representation

**Resultado esperado:** vocabulário mínimo (ver
[`../discovery/modeling-core-0.5.md`](../discovery/modeling-core-0.5.md)).

**Depende de:** RQ-005 e exemplos de sistemas distintos.

### Fluxo de modelagem

**Resultado esperado:** entender por onde uma pessoa começa, como aprofunda e
quando encontra valor — **sem fixar telas**.

**Depende de:** RQ-003/RQ-006.

### Política modelo ↔ código

**Resultado esperado:** hipótese clara de autoridade/drift (Q-LOOP-* em
[`../discovery/open-questions-vision-0.5.md`](../discovery/open-questions-vision-0.5.md)).

**Depende de:** desk research (já iniciada) + debate de produto + evidência
posterior.

## POC candidata

### Representação estruturada

**Resultado esperado:** criar, alterar e consultar um conjunto pequeno de
conceitos e relações com semântica explícita.

**Risco:** cristalizar modelo ou schema antes de exemplos suficientes.

### Persistência e reabertura

**Resultado esperado:** salvar e restaurar uma representação sem perda de
significado ou proveniência.

**Risco:** escolher armazenamento antes de conhecer requisitos de evolução.

### Exportação de contexto

**Resultado esperado:** projetar a representação em um pacote comparável de
contexto para avaliação humana ou de agente.

**Risco:** confundir melhoria causada por curadoria humana com melhoria causada
pela estrutura.

### Consistência básica

**Resultado esperado:** detectar relações, responsabilidades ou informações
ausentes que impedem uma representação de responder perguntas relevantes.

**Risco:** transformar validação em regras rígidas de UML.

## MVP candidato

### Gestão de projeto e explorer

**Resultado esperado:** criar projetos e navegar por elementos, visões e
artefatos do mesmo sistema.

### Canvas semântico

**Resultado esperado:** visualizar e editar elementos e relações com pan, zoom,
seleção e significado verificável.

### Inspector e propriedades

**Resultado esperado:** tornar intenção, responsabilidade, regra e restrição
editáveis sem espalhar informação pela interface.

### Feedback de validação

**Resultado esperado:** apontar lacunas de forma explicável e não prescritiva.

### Exportação de Spec

**Resultado esperado:** gerar uma projeção portátil para pessoas, ferramentas ou
avaliação de contexto.

## Pós-MVP ou pesquisa futura

Itens abaixo podem ser **fase tardia** e ainda assim pertencer à visão:

- integração com Git e diffs de representação;
- importação / engenharia reversa de código;
- implementação assistida por agente a partir do modelo (está na **visão 0.5**;
  o estágio de entrega é que permanece aberto);
- sincronização ou gates de drift modelo ↔ código;
- provedores de IA, MCP e Context Builder em produção;
- plugins e SDK;
- colaboração, projetos remotos e marketplace;
- agentes ajudando a modelar; testes nativos no app.

## Regra de promoção

Uma capability só avança de estágio se tiver:

1. problema ou hipótese associados;
2. evidência de valor para um segmento;
3. risco e dependência explícitos;
4. critério de validação;
5. approval humana para abrir a próxima sessão ou POC.
