# Próxima sessão de discovery

## Objetivo

Transformar a sessão-semente em uma investigação de problema com público e
método explicitamente aprovados. A próxima sessão não deve iniciar pela escolha
de tecnologia ou por uma interface de modelagem.

## Decisão humana necessária

Escolher uma pergunta P0 para a primeira investigação:

1. identificar qual segmento sente o problema com maior intensidade
   ([RQ-001](research-backlog.md#rq-001--qual-segmento-sente-o-problema-com-maior-intensidade));
2. identificar qual trabalho perdido é caro o suficiente para justificar uma
   nova prática ([RQ-002](research-backlog.md#rq-002--qual-trabalho-perdido-queremos-reduzir));
3. validar se pessoas modelariam antes de implementar
   ([RQ-003](research-backlog.md#rq-003--pessoas-modelariam-antes-de-implementar)).

Recomendação inicial: agrupar RQ-001 e RQ-002 em uma única investigação de
entrevistas, porque não é possível avaliar aceitação de modelagem sem primeiro
entender um problema concreto e recorrente. Esse agrupamento só pode avançar se
o brief separar as evidências de cada pergunta e o approval autorizar ambas.

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

## Saída esperada

Uma conclusion revisada que:

- fortaleça, enfraqueça ou substitua a hipótese de problema;
- atualize RQ-001 e RQ-002 com evidências;
- indique se EXP-002 é justificado;
- registre o próximo gate humano, inclusive se a decisão for interromper ou
  redirecionar o discovery.
