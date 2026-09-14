# SDM Glossary

| Term | Definition |
|---|---|
| **SDM** | Spec-Driven Methodology — a methodology-as-specs framework for competency assessment and skills management |
| **Canonical** | The single source of truth for competency artifacts, stored in git as YAML files |
| **Ontology** | A graph of nodes of any `kind` (`skill`, `concept`, `topic`, `question`, `term`, `talk`, `course`, `product`, …) and their relations (`depends_on`, `related_to`). Content is part of the ontology: questions and terms are nodes with their own `kind` |
| **Kind** | The type of an ontology node. Nodes of any kind live in the same graph; nothing about the methodology depends on a fixed list of kinds |
| **Profile** | A certification profile that selects nodes from the ontology with depth and weight requirements |
| **Level** | A certification level within a profile: a set of requirements (node + depth + weight) and a pass threshold |
| **Coverage** | The calculated state of how well the ontology's content covers a certification level's requirements; reported as ok / thin / missing per node |
| **Gap** | A requirement that is either missing (zero content) or thin (insufficient count or depth ratio) |
| **Depth ratio** | `achievedDepth / requiredDepth` — the fraction of required mastery that the content provides |
| **Weight** | The share of the final score assigned to a requirement (sum of all weights = 1) |
| **Export** | Delivery mechanics (Presentation layer): a generated artifact from the canonical — test pack, learning course, interview kit, matrix, Mermaid graph, Confluence page. Not a stage of the artifact chain |
| **Intent-loop** | The lifecycle's primary human UX pattern: clarify → plan → confirm → execute → result |
| **Portable skill** | An agent skill (`SKILL.md`) shipped with SDM and installed into the agent host (AI IDE) via `sdm agent install` or `sdm mcp install` |
| **Layer** | One of Specification / Computation / Presentation — a static view of the methodology (what it is made of, how often it changes) |
| **Lifecycle** | The dynamic view of the methodology: Human Intent → Agent + LLM → CLI / MCP / Skills → SDM → Specs YAML |