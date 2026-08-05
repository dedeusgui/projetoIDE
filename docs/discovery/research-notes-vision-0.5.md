# Notas de pesquisa — visão 0.5

**Status:** evidência de desk research (não substitui entrevistas com usuários).  
**Data:** 2026-08-04.

## Tese sob teste

> Modelar o sistema com clareza; o agente implementa a partir desse modelo vivo. Código na mão é apoio, não o centro.

## O que a pesquisa web sustenta

### [validado-em-pesquisa] Spec / modelo como contrato para agentes é tendência real

Entre 2025–2026, “Spec-Driven Development” (SDD) descreve o mesmo movimento: vibe-coding/chat solto gera intent drift e context decay; spec estruturada vira o prompt/contrato do agente.

Fontes: [Augment — SDD](https://www.augmentcode.com/guides/what-is-spec-driven-development), [DEV — SDD 2026](https://dev.to/krlz/spec-driven-development-in-2026-what-is-the-tooling-and-how-teams-actually-use-it-2fk2), [BCMS — SDD](https://thebcms.com/blog/spec-driven-development).

**Implicação:** a visão “substituir IDE-chat por modelagem + agente” **não é exótica**; o mercado já nomeia o problema.

### [validado-em-pesquisa] Drift modelo↔código é o risco central

Três rigorosidades recorrentes:

1. **Spec-first** — spec gera, depois o código pode driftar.
2. **Spec-anchored** — spec e código evoluem juntos; gates/testes detectam desalinho (ponto pragmático citado com frequência).
3. **Spec-as-source** — humano só edita a spec; código regenerado (alto trust; ainda aspiracional em geral).

Fontes: [arXiv 2602.00180](https://arxiv.org/html/2602.00180v1), [arXiv Spec Growth Engine](https://arxiv.org/html/2606.27045).

**Implicação:** as perguntas do product owner (revisa? modela de novo? código muda e modelo não?) **não são detalhe** — são o produto. A 0.5 deve listá-las como abertas, não fingir sync mágico.

### [validado-em-pesquisa] Contexto explícito (decisões/regras) melhora agentes

ADRs e decision records próximos do código são citados como memória que agentes precisam e o código sozinho não carrega.

Fontes: [Rick Pollick — ADR comeback](https://rickpollick.com/blog/adr-comeback-anchoring-agentic-engineering-teams), [Nexapp — ADRs](https://www.nexapp.ca/en/blog/architecture-decision-records-adr).

**Implicação:** Decision / Rule / Responsibility no modelo candidato alinhados com prática externa.

## O que a pesquisa desafia / limita

### [hipótese sob risco] “Spec-as-source” total (nunca editar código)

Ferramentas e papers apontam que edição manual e regeneração total são tensas; MDA histórico sofreu com não-determinismo. Editor de arquivos no app (como apoio) **bate** com o mundo real — mas obriga política de autoridade (quem manda quando diverge).

### [hipótese de produto — PO] Modelo forte + reconciliação a partir do código

Product owner propõe: modelo como fonte forte + auto-update/botão quando o código muda + feedback de drift + customização por custo de máquina. Isso é mais ambicioso que spec-anchored clássico (só detectar) e mais permissivo que Tessl-style (não editar código).

**Contraponto da pesquisa:** sync semântica código→modelo é o ponto mais difícil (não-determinismo, perda de intenção). Caminho prudente: detectar barato primeiro; propor atualização; auto-aplicar só o que for mecânico/seguro; nunca silenciar Decisions/Rules sem confirmação — a validar com o PO (Q-LOOP-002a/b/c).

### [validado-em-pesquisa] JSON/YAML declarativo + grafo é caminho comum (não DSL custom)

Agentes e engines modernas descrevem workflows/sistemas como grafo em JSON/YAML validável; há experimentos de “programa = grafo semântico” em JSON-LD. Markdown-spec SDD é popular, mas sofre review verboso e pouca validação mecânica (Fowler). MDD com DSL/UML histórica: overhead alto.

**Implicação para o PO:** tese “JSON + grafos (sobre grafos)” **se confirma como direção sensata**; “criar DSL textual própria” **não** é o melhor primeiro passo — o schema/vocabulário *é* a DSL.

Desk research reforça o valor de spec estruturada; **não** prova um grafo/JSON universal multi-linguagem. Isso continua gap G-003 / RQ-005 no repo.

### [aberto] Segmento e disposição de modelar

Nada na web substitui RQ-001/RQ-002/RQ-003 do [`research-backlog.md`](research-backlog.md). Tendência de mercado ≠ usuário pagando o custo de modelar.

## Cruzamento com o repo

| Repo dizia | Pesquisa | Ajuste na 0.5 |
|------------|----------|---------------|
| Norte = exportar contexto | SDD aponta implementação a partir de spec | Visão promove modelar → implementar; export pode ser meio |
| Agentes/geração “fora do MVP” | Agente é o valor anunciado da visão | Separar **visão** de **fase de entrega**; não esconder a visão |
| Sync bidirecional “fora” | Drift é problema #1 | Manter sync como **aberto**, não como “não pensamos” |
| Telas/canvas cedo | Sem prova de UX | Continuar prematuro até core + segmento |

## Conclusão da desk research

- A **direção de produto** (modelo vivo → agente implementa; chat-IDE insuficiente) tem respaldo externo.
- O **modo de autoridade** inclina para “modelo forte + reconciliação customizável”; o **como** (propor vs auto, o que é sagrado) ainda decide se isso é viável.
- O **custo de modelar** e o segmento (RQ P0) ainda decidem se o produto faz sentido no mercado.
- Próxima evidência humana: entrevistas (EXP-001) + depois teste de modelagem (EXP-002).
