# SDM — Spec-Driven Methodology

SDM is a **methodology-as-specs** approach to competency assessment and skills management. Instead of scattered job descriptions and one-off exams, SDM treats every competency as a *spec*: an ontology of skills, a content library, certification profiles, and a measurable coverage model — all versioned, all reviewable, all exportable.

> **Ontology → Content → Profiles → Coverage → Export**

| Layer | What | How it changes |
|---|---|---|
| **Specification** | Ontology + profile + gap definition | Rarely |
| **Computation** | Coverage calculation under a fixed measure | Iteratively |
| **Presentation** | Export (MCP, CLI, web, Obsidian) | Fully open |

## Core idea

One **canonical** competency skeleton (files in git), many surfaces:

- **Assessment** — test exports, interview kits
- **Learning** — course packs, cheat sheets, how-to guides
- **Reporting** — coverage matrices, quality reports, Mermaid graphs

No duplication across surfaces. One edit in the ontology reflects everywhere.

## Documents

- [Concept](concept.md) — full methodology concept: lifecycle, three layers, invariants
- [Why SDM?](why-sdm.md) — what SDM adds that a bare agent cannot provide
- [Glossary](glossary.md) — key terms defined
- ADR — architecture decisions (naming, scope)

## What SDM is not

- Not an HR testing platform or LMS
- Not a tool / product — CLI, MCP, plugins are *implementations*, not the methodology
- Not a storage format (YAML is not required)
- The methodology defines only coverage invariants; content quality judges and conformance tests are outside SDM

## Soundness criterion

A person without SDM context reads these documents and explains the methodology to someone else without asking to "show the code."

## Repository map

| Path | Purpose |
|---|---|
| `README.md` | Entry point (this file) |
| `concept.md` | Full concept: lifecycle, three layers, invariants |
| `why-sdm.md` | Why SDM vs a bare agent |
| `glossary.md` | Key terms |
| `adr/` | Architecture Decision Records |

See also: [sdm](https://github.com/spec-driven-methodology/sdm) (reference implementation: CLI, MCP, npm package).