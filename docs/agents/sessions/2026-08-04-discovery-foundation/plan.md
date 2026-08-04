# Plano — 2026-08-04-discovery-foundation

## Identificação

- Revisão: `1`
- Owner: `bootstrap-orchestrator`
- Baseline:
  - [`brief.md`](brief.md)
  - [`brainstorming técnico e de produto`](../../../discovery/inputs/2026-08-04-product-and-technical-brainstorm.md)
  - [`product-context.md`](../../../product/product-context.md)
- Perfil de verificação: links Markdown, integridade YAML, classificação de
  status, escopo de MVP e simulação de jornada candidata.

## Tarefas

### D-001 — Preservar fonte e rastreabilidade

- Tags: `[lm:documentation]`
- Owner: `documentation-delivery`
- Saída: input preservado e matriz de rastreabilidade no próprio artefato.
- Allowlist: `docs/discovery/inputs/`, `docs/agents/sessions/2026-08-04-discovery-foundation/`.

### D-002 — Especificar produto e fases

- Tags: `[lm:product]`
- Owner: `documentation-delivery`
- Saída: especificação de produto, mapa de capabilities e backlog por fases.
- Allowlist: `docs/product/`, `docs/discovery/product-backlog.md`.

### D-003 — Mapear experiência e fluxos

- Tags: `[lm:product]`, `[lm:modeling]`
- Owner: `documentation-delivery`
- Saída: jornadas, telas candidatas e fluxos conceituais com estágio explícito.
- Allowlist: `docs/product/experience-map.md`, `docs/discovery/technical-context.md`.

### D-004 — Registrar direção técnica e gaps

- Tags: `[lm:architecture]`
- Owner: `documentation-delivery`
- Saída: dossiê técnico proposto, fronteiras e registro de lacunas.
- Allowlist: `docs/discovery/technical-context.md`, `docs/discovery/gap-register.md`.

### D-005 — Definir conceitos candidatos

- Tags: `[lm:modeling]`
- Owner: `documentation-delivery`
- Saída: pesquisa de nomenclatura e modelo conceitual não canônico.
- Allowlist: `docs/discovery/system-representation-concept.md`, `docs/discovery/system-model-candidate.md`.

### D-006 — Atualizar contexto

- Tags: `[lm:documentation]`
- Owner: `documentation-delivery`
- Saída: índices, backlog e validação atualizados.
- Allowlist: `README.md`, `docs/product/product-context.md`, `docs/discovery/`,
  `docs/agents/sessions/2026-08-04-discovery-foundation/`.

### D-007 — Revisar pacote documental

- Tags: `[lm:qa]`
- Owner: `documentation-reviewer`
- Saída: `reviews/review.md` com eixos de aderência e qualidade.
- Allowlist: `docs/agents/sessions/2026-08-04-discovery-foundation/reviews/`.

### D-008 — Concluir sessão

- Tags: `[lm:documentation]`
- Owner: `documentation-concluder`
- Saída: `conclusion.md` e proposta de estado final.
- Allowlist: `docs/agents/sessions/2026-08-04-discovery-foundation/`.

## Paralelismo

As tarefas são sequenciais nesta sessão. Todas dependem da classificação e
linguagem estabelecidas por D-001, e vários artefatos cruzam o mesmo contexto de
produto.

## Critérios de saída

- [ ] Todo item do brainstorming tem destino, status e fonte.
- [ ] Nenhuma tecnologia ou capacidade futura é registrada como decisão aceita.
- [ ] Fluxos e telas trazem estágio e hipótese de validação.
- [ ] O modelo conceitual não contém schema, API, persistência ou taxonomia fixa.
- [ ] Links, YAML e consistência de sessão foram validados.

## Handoff

- Próximo papel: `Challenger`.
- Condição de avanço: revisão adversarial concluída sem bloqueio.
