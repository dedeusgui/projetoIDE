# Papéis do workflow

## Princípio de separação

O workflow separa formulação, crítica, execução, revisão e fechamento. Um papel
pode ser exercido por uma pessoa ou um agente, mas a mesma identidade não pode
produzir, revisar e concluir a mesma entrega.

## Orchestrator

**Responsável por:** criar brief, selecionar trilha, manter a sessão coerente,
decompor o trabalho, atribuir owners, registrar dependências e coordenar
handoffs.

**Não pode:** implementar tasks de delivery, emitir approval, aceitar a própria
proposta em review ou encerrar a sessão.

## Research/Product

**Responsável por:** pesquisar problema, público, comportamento atual, evidência
de entrevistas e hipóteses de valor.

**Não pode:** apresentar uma conclusão de pesquisa como decisão de produto sem
approval humana; escolher solução técnica como substituto de evidência.

## Modeling/Architecture

**Responsável por:** explorar linguagem de modelagem, conceitos, relações,
restrições, versões e consequências arquiteturais de uma hipótese.

**Não pode:** declarar um modelo canônico aceito sem ADR e aprovação humana;
inventar semântica para acomodar um exemplo isolado.

## Challenger

**Responsável por:** atacar premissas, escopo, critérios de sucesso, riscos,
evidências ausentes, fronteiras e reversibilidade do plano.

**Não pode:** reescrever produto, implementar solução, aprovar plano ou
substituir a decisão humana.

## Delivery

**Responsável por:** executar uma task autorizada e registrar a evidência
exigida. Em discovery, normalmente é exercido pelos papéis `Research/Product` ou
`Modeling/Architecture`.

**Não pode:** mudar objetivo, assumir aprovação implícita, editar paths fora da
allowlist ou revisar a própria entrega.

## Reviewer

**Responsável por:** avaliar independentemente aderência ao pacote aprovado e
qualidade da entrega/evidências.

**Não pode:** implementar a correção, reabrir escopo sem registrar bloqueio,
emitir approval humana ou concluir a sessão.

## Concluder

**Responsável por:** consolidar resultados, atualizar destinos de aprendizado,
declarar gates pendentes, propor o estado final e preparar a continuidade. O
`Orchestrator` persiste a transição de fase em `session.yaml`.

**Não pode:** alterar a decisão para tornar o resultado mais favorável,
implementar correções ou ocultar evidência negativa.

## Humano aprovador

**Responsável por:** decidir escopo, hipótese a perseguir, riscos aceitos,
decisões arquiteturais e transições que exigem autoridade humana.

**Não pode:** delegar aprovação para uma inferência do agente. A autorização
precisa estar no artefato de approval vinculado à revisão correta.

## Matriz de incompatibilidade

Para a mesma unidade de entrega:

- `Delivery` não pode ser `Reviewer` nem `Concluder`;
- `Reviewer` não pode ser `Concluder`;
- `Orchestrator` não pode ser `Delivery` nem `Reviewer`;
- `Challenger` não pode ser `Delivery` nem `Reviewer`;
- humano aprovador não pode ser simulado por nenhum papel de agente.

Se uma equipe pequena não tiver identidades suficientes, a sessão deve declarar
a exceção como risco e obter approval humana antes de seguir. A exceção não pode
ser invisível.
