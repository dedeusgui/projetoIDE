# System Representation: conceito e pesquisa de nomenclatura

## Status

`System Representation` é o termo provisório de trabalho. Ele não é marca,
nome oficial nem definição de schema.

## Definição provisória

Uma System Representation é um conjunto vivo, versionável e semanticamente
explícito de conhecimento sobre um sistema. Ela preserva elementos,
responsabilidades, regras, relações, fluxos, fronteiras, decisões, hipóteses,
riscos e evidências.

Diagramas, documentação, contextos de agente, testes e código podem ser
projeções dessa representação. Nenhuma projeção se torna fonte de verdade apenas
por ser mais conveniente de produzir ou visualizar.

## O que o conceito não é

- não é um diagrama isolado;
- não é sinônimo de UML;
- não é uma linguagem de programação;
- não é uma cópia de código-fonte;
- não exige geração de código;
- não determina banco, grafo, JSON, API ou interface.

## Candidatos de nome

### Living System Representation (LSR)

**Sinal desejado:** enfatiza evolução contínua e independência de código.

**Risco:** pode ser longo, abstrato e remeter a uma representação visual em vez
de uma base de conhecimento.

### System Knowledge Model (SKM)

**Sinal desejado:** enfatiza conhecimento explícito e compartilhável.

**Risco:** “model” pode trazer associação imediata com modelagem tradicional e
não evidencia que há múltiplas projeções.

### Canonical System Model (CSM)

**Sinal desejado:** enfatiza autoridade e fonte de verdade.

**Risco:** “canonical” promete uma maturidade que ainda não existe e pode
sugerir schema rígido ou centralização prematura.

### System Representation

**Sinal desejado:** é neutro quanto a paradigma, tecnologia e forma visual; abre
espaço para discutir o significado antes de fixar nome.

**Risco:** é genérico e pode não carregar sozinho a ambição de conhecimento
vivo ou fonte de verdade.

## Critérios para nome oficial

Um nome candidato deve:

1. comunicar que o produto vai além de diagramas;
2. ser compreensível por pessoas técnicas sem treinamento em uma metodologia;
3. não privilegiar orientação a objetos, uma linguagem ou fornecedor;
4. acomodar visualização, texto, regras, decisões e projeções;
5. resistir à evolução de produto sem exigir rebranding conceitual;
6. não prometer canonicidade antes de haver autoridade e invariantes definidos.

## Experimento de nomenclatura

Antes de promover um nome:

- apresentar candidatos junto de exemplos da mesma representação;
- pedir a pessoas do segmento que expliquem o que acreditam que o produto faz;
- observar associações espontâneas com UML, diagrama, IDE, low-code ou código;
- medir clareza sem explicar o termo previamente;
- registrar ambiguidades e decisão humana em sessão aprovada.

## Destino

O termo escolhido poderá ser promovido para manifesto, documentação de produto e
um futuro `SYSTEM_MODEL.md` somente depois de evidência e ADR. Até lá, use
`System Representation` nos documentos novos.
