# Contexto inicial do produto

## Visão geral

O projeto investiga a mudança de paradigma em que o código deixa de ser o centro
do desenvolvimento. LLMs conseguem produzir implementação de alta qualidade
quando recebem contexto suficiente; estruturar, validar e transmitir esse
conhecimento passa a ser o problema central.

A proposta é uma plataforma que representa sistemas em um nível de abstração
superior ao código-fonte, por meio de um modelo semântico estruturado,
versionável e útil para pessoas e agentes.

## Problema observado

Hoje, requisitos, documentação e diagramas normalmente se separam do código e
se tornam obsoletos. A arquitetura acaba concentrada na memória das pessoas que
criaram o sistema. Agentes precisam inferir responsabilidades, regras de
negócio e decisões a partir de muitos arquivos, o que reduz contexto e aumenta
inconsistências.

O problema não está comprovado para um público específico. Esta descrição é a
hipótese de problema que o discovery precisa investigar.

## Hipótese principal

> Desenvolvedores conseguem produzir software de maior qualidade quando modelam
> o sistema antes da implementação e utilizam essa modelagem como contexto para
> agentes de IA.

## Hipóteses secundárias

- Desenvolvedores aceitam manter uma modelagem viva.
- Uma representação estruturada melhora de forma significativa o contexto
  enviado a LLMs.
- A modelagem reduz retrabalho arquitetural.
- O modelo pode permanecer sincronizado com a evolução do projeto.
- O valor obtido justifica o custo de criar e manter a modelagem.

Essas são hipóteses, não promessas do produto.

## Público e proposta de valor

O público ideal e a proposta de valor ainda são desconhecidos. Não devemos
presumir que todo desenvolvedor, toda equipe ou todo tipo de sistema tenha o
mesmo problema.

O discovery deve identificar segmentos em que a perda de contexto arquitetural
é frequente, cara e percebida, além de verificar se essas pessoas aceitariam
trocar parte da escrita de código por modelagem explícita.

## Escopo de investigação

### POC técnica futura

Uma primeira POC deve validar:

- modelo interno;
- representação de sistema;
- persistência;
- exportação;
- consistência.

Não deve priorizar design refinado nem integração com agentes.

### MVP futuro

Caso a POC e o discovery sustentem a hipótese, o MVP poderá focar em:

- criação de projetos;
- explorer;
- canvas de modelagem;
- edição de propriedades;
- relacionamentos;
- persistência;
- exportação de uma Spec.

Essa lista é uma direção de escopo, não um compromisso de implementação.

## Fora do MVP inicial

Para proteger a hipótese principal, ficam fora do MVP inicial:

- importação automática de projetos existentes;
- geração completa de código;
- integração profunda com Git;
- CI/CD;
- agentes especializados;
- sincronização bidirecional código-modelo;
- colaboração em tempo real;
- marketplace de plugins;
- integrações com Jira, GitHub ou análise automática de legado.

## Restrições de decisão

Ainda não há decisão sobre stack, banco de dados, formato de arquivo, grafo,
modelo canônico, editor visual, provedor de IA, licença operacional ou
infraestrutura. Qualquer proposta nesses temas precisa ser sustentada por uma
pergunta de discovery, uma experimentação ou um ADR aprovado.

## Direções documentadas, ainda não adotadas

O brainstorming atual foi organizado como dossiê de discovery:

- [especificação de produto](product-specification.md);
- [capabilities candidatas](capability-map.md);
- [experiências e telas candidatas](experience-map.md);
- [direção técnica proposta](../discovery/technical-context.md);
- [conceito provisório de System Representation](../discovery/system-representation-concept.md);
- [modelo conceitual candidato](../discovery/system-model-candidate.md).

Esses documentos ampliam contexto para pessoas e agentes, mas não alteram as
restrições desta seção nem autorizam uma POC ou implementação.
