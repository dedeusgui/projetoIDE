# Visão de produto 0.5

**Status:** hipótese alinhada com o product owner (diálogo 2026-08-04) + desk research.  
**Não é:** POC, MVP, stack, tela ou compromisso de entrega.

Documento irmão: inventário, core, abertos e notas de pesquisa em [`../discovery/`](../discovery/).

## Em uma frase

> O app é onde o sistema é **modelado** com clareza; o **agente implementa** a partir desse modelo vivo. Código na mão é **apoio**, não o centro.

## O que é

- Ambiente para **pensar e representar** software (domínio, comportamentos, relações, regras, decisões) de forma estruturada.
- Fonte de verdade candidata: a **representação** (grafo + JSON semântico), não o chat solto.
- Fluxo de valor na visão: **modelar → pedir implementação ao agente → revisar**.
- Editor de arquivos no app (ex. estilo VS Code): ver o que o agente fez, ajustar na mão, inspecionar artefatos — **secundário**.

## O que não é

- Outra IDE cujo centro é digitar código.
- Só um wrapper de chat com IA.
- Low-code / no-code genérico.
- UML cerimonial ou gerador mágico de apps sem modelo explícito.

## Por que agora (hipótese de problema)

IDEs viraram chats: pouco contato direto com código, muito prompt solto. Isso perde arquitetura, regras e decisões. Estruturar o sistema **antes** (e manter vivo) deve melhorar o que o agente produz e o que humanos revisam.

Desk research: tendência “Spec-Driven Development” e o risco de drift spec↔código — ver [`../discovery/research-notes-vision-0.5.md`](../discovery/research-notes-vision-0.5.md).

## Core (apontador)

O coração do produto na 0.5 é a **modelagem** (conceitos, grafo/JSON, universal + extensão por linguagem), não a UI:

→ [`../discovery/modeling-core-0.5.md`](../discovery/modeling-core-0.5.md)

## Loop modelo ↔ código (hipótese de política)

**[hipótese — diálogo 2026-08-04]** Meio-termo entre “modelo é a fonte” e “código pode atualizar o modelo”:

1. O **modelo é a fonte forte de verdade** — é o que o dev deve cuidar e evoluir de propósito.
2. Se o **código mudar** (pelo app, por outro agente ou por outra ferramenta), o modelo precisa **poder se atualizar** de forma rápida e simples.
3. O usuário recebe **feedback claro** quando algo está desatualizado.
4. A reconciliação pode ser **auto-atualização** ou **ação explícita** (ex.: botão), conforme custo de CPU/memória e preferência — **customização do usuário**, app melhor *para ele*.

Isso **não** é sync bidirecional mágico já resolvido. Continua aberto: o que auto-atualiza vs o que só alerta; o que fazer quando a atualização pisaria numa decisão humana do modelo.

Detalhe e riscos: [`../discovery/open-questions-vision-0.5.md`](../discovery/open-questions-vision-0.5.md) (Q-LOOP-002).

## Temas na visão, fora do detalhe 0.5

Inventário apenas — não especificados aqui:

- Como pedir implementação (chat / botão / iterativo).
- Git nativo, testes nativos, agentes ajudando a **modelar**.
- Colaboração e branches.
- Nível exato de “tempo real” (ligado à política acima e ao hardware do usuário).

## Relação com docs anteriores

Docs que falavam só em “exportar contexto” ou empurravam agentes para “pós-MVP” descrevem **fases de entrega candidatas**, não esta visão. A visão 0.5 é o norte; fases continuam a exigir evidência e approval.

## Critério para evoluir além de 0.5

1. Product owner confirma: “é isso”.
2. Core de modelagem legível e debatido.
3. Abertos listados (não escondidos).
4. Pesquisa com usuários nos RQ P0 (problema, segmento, custo de modelar).
