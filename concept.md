# SDM Concept

**SDM (Spec-Driven Methodology)** — a methodology for treating methodological artifacts (ontologies, profiles, coverage) as specifications: they are written once, verified by machine, and everything derived (exports, reports) is generated.

## Agent-first

**Agent-first: the AI agent does the work, humans keep control.**

Competency owners (HR, recruiters, methodologists, analysts, domain experts — in university, bootcamp, and onboarding contexts) formulate intent and review. The AI agent with a model calls CLI/MCP (`--json`). SDM is the canonical in YAML + Zod (files in git) and a rule framework — not manual CRUD, not a hidden methodology database.

## Two views of the methodology

SDM answers two different questions, and the two answers must not be mixed:

| View | Question | Shape |
|---|---|---|
| **Layers (artifacts)** | What is the methodology made of? (static) | Specification → Computation → Presentation |
| **Lifecycle (usage)** | How is it executed end to end? (dynamic) | Human Intent → Agent + LLM → CLI / MCP / Skills → SDM → Specs YAML |

The layers describe the *substance* of the methodology; the lifecycle describes the *scenario* in which a person gets a result.

## Layers (artifacts, static)

| Layer | What | How it changes |
|---|---|---|
| **Specification** | Ontology + profile + gap definition | Rarely |
| **Computation** | Coverage calculation under a fixed measure | Iteratively |
| **Presentation** | Export (MCP / Obsidian / web / CLI / documents) | Fully open |

### What belongs to Specification

- **Ontology** — a graph of nodes of any kind (`skill`, `concept`, `topic`, `question`, `term`, `talk`, `course`, `product`, …) and their relations (`depends_on`, `related_to`). Content (questions, terms, learning materials) is **not a separate layer**: it is nodes of the ontology with their own `kind`. The ontology is written once and is the single source of truth.
- **Profile** — what we select from the ontology and up to which threshold (which nodes, at which depth, with which weight).
- **Gap definition** — the fixed measure by which coverage is computed.

### What belongs to Computation

- **Coverage** — what is missing: the set of gap nodes under the fixed definition. Identical across all implementations given the same ontology and profile.

### What belongs to Presentation

- **Export** — where the result goes (test packs, learning courses, interview kits, matrices, Mermaid graphs, Confluence pages, MCP, CLI, web). Export is delivery mechanics: like "save / print / display". It is fully open and replaceable; it is not a stage of the artifact chain.

The split is the point: the specification is stable and reviewable; computation is mechanical and repeatable; presentation is fully open and replaceable.

## Lifecycle (usage, dynamic)

> **Human Intent → Agent + LLM → CLI / MCP / Skills → SDM → Specs YAML**

1. **Human Intent** — a person states what they need in natural language ("foundation for a Java Middle backend profile").
2. **Agent + LLM** — the agent clarifies, plans, confirms, then executes. No CLI flags, no YAML by hand for the human.
3. **CLI / MCP / Skills** — the agent's hands: portable skills (`intent-loop`, `close-coverage`, …) and MCP/CLI tools call SDM.
4. **SDM** — the rule framework: schema, operations, coverage, quality. The agent stays within the frame and cannot violate invariants.
5. **Specs YAML** — the canonical artifacts in git: ontology, profiles, coverage results. Reviewable, diffable, versioned.

No matter who performs the steps (a human or an agent), the artifact chain is the same: the layers hold, the lifecycle runs.

## Invariants (≤5)

1. Given the same ontology and profile, the set of gap nodes is identical across any implementation. The gap definition is fixed by the methodology — implementations do not choose it.

## What SDM is not

- Not SDD (that is about code)
- Not a tool / product — CLI, MCP, plugins are implementations, not the methodology
- Not a storage format (YAML is not required)
- Not an LMS, not a testing platform
- The methodology defines only coverage invariants; content quality judges and conformance tests are outside SDM

## Repository and packages

- **GitHub org:** spec-driven-methodology
- **npm scope:** @spec-driven-methodology
- **Implementation:** `sdm` (core + cli + mcp), binary `sdm`
- **Methodology:** this repository

## Soundness criterion

A person without SDM context reads the concept and explains the methodology to someone else without asking to "show the code" — so the concept must be readable standalone.