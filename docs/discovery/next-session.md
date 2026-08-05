# Próxima sessão de discovery

## Contexto pós visão 0.5

A documentação de produto está em **0.5** ([visão](../product/vision-0.5.md),
[core](modeling-core-0.5.md), [abertos](open-questions-vision-0.5.md),
[pesquisa desk](research-notes-vision-0.5.md)). Isso **não** substitui
entrevistas: ainda não há segmento validado.

## Objetivo

Transformar a base 0.5 numa investigação de problema com público e método
aprovados — **ou** num debate curto de política de drift (RQ-016) se o product
owner priorizar fechar autoridade modelo↔código antes de campo.

A próxima sessão não deve iniciar pela escolha de tecnologia ou por telas.

## Decisão humana necessária

Escolher o foco da primeira investigação:

1. segmento que sente o problema ([RQ-001](research-backlog.md#rq-001--qual-segmento-sente-o-problema-com-maior-intensidade));
2. trabalho perdido caro o suficiente ([RQ-002](research-backlog.md#rq-002--qual-trabalho-perdido-queremos-reduzir));
3. aceitação de modelar antes ([RQ-003](research-backlog.md#rq-003--pessoas-modelariam-antes-de-implementar));
4. **ou** política de drift/autoridade ([RQ-016](research-backlog.md)) — desk +
   debate interno, não substitui usuários.

Recomendação: agrupar RQ-001 e RQ-002 em entrevistas; tratar RQ-016 em paralelo
só como nota de produto curta, sem travar campo.

## Pacote a preparar antes de approval

O `Orchestrator` deve criar uma nova revisão da sessão-semente com:

- brief que delimite o segmento a explorar sem afirmar que ele é o público
  definitivo;
- plano baseado no EXP-001, com roteiro de entrevista não indutivo;
- critérios que separem relatos de evento recente de preferência abstrata;
- política de registro, consentimento e anonimização das entrevistas;
- challenge focado em viés de confirmação, tamanho de amostra e interpretação;
- artefato de approval que autorize participantes, método e limites.

## Sinais para decisão

A pesquisa deve responder, com evidência:

- qual papel ou tipo de equipe vive o problema;
- em que evento recente ele ocorreu;
- o que a pessoa fez para recuperar contexto;
- quais custos ou riscos resultaram;
- quais ferramentas ou processos atuais já mitigam o problema;
- se há um padrão suficiente para justificar uma segunda rodada.

Uma preferência por “uma ferramenta com IA” não é evidência suficiente para a
hipótese de produto.

## Limites

Não iniciar POC, canvas, exportação de Spec, geração de código, integração de
LLM ou definição de modelo semântico nesta sessão. Esses itens dependem da
evidência de problema, público e custo de modelagem.

O novo [dossiê de produto e direção técnica](../product/product-specification.md)
serve como contexto para formular perguntas, não como autorização para antecipar
essas capacidades. Stack, System Representation canônica, plugins e IA
permanecem propostas até as validações correspondentes.

## Saída esperada

Uma conclusion revisada que:

- fortaleça, enfraqueça ou substitua a hipótese de problema;
- atualize RQ-001 e RQ-002 com evidências;
- indique se EXP-002 é justificado;
- registre o próximo gate humano, inclusive se a decisão for interromper ou
  redirecionar o discovery.
