# Approval — <sessionId>

## Identificação

- Revisão aprovada: `<n>`
- Aprovador humano: `<nome ou papel>`
- Data: `<YYYY-MM-DD>`
- Artefatos avaliados: `<brief, plan, challenge e links>`

## Decisão

`approved | rejected | approved-with-conditions`

## Escopo autorizado

<Descrever exatamente o que pode seguir para delivery.>

## ADRs e decisões de governança avaliados

- Artefato: `<link ou not-applicable>`
- Disposição: `accept | revise | reject | not-applicable`
- Justificativa: `<motivo; not-applicable exige motivo>`

Se esta for a primeira approval do repositório, este bloco deve incluir
`docs/architecture/adr/ADR-0001-governanca-de-conhecimento-e-decisoes.md` com
disposição `accept`, `revise` ou `reject`; `not-applicable` é proibido nesse
caso.

## Condições e riscos aceitos

### <COND-001> — <título>

- Tipo: `pre-delivery | post-delivery`
- Gate vinculado: `<HG-001 em session.yaml>`
- Owner da verificação: `<papel ou identidade>`
- Fase de avaliação: `<fase>`
- Estado: `pending | resolved`
- Evidência de resolução: `<link ou vazio se pending>`

Repita esta estrutura para cada condição. Toda condição deve ter ID e gate
vinculado em `session.yaml`, inclusive quando já tiver sido resolvida.

### Riscos aceitos

- <risco e motivo>

`approved-with-conditions` só permite `delivery` quando todas as condições
pré-delivery estiverem resolvidas e registradas. Gates posteriores não podem ser
tratados como resolvidos e bloqueiam `concluded` até sua resolução ou
transferência para uma sessão aprovada.

## Gates humanos pendentes

- `<HG-001>` — <resumo; detalhes e estado vivem em session.yaml>

## Limites

- Não autoriza: <itens fora do escopo>
- Exige nova approval se: <mudanças que invalidam esta revisão>

## Assinatura

<Registro explícito da pessoa responsável. Chat não substitui este artefato.>
