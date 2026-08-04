# Manifesto do produto

## Por que este projeto existe

Software deixou de ser limitado apenas pela capacidade de escrever código. Com
LLMs modernos, o gargalo crescente é pensar, modelar e comunicar sistemas com
precisão.

Durante décadas, código-fonte ocupou o lugar de artefato primário. Requisitos,
arquitetura, diagramas e decisões existiam como material auxiliar e, com o
tempo, se desatualizavam. Quando uma pessoa ou um agente precisa mudar o
sistema, precisa reconstruir contexto a partir de fragmentos.

Este projeto parte da hipótese de que há uma alternativa: a representação do
sistema pode ser um artefato vivo, independente da implementação.

## Nossa crença

Software não deve ser descrito pelo seu código. Código deve descrever uma
implementação.

Uma única representação viva deve permitir compreender:

- domínio, comportamentos e responsabilidades;
- arquitetura, restrições e dependências;
- relações, fluxos e decisões;
- requisitos, testes, documentação e integrações.

Pessoas e agentes devem partir do mesmo modelo, sem exigir que cada conversa
reconstrua a arquitetura do zero.

## Missão

Construir o melhor ambiente possível para pensar, desenhar e evoluir software.

Não é outra IDE, outro editor de diagramas, plataforma low-code, wrapper de IA
ou cliente de chat. É uma forma diferente de construir software: modelar antes
de implementar e manter o modelo vivo durante a evolução.

## Modelo mental

Fluxo atual:

```text
Requisitos → Documentação → Arquitetura → Código → IA tenta reconstruir o sistema
```

Fluxo pretendido:

```text
Requisitos → Modelo → Representação viva → Pessoas e IA → Implementação → Evolução
```

O modelo não morre quando o código nasce. O código é uma das saídas possíveis
do conhecimento estruturado.

## Princípios

### O modelo é a fonte de verdade

Código gerado ou escrito não substitui requisitos, decisões e relações
explicitadas no modelo.

### Humanos mantêm o controle

IA é colaboradora. Ela não substitui decisões de design, produto ou arquitetura.

### Conhecimento deve ser explícito

Conhecimento escondido vira dívida técnica. Elementos visuais, decisões e
abstrações precisam ter significado verificável.

### Flexibilidade vem antes de suposições

A plataforma deve acomodar diferentes paradigmas, linguagens, frameworks e
estilos arquiteturais; não deve codificar orientação a objetos ou um fornecedor
específico como verdade universal.

### Extensibilidade é essencial

O núcleo precisa permanecer pequeno, estável e opinativo. Linguagens,
frameworks, visualizações, provedores de IA, estratégias de modelagem,
workflows de teste e pipelines devem poder evoluir sem reescrever o núcleo.

### Simplicidade vence

Poder deve emergir da composição. Complexidade precisa demonstrar valor antes
de entrar no produto.

### Aberto por design

Pessoas usuárias devem possuir seus modelos, dados, histórico e projetos.

## Pergunta de foco

Cada proposta deve responder:

> Isso ajuda desenvolvedores a pensar melhor sobre software?

Se a resposta não for clara, a proposta não pertence ao escopo atual.
