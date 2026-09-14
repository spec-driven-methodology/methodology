# SDM — Spec-Driven Methodology

A methodology for treating methodological artifacts (ontologies, profiles, coverage) as specifications: they are written once, verified by machine, and everything derived (exports, reports) is generated.

## Lifecycle (artifacts, not commands)

> **Ontology → Profile → Coverage → Export**

- **Ontology** — a graph of nodes (skills/topics/lessons/programs) and their relations
- **Profile** — what we select from the ontology and up to which threshold
- **Coverage** — what is missing: the set of gap nodes under a fixed definition
- **Export** — where the result goes (MCP, Obsidian, web, CLI)

No matter who performs the steps (a human or an agent), the artifact chain is the same.

## Three layers

| Layer | What | How it changes |
|---|---|---|
| **Specification** | Ontology + profile + gap definition | Rarely |
| **Computation** | Coverage calculation under a fixed measure | Iteratively |
| **Presentation** | Export (MCP/Obsidian/web/CLI) | Fully open |

## Invariants (≤5)

1. Given the same ontology and profile, the set of gap nodes is identical across any implementation. The gap definition is fixed by the methodology — implementations do not choose it.

## What it is not

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

A person without SDM context reads the concept and explains the methodology to someone else without asking to "show the code" — so the concept must be readable standalone, and this document is the entry point.