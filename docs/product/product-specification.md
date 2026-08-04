# Especificação concisa de produto

## Status

Discovery. Este documento consolida uma direção de produto para discussão e
validação; não é uma especificação de implementação nem uma decisão de
arquitetura.

## Problema a validar

Em projetos de software, requisitos, decisões, diagramas e regras de domínio
costumam se separar do código e perder atualidade. Pessoas e agentes precisam
reconstruir contexto em arquivos dispersos, o que pode aumentar retrabalho,
inconsistência e tempo de revisão.

Ainda não sabemos para quais segmentos esse problema é frequente, caro e
percebido. A formulação acima é uma hipótese de problema.

## Hipótese de produto

Desenvolvedores podem pensar e evoluir sistemas com mais qualidade quando
constroem uma **System Representation** antes da implementação e usam suas
projeções como contexto para pessoas e agentes.

`System Representation` é termo provisório. A pesquisa de terminologia vive em
[`../discovery/system-representation-concept.md`](../discovery/system-representation-concept.md).

## Experiência norteadora candidata

```text
Criar projeto
→ representar um sistema novo
→ explicitar domínios, comportamentos e relações
→ revisar lacunas e restrições
→ gerar contexto estruturado para uma tarefa de agente
→ revisar a saída sem perder a representação
```

Essa jornada não afirma que geração de código, sincronização ou IA pertencem à
primeira POC. Ela fornece um cenário contra o qual a utilidade da representação
deve ser avaliada.

## Usuários e necessidades a investigar

Público, frequência e disposição de uso ainda são desconhecidos. A pesquisa
deve distinguir pelo menos:

- desenvolvedores individuais que iniciam sistemas novos;
- tech leads e arquitetos que precisam comunicar decisões;
- equipes que usam agentes de IA em mudanças com regras e dependências.

Cada segmento pode valorizar modelagem, visualização, contexto de IA ou
rastreabilidade de forma diferente. Não existe persona aceita ainda.

## Resultado de valor esperado

Uma pessoa deve conseguir criar uma representação que:

- torna responsabilidades, regras, relações e decisões discutíveis;
- revela lacunas antes da implementação;
- produz contexto que outra pessoa ou um agente consegue usar sem reconstruir
  toda a arquitetura;
- permanece independente de uma única visualização ou saída de código.

## Requisitos candidatos de produto

### Núcleo de aprendizagem

- criar e abrir um projeto local;
- organizar conceitos do sistema em uma representação estruturada;
- visualizar e editar relações relevantes;
- inspecionar propriedades e restrições;
- identificar inconsistências ou informações ausentes;
- exportar uma projeção de contexto para avaliação.

### Restrições de experiência

- o usuário decide a profundidade da representação;
- elementos visuais precisam ter semântica, não ser desenho livre;
- a ferramenta deve explicar o que ainda é hipótese, decisão ou lacuna;
- o fluxo não pode exigir conhecimento de UML nem um paradigma de programação
  específico.

## Não-objetivos atuais

Não são compromissos de POC ou MVP inicial:

- substituir IDE, Git, GitHub, CI/CD, package manager, cloud ou no-code;
- importar e reconstruir automaticamente projetos existentes;
- gerar aplicações completas;
- sincronizar código e representação de forma bidirecional;
- oferecer colaboração em tempo real, marketplace ou agentes especializados.

## Critérios de avanço

A proposta deve demonstrar evidência de que:

1. um segmento reconhece o problema em episódios recentes;
2. a criação da representação gera perguntas ou decisões úteis antes do código;
3. o custo de produzir e manter a representação é aceitável;
4. uma projeção estruturada melhora contexto para uma tarefa comparável;
5. o vocabulário inicial não obriga o usuário a modelar detalhes irrelevantes.

Os experimentos correspondentes vivem em
[`../discovery/validation-plan.md`](../discovery/validation-plan.md).
