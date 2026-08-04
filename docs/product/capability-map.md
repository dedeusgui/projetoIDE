# Mapa de capabilities candidato

## Como ler

Capabilities abaixo não são requisitos aceitos. Elas agrupam resultados que o
produto pode precisar para testar a hipótese principal. O estágio indica quando
vale investigar, não uma promessa de entrega.

## Discovery

### Entendimento do problema

**Resultado esperado:** identificar segmento, episódio recente, custo de
reconstruir contexto e alternativa atual.

**Depende de:** entrevistas e evidências de RQ-001/RQ-002.

### Linguagem da System Representation

**Resultado esperado:** vocabulário mínimo que expresse responsabilidade, regra,
relação, fluxo e decisão sem reduzir o sistema a diagrama.

**Depende de:** RQ-005 e exemplos de sistemas distintos.

### Fluxo de modelagem

**Resultado esperado:** entender por onde uma pessoa começa, como aprofunda a
representação e em que momento encontra valor.

**Depende de:** RQ-003/RQ-006 e observação de comportamento.

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

- integração profunda com Git e diffs de representação;
- importação e engenharia reversa de código;
- geração de código e sincronização bidirecional;
- provedores de IA, MCP e Context Builder em produção;
- plugins e SDK público;
- colaboração em tempo real, projetos remotos e marketplace;
- agentes especializados, testes e documentação automáticos.

## Regra de promoção

Uma capability só avança de estágio se tiver:

1. problema ou hipótese associados;
2. evidência de valor para um segmento;
3. risco e dependência explícitos;
4. critério de validação;
5. approval humana para abrir a próxima sessão ou POC.
