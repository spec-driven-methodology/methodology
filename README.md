# SDM — Spec-Driven Methodology

A methodology for treating methodological artifacts (ontologies, profiles, coverage) as specifications: they are written once, verified by machine, and everything derived (exports, reports) is generated.

## Two views

| View | Question | Shape |
|---|---|---|
| **Layers (artifacts)** | What is the methodology made of? | Specification → Computation → Presentation |
| **Lifecycle (usage)** | How is it executed end to end? | Human Intent → Agent + LLM → CLI / MCP / Skills → SDM → Specs YAML |

## Layers (static)

| Layer | What | Changes |
|---|---|---|
| **Specification** | Ontology (nodes of any `kind`) + Profile (selection + threshold) + Gap definition | Rarely |
| **Computation** | Coverage — gap nodes under a fixed measure | Iteratively |
| **Presentation** | Export (MCP, CLI, web, documents — delivery mechanics) | Fully open |

Content (questions, terms, materials) is **not a separate layer** — it is nodes of the ontology with their own `kind`.

Export is **not a stage of the artifact chain** — it is delivery mechanics (save / print / display), fully replaceable.

## Lifecycle (dynamic)

> **Human Intent → Agent + LLM → CLI / MCP / Skills → SDM → Specs YAML**

The agent clarifies the intent, plans, confirms, executes within the SDM frame, and commits the result as versioned YAML specs.

## Invariant

Given the same ontology and profile, the set of gap nodes is identical across any implementation.

## Documents

- [Concept](concept.md) — full concept: two views, layers, lifecycle, what it is not
- [Why SDM?](why-sdm.md) — what SDM adds that a bare agent cannot provide
- [Glossary](glossary.md) — key terms defined
- ADR — architecture decisions (naming, scope)

## What it is not

- Not a tool / product — CLI, MCP, plugins are *implementations*, not the methodology
- Not a storage format (YAML is not required)
- Not an LMS or testing platform
- Not a content quality judge — that is outside SDM