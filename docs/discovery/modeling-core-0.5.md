# Core de modelagem 0.5 (candidato)

**Status:** candidato — diálogo com product owner + vocabulário já existente no repo.  
**Não é:** schema canônico, JSON Schema fechado, UML, nem decisão de stack.

Visão: [`../product/vision-0.5.md`](../product/vision-0.5.md).  
Vocabulário anterior: [`system-model-candidate.md`](system-model-candidate.md).

## Ideia central

Tudo é **orientado a Component**: peça completa (estado, comportamento, atributos,
relações…) que o usuário modela com a profundidade que quiser. O grafo semântico
em JSON é a persistência; diagramas/código/agente são projeções.

```text
Project          ← também pode ser pensado como Component de topo (aberto)
  └── Slice      ← Component role: slice  (pacote; rules de fatia)
        └── Scope ← Component role: scope (pacote; JSON/pasta; rules de escopo)
              └── Component + role (miolo, relationship, tunnel, edge, …)
```

**[hipótese PO]** Slice e Scope **não** são só pastas/índices: são **Components
de role mais alta** (pacotes). Como qualquer Component, podem ter estado,
comportamento, attrs e **Rules** — inclusive regras de negócio em nível de
fatia/escopo (não só no miolo). Hierarquia = composição de Components.

## Vocabulário mínimo candidato

| Conceito | Em português | Para quê |
|----------|--------------|----------|
| **Project** | Projeto | Sistema como um todo (pacote raiz; detalhe de role ainda aberto) |
| **Slice** | Fatia | `role: slice` — pacote/Component; agrupa Scopes; rules no nível da fatia |
| **Scope** | Escopo | `role: scope` — pacote/Component; conjunto de Components filhos; unidade JSON |
| **Component** | Componente | Unidade do modelo — **tudo** é Component (incl. slice/scope) |
| **role** | Papel | slice, scope, relationship, tunnel, edge, miolo, **import/lib** (candidato)… |
| **role profile** | Perfil do papel | Attrs/comportamentos/possibilidades por role (+ LanguageExtension) |
| **Rule** | Regra | **Campo/bloco dentro do Component** (não Component separado) — políticas/invariantes que a engine usa ao **compilar** o JSON → contexto/implementação do agente |

Roles já debatidas (lista aberta):

| role | Função |
|------|--------|
| `slice` / `scope` | Pacotes de nível alto; contêm outros Components; rules de projeto/fatia/escopo |
| (miolo / domain / …) | Conteúdo modelado pelo usuário |
| `relationship` | Ligação reificada entre Components |
| `tunnel` / `edge` | Ponte entre scopes e pontas |
| `import` | Lib externa — pendurada no pacote; UX de importação; depends via relationship |
| `config` | Preferência atual: **bloco no pacote Slice**, não role solto no grafo (por enquanto) |

### Imports de libs (hipótese PO)

```text
[Component do app] ──relationship (depends)──→ [Component role: import]
                                                      ↑
                                              lib X @ versão
                                              (caixa preta ou superfície usada)
```

- **Modelo:** `role: import` + relationships de dependência entre Components.
- **UX:** não parece “mais um nó genérico” — é fluxo/objeto de **importação**.
- **Semântica:** deixa explícito *por que* a lib existe no modelo (“preciso dela
  para este Component / esta superfície”).
- **Onde vive:** import **sempre pendurado no Scope/Slice** (pacote) — facilita
  produzir; relationships ligam quais Components **usam** aquela import.
- **Futuro (benefício candidato):** catálogo + autocomplete por LanguageExtension —
  Components pré-prontos da lib, menos boilerplate; ainda **não** é compromisso
  de fase.

### Config / toolchain por Slice (hipótese PO)

Cada Slice pode ter **stack e configs diferentes** (ex.: FE com Vite/Turbopack;
BE Spring + Gradle; tools de teste por fatia).

**Direção (PO):** config como **bloco no pacote Slice** (não vários Components
`config` soltos no começo) — mais fácil de produzir. O bloco declara toolchain
(build, test, bundler, runtime/DI de framework, etc.); LanguageExtension
interpreta.

Beans/wiring finos (ex.: cada bean Spring) **não** precisam entrar nesse bloco
inicial — podem ser Components de miolo + relationships depois, se fizer falta.

**Ainda aberto:** formato do bloco; o que é obrigatório vs opcional; overlap com
imports do pacote.

### O que evitamos de propósito

- Congelar Class/Interface/Inheritance no núcleo → LanguageExtension / OOP.
- Desenho sem semântica.
- Tratar Slice/Scope como pasta burra sem semântica/rules.
- Formulário único de attrs para todos os roles.
- Esquecer **imports de libs** na modelagem (ainda aberto; ver Q-CORE-006).

## Universal vs por linguagem

**[hipótese]** Duas camadas:

**Rules (PO):** vivem **dentro** do Component (campo/bloco), inclusive em
Slice/Scope. A engine consome na hora de **compilar** o grafo/JSON para o
agente implementar — não são nós `role: rule` no grafo (por enquanto).

**Ainda aberto:** Behavior e Decision — mesmo padrão (bloco interno) ou outro?

**[risco]** Universal vago demais = inútil; extensão demais = N produtos. A linha só fecha com exemplos reais (RQ-005 / G-003).

## Grafo e JSON (direção candidata — diálogo + pesquisa)

