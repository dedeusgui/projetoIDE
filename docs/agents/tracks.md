# Trilhas de cerimônia

## Seleção

O `Orchestrator` propõe a trilha no brief; o humano aprova a seleção junto com o
plano. Na dúvida, usar `discovery` para aprendizado de produto ou `full` para
mudança de implementação. Nenhuma trilha permite pular approval em arquivo.

## Discovery

Usada para perguntas de produto, pesquisa de usuário, experimentos de hipótese,
exploração de conceitos de modelagem e decisões ainda sem implementação.

Fluxo:

```text
Brief → Plan → Challenge → Approval → Research/Modeling → Review → Conclusion
```

Checklist:

- brief separa fatos, hipóteses, decisões, riscos e perguntas;
- plano define evidência e sinal de apoio/invalidação;
- challenge avalia vieses, amostra, escopo e custo de aprendizagem;
- approval autoriza a pergunta e o método, não uma conclusão;
- review avalia rastreabilidade e se a evidência sustenta a conclusão;
- conclusion atualiza backlog, hipóteses e aprendizados.

## Full

Reservada para uma futura mudança que atravesse mais de uma fronteira relevante,
introduza ou modifique contrato, altere modelo canônico, afete segurança,
persistência, integrações ou requeira decisão arquitetural.

Fluxo:

```text
Brief → Spec/ADR → Plan → Challenge → Approval → Delivery → Review → Conclusion
```

Checklist:

- spec ou ADR explica a mudança e suas alternativas;
- tasks têm tags de domínio, dependências e allowlists;
- plano define critérios de aceite e verificação reproduzível;
- reviewer executa eixo de aderência e eixo de qualidade;
- conclusão registra impacto no modelo, documentação e próximos gates.

## Light — proposta inativa

`light` poderá ser proposta após existir uma base de código e dados suficientes
para classificar uma alteração local e reversível. Até esse momento, ela não é
uma forma de encurtar o processo.

Sua ativação exige ADR que defina:

- limites mensuráveis de escopo;
- riscos que ainda exigem upgrade para `full`;
- testes e gates mínimos;
- condições de independência entre produção, revisão e conclusão.

## Upgrade obrigatório

Uma sessão deve migrar para `full` se surgir qualquer um destes sinais:

- mudança no problema, público, hipótese ou requisito **já aprovado** que
  altere o escopo, método, risco ou decisão da sessão;
- novo contrato, persistência, integração, dado compartilhado ou risco de
  segurança;
- alteração de modelo canônico ou regra de compatibilidade;
- mais de uma fronteira de domínio ou área de entrega;
- conflito de paths ou dependência que invalide o paralelismo planejado;
- necessidade de waiver de gate.

O upgrade incrementa a revisão, reabre challenge e exige nova approval. Uma
approval anterior não cobre escopo ampliado.

Resultados esperados de discovery — fortalecer, enfraquecer, invalidar ou
refinar uma hipótese investigada — não exigem upgrade por si só. Eles devem ser
registrados na conclusion e usados para propor a próxima sessão. O upgrade só é
necessário quando a resposta muda o trabalho autorizado em curso.
