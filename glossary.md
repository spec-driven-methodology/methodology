# SDM Glossary

| Term | Definition |
|---|---|
| **SDM** | Spec-Driven Methodology — a methodology-as-specs framework for competency assessment and skills management |
| **Canonical** | The single source of truth for competency artifacts, stored in git as YAML files |
| **Ontology** | A graph of nodes (skills, topics, concepts, products, persons) and their relations (`depends_on`, `related_to`) |
| **Profile** | A certification profile that selects skills from the ontology with depth and weight requirements |
| **Level** | A certification level within a profile: a set of requirements (skill + depth + weight) and a pass threshold |
| **Coverage** | The calculated state of how well a question library covers a certification level's requirements; reported as ok / thin / missing per skill |
| **Gap** | A skill requirement that is either missing (zero questions) or thin (insufficient count or depth ratio) |
| **Depth ratio** | `achievedDepth / requiredDepth` — the fraction of required mastery that the question library provides |
| **Weight** | The share of the final score assigned to a skill requirement (sum of all weights = 1) |
| **Export** | A generated artifact from the canonical: test pack, learning course, interview kit, matrix, Mermaid graph, Confluence page |
| **Intent-loop** | The primary human UX pattern: clarify → plan → confirm → execute → result |
| **Portable skill** | An agent skill (`SKILL.md`) shipped with SDM and installed into the agent host (AI IDE) via `sdm agent install` or `sdm mcp install` |