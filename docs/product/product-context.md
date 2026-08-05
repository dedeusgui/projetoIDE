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

> Desenvolvedores produzem software de maior qualidade quando modelam o sistema
> numa representação viva e usam essa representação para o agente implementar —
> em vez de depender de chat solto na IDE.

Norte documental: [`vision-0.5.md`](vision-0.5.md).

## Hipóteses secundárias

- Desenvolvedores aceitam manter uma modelagem viva.
- Uma representação estruturada melhora de forma significativa o contexto
  enviado a LLMs e a qualidade da implementação assistida.
- A modelagem reduz retrabalho arquitetural.
- Existe uma política viável para drift modelo ↔ código (ainda aberta).
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

Caso a POC e o discovery sustentem a hipótese, o MVP poderá focar em
capacidades que sustentem a visão (modelar com clareza + caminho até o agente
implementar), por exemplo:

- criação de projetos e representação estruturada;
- navegação / edição semântica (forma de UI ainda aberta — sem telas fixadas);
- relacionamentos, regras e comportamentos;
- persistência;
- projeção de contexto e/ou pedido de implementação assistida.

Essa lista é direção de escopo, não compromisso. Detalhe de telas em
[`experience-map.md`](experience-map.md) é **prematuro** até o core e o
segmento avançarem.

## Fora do MVP inicial (fase, não visão)

Para proteger aprendizado, ficam fora do **MVP inicial** (não significam
“fora da visão de produto”):

- importação automática de projetos existentes;
- geração completa sem revisão humana;
- integração profunda com Git / CI/CD;
- sincronização bidirecional automática código-modelo;
- colaboração em tempo real;
- marketplace de plugins;
- integrações com Jira ou análise automática de legado.

Perguntas abertas (drift, branches, chat vs botão):  
[`../discovery/open-questions-vision-0.5.md`](../discovery/open-questions-vision-0.5.md).

## Restrições de decisão

Ainda não há decisão sobre stack, banco de dados, formato de arquivo, grafo,
modelo canônico, editor visual, provedor de IA, licença operacional ou
infraestrutura. Qualquer proposta nesses temas precisa ser sustentada por uma
pergunta de discovery, uma experimentação ou um ADR aprovado.

## Direções documentadas, ainda não adotadas

Dossiê de discovery (candidatos, não decisões):

- [visão 0.5](vision-0.5.md);
- [especificação de produto](product-specification.md);
- [core de modelagem 0.5](../discovery/modeling-core-0.5.md);
- [perguntas abertas](../discovery/open-questions-vision-0.5.md);
- [notas de pesquisa visão 0.5](../discovery/research-notes-vision-0.5.md);
- [capabilities candidatas](capability-map.md);
- [experiências (rascunho prematuro)](experience-map.md);
- [direção técnica proposta](../discovery/technical-context.md);
- [conceito provisório de System Representation](../discovery/system-representation-concept.md);
- [modelo conceitual candidato](../discovery/system-model-candidate.md).

Esses documentos ampliam contexto, mas não autorizam POC ou implementação.
