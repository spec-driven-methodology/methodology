# Why SDM, not just an agent with a model?

An agent with a model (harness) can "do" — write an ontology, questions, exports — and it looks the same. SDM adds what a bare agent cannot give: **a fixed definition of correctness and verifiability**.

## Without SDM

An agent answering "what's missing in this profile?" replies from its own understanding — that is the **opinion** of one model in one context.

- **Unverifiable** — there is no formula that produced the answer
- **Non-reproducible** — a different agent (or the same one an hour later) gives a different list
- **No threshold** — "looks like enough" vs "looks thin" is judged by eye every time
- **No audit trail** — you cannot say "between version 3 and 4 this changed"

## With SDM

| Property | How it works |
|---|---|
| **Deterministic coverage** | Same ontology + profile → same gap list across any implementation (invariant 1). Compare — `diff` of two runs is byte-identical. |
| **Machine self-check** | `sdm doctor`, `validate`, `coverage` catch broken links, invalid kinds, weights ≠ 1, graph cycles — before the defect reaches export. |
| **Thresholds and criteria** | "Profile passes when every skill has ≥3 questions AND depthRatio ≥ 0.9" — fixed, not eyeballed. |
| **Audit through git** | Artifacts are specs: diffs, history, reviews. "What changed between versions?" — `git diff`, not re-asking the model. |
| **One skeleton → many surfaces** | Exports (MCP/Obsidian/web/CLI/test/course) from one source. Without SDM, every export is a manual assembly. |

## Side by side

| With SDM | Without SDM |
|---|---|
| `❌ ontology-concept: achievedDepth=0, questions=0` | "I feel like something is missing" |
| `diff` of two runs — identical | No way to verify |
| Threshold 0.9 / 3 questions — fixed | "Uh, maybe 5...?" |
| Any tool → same result | Depends on model context |

## Demonstration

```bash
# Two independent coverage runs — results identical
sdm cert coverage --profile sdm --level current --json > run1.json
sdm cert coverage --profile sdm --level current --json > run2.json
diff run1.json run2.json  # → empty: byte-identical
```

A bare agent asked the same question gives different answers from run to run.