**Tese do PO:** JSON + grafos (incluindo grafos sobre grafos / escopos).  
**Status:** hipótese reforçada por desk research — **ainda não** schema oficial.

### DSL textual custom vs JSON?

| Caminho | Prós | Contras |
|---------|------|---------|
| **DSL textual própria** | Expressiva; “cheiro” de linguagem | Parser, tooling, curva; histórico MDD pesado; agentes ergam sintaxe |
| **Markdown solto (SDD típico)** | Fácil de escrever | Difícil validar; drift; review verboso (Fowler sobre SDD) |
| **JSON + schema (recomendado)** | Validável; diffável; LLMs lidam bem; git-friendly; UI edita sem o humano “escrever JSON” | Verbose na mão; precisa de IDs estáveis e disciplina de grafo |

**Recomendação conjunta (hipótese):**

1. **Verdade em disco = JSON** (ou conjunto de JSONs) descrevendo um **property graph**: nós, arestas tipadas, atributos.
2. A “DSL” de verdade é o **vocabulário + JSON Schema** (o que pode existir), não uma sintaxe nova tipo `.lm`.
3. Humanos modelam pela **UI** (e talvez atalhos); JSON é o que a engine, o git e o agente consomem.
4. **Grafos sobre grafos** = `Scope` como recorte do mesmo grafo flat (filtrar por
   `scopeId` / nó-contêiner) — não árvore JSON aninhada no começo.
5. **JSON-LD** (padrão W3C de grafo em JSON) fica como **candidato futuro** se precisarmos de IDs globais/interop pesada — não obrigatório no começo (pode ser barulho demais).

Pesquisa que sustenta JSON/grafo como artefato: orquestração agentic declarativa em JSON/YAML; projetos que tratam programa como grafo semântico em JSON-LD; GraphAI e similares. Contraponto: MDD clássico com DSL/UML sofreu overhead — LLM ajuda a gerar, mas **estrutura validável** ainda vence prosa solta.

### Forma candidata (conceitual — não schema)

**Default candidato (eficiência):** property graph **flat**.

```text
Project
  nodes[]: { id, kind, scopeId?, attrs… }   // Element, Rule, Decision, Scope…
  edges[]: { id, type, from, to, attrs… }
  // subgrafo = filtro por Scope, não nesting profundo
```

**Adiado:** árvore JSON aninhada por escopo — só revisitar com evidência de dor.

**Default candidato (PO):**

- **JSON por Scope** (e Slice como pacote Component — JSON próprio candidato);
- layout **espelhando pastas do código**;
- **Slice** / **Scope** = Components pacote (`role` alta), com Rules de nível;
- modelagem por scopes, parte a parte.

### Pontes entre Scopes: Tunnel + Edge

**Problema:** fatias isoladas demais quebram o sistema; precisa de ponte explícita.

**[hipótese PO — refinada]**

```text
Scope A                              Scope B
  Components…                          Components…
  [edge] ←─ relationship ─→ [tunnel] ←─ relationship ─→ [edge]
              (também Components)
```

Tudo na figura é **Component** com role. O Tunnel referencia/relaciona quais
Edges conecta; essas ligações são Components `role: relationship`.

**Meta-modelo (PO):** peça = Component + role; perfil do role define attrs e
possibilidades; usuário escolhe profundidade.

Qualquer schema concreto exige evidência + approval.

### Persistência local: SQLite ajuda ou é overengineering?

**[hipótese]** Separar dois papéis:

| Camada | Papel | No git? |
|--------|--------|---------|
| **JSON por Scope** | Fonte de verdade do modelo (diff, branch, review) | Sim |
| **SQLite local** | Índice/cache derivado (busca, travessia, FTS, montar contexto pro agente, checagens de drift) | Não (rebuildável, gitignore) |

Padrão comum em apps local-first / índices pra agentes: arquivos = verdade;
SQLite = cache descartável.

**Onde SQLite ajuda de verdade**

- consultar “o que depende de X?” sem varrer todos os JSONs;
- busca textual no modelo;
- montar recorte rápido de contexto pro agente;
- transações na **sessão de trabalho** (UI), sem brigar com merge de `.db`.

**Onde seria overengineering**

- SQLite como **única** fonte no repo (binário = merge infernal, branches doem);
- dual-write confuso (editar SQLite e JSON como se ambos mandassem);
- exigir SQLite na **primeira prova** de vocabulário (dá pra validar schema só com JSON + grafo em memória).

**Recomendação:** na visão do produto, **sim ao SQLite como motor local de
consulta**; na ordem de construção, **JSON-first**, SQLite quando a query/drift
doer sem ele — não no dia zero do experimento de conceitos.

Qualquer schema concreto exige evidência + approval.

## Como o core serve o agente

A engine **compila** o grafo/JSON (Components + roles + **Rules** nos blocos +
imports/config do pacote + LanguageExtension) num pacote de contexto /
instruções para o agente implementar. Forma exata do pacote compilado continua
aberta.

## Perguntas do core ainda abertas

Ver [`open-questions-vision-0.5.md`](open-questions-vision-0.5.md) itens Q-CORE-*.

## Critério para promover a canônico

Só após: exemplos em ≥2 paradigmas/linguagens, pesquisa RQ-005, e decisão humana explícita. Até lá, este arquivo e `system-model-candidate.md` convivem como candidatos.
