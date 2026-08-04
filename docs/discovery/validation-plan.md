# Plano de validação de hipóteses

## Regra de evidência

Um experimento não confirma uma hipótese por parecer promissor. Cada experimento
deve registrar participantes, contexto, material usado, observações,
limitações e resultado. Sinais negativos ou inconclusivos são resultados válidos
e devem orientar a próxima decisão.

Os limiares abaixo são critérios iniciais de aprendizado, não métricas de
sucesso do negócio. Eles podem ser ajustados somente antes da coleta, com motivo
registrado na sessão.

## EXP-001 — Entrevistas de problema

**Hipóteses investigadas:** o problema existe, é frequente e é caro para algum
segmento; RQ-001 e RQ-002.

**Método:** conduzir entrevistas sem demonstrar uma solução primeiro. Pedir que
a pessoa descreva uma mudança recente em que precisou reconstruir arquitetura,
domínio ou decisões e quais artefatos consultou.

**Evidência esperada:** transcrições ou notas estruturadas que separem evento,
comportamento atual, consequência, frequência e ferramenta atual.

**Sinal de apoio:** pessoas do mesmo segmento relatam episódios recentes,
concretos e consequências comparáveis, sem depender de perguntas indutivas.

**Sinal de invalidação:** relatos vagos, raros ou já bem resolvidos pelas
ferramentas atuais; ou problema forte apenas em segmentos que não aceitariam
modelagem adicional.

**Decisão desbloqueada:** escolher o primeiro segmento e formular uma hipótese
de problema mais precisa.

## EXP-002 — Teste de comportamento de modelagem

**Hipóteses investigadas:** pessoas aceitam modelar antes de implementar;
RQ-003 e RQ-006.

**Método:** pedir a participantes do segmento selecionado que descrevam e
organizem uma mudança pequena, porém com regra de negócio e relação entre
componentes. Observar quais informações registram espontaneamente, quais não
entendem e o que consideram redundante.

**Evidência esperada:** gravação ou observação, artefatos produzidos, tempo por
etapa, dúvidas e autoavaliação do valor percebido.

**Sinal de apoio:** a maioria consegue criar um artefato compreensível, aponta
lacunas úteis antes do código e relata valor que supera o esforço.

**Sinal de invalidação:** participantes tratam a atividade como duplicação sem
encontrar novas perguntas, ou só conseguem concluir com treinamento intenso.

**Decisão desbloqueada:** definir o menor fluxo de modelagem a prototipar.

## EXP-003 — Contexto estruturado para agente

**Hipóteses investigadas:** uma Spec estruturada melhora o contexto para LLMs;
RQ-004 e RQ-005.

**Método:** selecionar uma tarefa com regras e dependências verificáveis.
Executar prompts equivalentes em condições controladas: uma usando apenas
documentação/código dispersos e outra usando uma representação estruturada
derivada da mesma fonte. Avaliar respostas cegamente contra critérios definidos
antes da execução.

**Seleção e pré-registro:** antes de gerar qualquer representação estruturada,
montar uma população de pelo menos três tarefas reais ou sintéticas
documentadas que tenham no mínimo três regras verificáveis e duas dependências
explícitas. Selecionar uma delas por sorteio ou por critério de inclusão
registrado; salvar população, tarefa escolhida, justificativa, rubrica e
critérios de exclusão no artefato aprovado. Não trocar a tarefa depois de ver
respostas; se ela se tornar inviável, registrar a falha e reiniciar a
comparação com uma nova approval.

**Controles obrigatórios:** usar a mesma tarefa, modelo, versão, parâmetros,
limite de contexto e rubrica nas duas condições; registrar o material entregue
em cada prompt; executar exatamente três tentativas bem-sucedidas por condição;
alternar a ordem de avaliação; e medir separadamente o tempo de curadoria para
produzir a representação estruturada. A avaliação usa a média dos três escores
da rubrica por condição, preservando cada escore individual. Falha técnica é
registrada e a tentativa pareada é repetida até três resultados bem-sucedidos;
nenhuma resposta pode ser descartada por sua qualidade. Qualquer conteúdo
adicional que exista apenas na condição estruturada deve ser identificado como
possível fator de confusão.

