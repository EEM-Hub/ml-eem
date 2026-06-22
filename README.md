---
schema_version: "1.0"
type: eem
project_name: "reasons"
domain: []
license: mit
base_network: null
source_repos: []
beliefs_total: 1059
beliefs_in: 930
beliefs_out: 129
premises: 628
derived: 431
nogoods: 0
generator: ftl-reasons/0.48.0
---

# Reasons

## Stats

| Metric | Value |
|--------|-------|
| Total beliefs | 1059 |
| Status | 930 IN / 129 OUT |
| Premises (observations) | 628 |
| Derived (justified conclusions) | 431 |
| Nogoods (contradictions) | 0 |
| Retraction rate | 12% |
| Max derivation depth | 23 |

## How to Use

### Import into a reasons database

```bash
reasons init
reasons import-json network.json
```

### Query beliefs

```bash
reasons search "your query"
reasons explain <node-id>
reasons show <node-id>
```

## Files

| File | Description |
|------|-------------|
| `network.json` | Full belief network (machine-readable, portable) |
| `reasons.db` | SQLite database (gitignored, regenerate with `reasons import-json network.json`) |
| `README.md` | This EEM card |

## Quality

- 930 beliefs IN, 129 OUT
- 628 premises grounded in direct observations
- 431 derived beliefs justified via SL justifications
- 0 nogoods detected

## Exam Results

50-question multiple-choice exam across 16 ML topics, run via `expert-build exam-matrix --agentic`.

| Model | With Beliefs | Control | Agentic | Delta |
|-------|-------------|---------|---------|-------|
| claude:opus | 50/50 (100%) | 50/50 (100%) | 50/50 (100%) | +0% |
| claude:sonnet | 50/50 (100%) | 50/50 (100%) | 49/50 (98%) | +0% |
| claude:haiku | 50/50 (100%) | 50/50 (100%) | 45/50 (90%) | +0% |

- **With Beliefs**: model receives all EEM beliefs as context
- **Control**: model answers from its own knowledge (no beliefs)
- **Agentic**: model uses tool-calling to search beliefs on demand

See `results/matrix-summary.md` for per-objective breakdown.

## Limitations

- Auto-generated card — review and customize for your use case

## License

mit
