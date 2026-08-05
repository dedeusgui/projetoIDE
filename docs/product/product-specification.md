# Especificação concisa de produto

## Status

Discovery. Este documento consolida uma direção de produto para discussão e
validação; não é uma especificação de implementação nem uma decisão de
arquitetura.

**Visão 0.5 (norte atual):** [`vision-0.5.md`](vision-0.5.md). Em caso de
tensão entre este arquivo e a visão 0.5, a visão prevalece como intenção de
produto; este arquivo descreve hipótese, jornada candidata e limites de fase.

## Problema a validar

Em projetos de software, requisitos, decisões, diagramas e regras de domínio
costumam se separar do código e perder atualidade. Pessoas e agentes precisam
reconstruir contexto em arquivos dispersos, o que pode aumentar retrabalho,
inconsistência e tempo de revisão. O fluxo “IDE = chat solto” agrava intent
drift quando a implementação é pedida sem modelo explícito.

Ainda não sabemos para quais segmentos esse problema é frequente, caro e
percebido. A formulação acima é uma hipótese de problema.

## Hipótese de produto

Desenvolvedores produzem software com mais qualidade quando **modelam** o
sistema numa representação viva e usam essa representação para o **agente
implementar** (e para humanos revisarem). Código na mão é apoio, não o centro.

`System Representation` é termo provisório. A pesquisa de terminologia vive em
[`../discovery/system-representation-concept.md`](../discovery/system-representation-concept.md).
Core candidato: [`../discovery/modeling-core-0.5.md`](../discovery/modeling-core-0.5.md).

## Experiência norteadora candidata

```text
Criar projeto
→ representar um sistema novo
→ explicitar domínios, comportamentos, relações e regras
→ revisar lacunas e restrições
→ pedir implementação ao agente a partir da representação
→ revisar saída (e, em aberto, reconciliar modelo ↔ código)
```

**Fase de entrega ≠ visão.** A primeira POC pode validar só a representação e
um pacote de contexto, sem integração profunda de agente. Isso não remove o
agente-implementa da visão de produto — só adia escopo até haver evidência.
Ver abertos em
[`../discovery/open-questions-vision-0.5.md`](../discovery/open-questions-vision-0.5.md).

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
- permite ao agente (na visão) implementar a partir desse conhecimento sem
  reconstruir a arquitetura via chat solto;
- permanece independente de uma única visualização ou arquivo de código.

## Requisitos candidatos de produto

### Núcleo de aprendizagem

- criar e abrir um projeto local;
- organizar conceitos do sistema em uma representação estruturada (core);
- relacionar elementos com semântica explícita;
- registrar regras, comportamentos e decisões;
- identificar inconsistências ou informações ausentes;
- projetar contexto / caminho para implementação assistida (forma aberta).

### Restrições de experiência

- o usuário decide a profundidade da representação;
- elementos visuais precisam ter semântica, não ser desenho livre;
- a ferramenta deve explicar o que ainda é hipótese, decisão ou lacuna;
- o fluxo não pode exigir conhecimento de UML nem um paradigma de programação
  específico.

## Não-objetivos de fase inicial (não confundir com a visão)

Não são compromissos da **primeira POC/MVP** (fases ainda candidatas):

- substituir por completo IDE, GitHub, CI/CD, package manager ou cloud;
- importar e reconstruir automaticamente projetos existentes;
- gerar aplicações completas de ponta a ponta sem revisão;
- sincronização bidirecional automática modelo ↔ código (política ainda aberta);
- colaboração multiplayer em tempo real, marketplace ou agentes especializados.

A visão 0.5 **inclui** agente implementando a partir do modelo e admite editor
de arquivos como apoio. Isso permanece hipótese de produto até pesquisa e
approval de fase — não é “fora da visão”.

## Critérios de avanço

A proposta deve demonstrar evidência de que:

1. um segmento reconhece o problema em episódios recentes;
2. a criação da representação gera perguntas ou decisões úteis antes do código;
3. o custo de produzir e manter a representação é aceitável;
4. uma projeção estruturada melhora contexto para uma tarefa comparável;
5. o vocabulário inicial não obriga o usuário a modelar detalhes irrelevantes.

Os experimentos correspondentes vivem em
[`../discovery/validation-plan.md`](../discovery/validation-plan.md).