**Evidência esperada:** prompts, versões de modelo, material de contexto,
respostas, rubrica, avaliação independente, número de tentativas e esforço de
curadoria.

**Sinal de apoio:** a condição estruturada reduz omissões de regra, perguntas de
esclarecimento ou correções necessárias sem aumentar material irrelevante.

**Sinal de invalidação:** a melhoria não é observável, depende de uma tarefa
artificial ou exige uma modelagem onerosa demais para ser mantida.

**Decisão desbloqueada:** continuar ou interromper a POC de modelo interno.

## EXP-004 — Cobertura semântica mínima

**Hipóteses investigadas:** existe um conjunto de conceitos pequeno e útil para
representar um sistema; RQ-005 e RQ-007.

**Método:** modelar dois ou três sistemas pequenos de domínios diferentes usando
um vocabulário candidato. Registrar conceitos ausentes, campos sem significado,
ambiguidades e adaptações necessárias.

**Evidência esperada:** modelos versionados, exemplos de perguntas respondidas
por eles e lista de lacunas por domínio.

**Sinal de apoio:** o vocabulário permite explicar regras, responsabilidades,
relações e decisões essenciais sem criar convenções específicas por sistema.

**Sinal de invalidação:** cada exemplo exige novos tipos ad hoc, perde regras
críticas ou cresce para uma linguagem difícil de aprender.

**Decisão desbloqueada:** escopo, ou não, da POC técnica.

## EXP-005 — Compreensão de terminologia e projeções

**Hipóteses investigadas:** um termo e um conjunto de projeções explicam a
proposta sem serem confundidos com UML, IDE, low-code ou gerador de código;
RQ-012 e RQ-014.

**Método:** apresentar a mesma representação em descrições, lista e visualização
candidatas, alternando os nomes `System Representation`, LSR, SKM e CSM. Pedir
que pessoas do segmento expliquem o que acreditam que o produto preserva, o que
ele não faz e que tarefa tentariam realizar primeiro.

**Evidência esperada:** respostas sem explicação prévia do termo, confusões
observadas, preferência justificada e lacunas de compreensão.

**Sinal de apoio:** participantes distinguem representação de diagrama e código,
e reconhecem que views são projeções do mesmo conhecimento.

**Sinal de invalidação:** o termo induz expectativa de UML, IDE, geração
automática ou ferramenta low-code; ou nenhuma projeção demonstra vantagem
compreensível.

**Decisão desbloqueada:** manter, revisar ou substituir o termo provisório e
selecionar a menor projeção de UX para investigar.

## EXP-006 — Requisitos de plataforma

**Hipóteses investigadas:** desktop/local-first, canvas, editor textual e
extensibilidade respondem a necessidades concretas do segmento; RQ-013, RQ-014
e RQ-015.

**Método:** depois de validar problema e fluxo de modelagem, apresentar
protótipos ou cenários de uso equivalentes e registrar requisitos de offline,
privacidade, arquivo local, desempenho, visualização e integração.

**Sinal de apoio:** necessidades observáveis tornam uma direção de plataforma
claramente mais adequada que alternativas menores.

**Sinal de invalidação:** as preferências são abstratas, sem ligação com
episódios reais, ou podem ser atendidas sem as camadas propostas.

**Decisão desbloqueada:** abrir ou não uma sessão de arquitetura para comparar
runtime, persistência, canvas e extensibilidade.

## Sequência sugerida

1. EXP-001 para confirmar segmento e problema.
2. EXP-002 para testar custo e valor de modelar.
3. EXP-003 para testar a promessa ligada a IA.
4. EXP-004 somente se os sinais anteriores justificarem uma POC de modelo.
5. EXP-005 para testar linguagem e projeções com o segmento validado.
6. EXP-006 para avaliar a menor direção técnica que atende necessidades reais.

Nenhum experimento autoriza iniciar o MVP sozinho. A passagem para POC exige
uma decisão humana registrada que explique quais hipóteses receberam evidência
suficiente e quais riscos permanecem.
