# Backlog de produto por fases

## Convenções

Itens deste backlog são candidatos de aprendizagem ou entrega. Não são issues de
implementação e não recebem status de “feito” sem uma sessão, evidência e
conclusão vinculadas.

Prioridade considera impacto na hipótese principal, aprendizagem esperada, custo
de modelagem, reversibilidade, risco de escopo e dependências.

## Discovery

### PB-001 — Validar problema e segmento

**Objetivo:** descobrir quem perde contexto arquitetural, em qual situação e
com qual consequência.

**Depende de:** entrevistas e RQ-001/RQ-002.

**Gate humano:** decidir se existe um segmento suficiente para continuar.

### PB-002 — Testar custo e utilidade da representação

**Objetivo:** observar se pessoas conseguem representar um sistema novo e
encontrar lacunas úteis antes de implementar.

**Depende de:** PB-001 e RQ-003/RQ-006.

**Gate humano:** decidir se o valor percebido justifica uma POC.

### PB-003 — Avaliar contexto estruturado

**Objetivo:** comparar contexto disperso com uma representação estruturada em
tarefa de regras e dependências.

**Depende de:** PB-001, PB-002, RQ-004 e controles de experimento aprovados.

**Gate humano:** decidir se há sinal para construir uma POC de exportação.

### PB-004 — Nomear e delimitar a System Representation

**Objetivo:** avaliar o termo provisório e um vocabulário semântico mínimo.

**Depende de:** exemplos, testes de compreensão e RQ-005.

**Gate humano:** decidir se algum termo pode ser promovido a nome oficial.

## POC candidata

### PB-101 — Representação mínima e persistência

**Objetivo:** validar criação, alteração, reabertura e consistência de exemplos
pequenos.

**Depende de:** PB-002, PB-004 e decisão de avançar.

**Risco:** inventar schema, armazenamento ou grafo antes dos requisitos.

### PB-102 — Projeção de contexto

**Objetivo:** exportar uma representação como pacote de contexto comparável.

**Depende de:** PB-101 e PB-003.

**Risco:** acoplar a POC a um provedor de IA ou formato de prompt.

## MVP candidato

### PB-201 — Projeto, explorer e representação navegável

**Objetivo:** permitir criar um projeto e navegar pelo conhecimento que o
compõe.

### PB-202 — Canvas e inspector semânticos

**Objetivo:** permitir criar e refinar elementos, relações e propriedades.

### PB-203 — Validação e exportação de Spec

**Objetivo:** fornecer feedback de consistência e uma projeção portátil.

**Dependência comum:** PB-101/PB-102 e evidência de que a experiência resolve um
problema validado.

## Fora da fase inicial

Importação automática, geração completa, sincronização código-representação,
Git profundo, CI/CD, colaboração, marketplace, integração com ferramentas
externas e agentes especializados não entram como backlog de MVP antes de nova
evidência e approval.
