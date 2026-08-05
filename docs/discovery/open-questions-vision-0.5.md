# Perguntas abertas — visão 0.5

**Status:** inventário explícito. Nenhuma linha abaixo está decidida.  
**Uso:** não esconder dúvida; puxar para research/backlog quando priorizar.

Fonte de intenção: diálogo product owner + [`research-notes-vision-0.5.md`](research-notes-vision-0.5.md).

## Loop e autoridade (bloqueadores de sentido do produto)

### Q-LOOP-001 — Depois de implementar, o que acontece?

Revisa saída do agente → ajusta modelo → pede de novo? Ou ajusta código e volta ao modelo depois?

**Por que importa:** define se o produto é ciclo contínuo ou “gera e esquece”.

### Q-LOOP-002 — Quem manda quando código e modelo divergem?

**Status:** hipótese de direção (não fechada).

**Direção do product owner:** meio-termo B+C —

- modelo = **fonte forte** (o que o dev deve fazer);
- código alterado fora do modelo → modelo **se atualiza** rápido/simples (auto ou botão);
- feedback útil de “desatualizado”;
- agressividade da sync **customizável** (custo CPU/RAM / máquina do usuário).

**Ainda aberto dentro disso:**

### Q-LOOP-002a — Default de reconciliação

Quando código diverge: (1) só avisar + botão, (2) auto o seguro + confirmar o resto, (3) auto quase tudo.

**Inclinação em diálogo:** (2) faz mais sentido com “modelo forte” — ainda não fechado pelo PO.
- Q-LOOP-002b — o que nunca pode ser sobrescrito em silêncio (Decision, Rule, Hypothesis)?
- Q-LOOP-002c — atualização estrutural barata (arquivos/símbolos) vs semântica cara (IA inferindo intenção)?

**Risco:** “auto-atualizar a partir do código” sem cuidado vira engenharia reversa que **apaga** intenção humana do modelo — o oposto da visão.

**Por que importa:** sem política, o modelo vira doc morta; com sync cega, o modelo vira eco ruidoso do código.

### Q-LOOP-003 — Integração “em tempo real” com código?

Em que nível: diff ocasional, watch de arquivos, gates no save/PR, nada no início?

**Por que importa:** custo de engenharia vs promessa de “vivo”.

## Colaboração e Git

### Q-COLLAB-001 — Vários devs / várias branches

A representação vive no repo? Por branch? Merge de grafo é tratável? Conflito de modelo vs conflito de código?

### Q-COLLAB-002 — Git nativo no app

Só visualização da evolução, ou também operações (commit, branch, PR)?

## Como o agente entra

### Q-AGENT-001 — Chat ao lado vs botão “implementar” vs fluxo iterativo

Qual combinação; o que é default na visão (ainda sem UI).

### Q-AGENT-002 — Agente ajuda a modelar (não só implementar)?

Escopo e risco de o modelo ser escrito pela IA sem revisão humana.

## Core de modelagem

### Q-CORE-001 — Granularidade de Element / Component

Quando algo é Component vs Scope vs só atributo?

### Q-CORE-002 — Behavior sem OOP

Como expressar comportamento de forma que Java e Python entendam sem virar pseudocódigo inútil?

### Q-CORE-003 — Fronteira LanguageExtension

O que é universal obrigatório vs plugin de linguagem?

### Q-CORE-004 — Forma do JSON/grafo

**Status:** hipótese parcial fechando.

**Direção:** JSON + property graph flat (`nodes[]` + `edges[]`); Scope = recorte,
não árvore aninhada. Ver [`modeling-core-0.5.md`](modeling-core-0.5.md).

**Ainda aberto / fechado parcial:**

- Q-CORE-004a — monolítico vs por Scope? **Fechado (hipótese PO):** JSON por Scope.
- Q-CORE-004c — JSON-LD cedo ou property graph simples? (inclinação: simples primeiro)
- Q-CORE-004d — SQLite: cache local rebuildável (recomendado) vs verdade no disco (evitar)?

**Adiado com critério:** Q-CORE-004b (árvore aninhada) — só revisitar com evidência
de dor no flat.

### Q-CORE-005 — Como o dev modela / meta-modelo

**Status:** hipótese forte (PO), em evolução.

**Direção atual:**

- Tudo **Component** + **role** (+ role profile).
- Slice e Scope = Components de role alta (**pacotes**), com **Rules** de nível
  fatia/escopo (negócio / política de projeto).
- relationship / tunnel / edge = roles; ligações bem modeladas.
- JSON por Scope; pastas espelham código.

**Ainda aberto:**

- Q-CORE-005c — espelhar pastas sempre ou só com código existente?
- Q-CORE-005d — direção in/out onde mora?
- Q-CORE-005f — **Rule = bloco/campo no Component** (engine usa ao compilar JSON
  → agente). Behavior / Decision ainda abertos (mesmo padrão?).
- Q-CORE-005g — Slice: JSON de pacote + refs aos Scopes?

### Q-CORE-006 — Imports de libs na modelagem

**Status:** hipótese parcial (PO).

**Direção:**

- Sob o capô: Component `role: import`.
- UX: **componente de importação**.
- **Sempre pendurado no Scope/Slice**; relationships marcam quem depende/usa.
- Futuro: catálogo + autocomplete por linguagem.

**Ainda aberto:** 006b (superfície vs nome+versão); 006c (catálogo = depois).

### Q-CORE-007 — Config e toolchain por Slice

**Status:** aberto → hipótese inicial (PO).

Slices diferentes = stacks diferentes (Vite/Turbopack vs Spring/Gradle; runners
de teste; beans/config de framework). Precisa viver no modelo para o agente
implementar/rodar no contexto certo.

**Direção (PO):** **bloco de config no pacote Slice** (facilita produzir) —
toolchain (build, test, bundler, runtime…). Beans/wiring finos = depois, se
preciso, como Components — não no bloco inicial.

**Ainda aberto:** 007b (quando bean vira Component); 007c (obrigatório vs
opcional no bloco); formato do bloco.

**Fechado parcial (005/006):** Component+role; pacotes com Rules; import no
pacote + depends.

## Experiência e valor (já no backlog P0)

### Q-VALUE-001 — Qual segmento sente a dor? → RQ-001

### Q-VALUE-002 — Qual trabalho perdido importa? → RQ-002

### Q-VALUE-003 — Pessoas modelariam antes? → RQ-003

## Fora da 0.5 (lembrar, não especificar)

- Testes nativos no app.
- Marketplace / plugins públicos.
- Importação automática de legado.
- Colaboração multiplayer em tempo real.

## Próximo uso

Priorizar no máximo 2–3 perguntas por sessão de research. Recomendação inicial pós-0.5: **Q-VALUE-001/002** (entrevistas) em paralelo a debate interno de **Q-LOOP-002** (autoridade), porque a pesquisa externa mostrou drift como risco estrutural.
