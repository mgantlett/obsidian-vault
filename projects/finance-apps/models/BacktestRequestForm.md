---
tags: [template, model, domain]
template: entity
entity: "BacktestRequestForm"
source: markbot/src/markbot/domain/models.py
owner: domain
status: draft
cache_ttl: 3600
version: 1
migration_state: draft
sensitive: false
generated_paths: []
tests: []
examples: []
---

# BacktestRequestForm

Inputs for running a portfolio backtest.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    strategy:
      type: string
      description: "The trading strategy to use."
    engine:
      type: string
      description: "The backtesting engine to use."
    use_sample:
      type: boolean
      description: "Use sample portfolio instead of real one."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `BacktestRequestForm` in `markbot/src/markbot/domain/models.py`.

## Example JSON
```json
{ "strategy": "mean-reversion", "engine": "vectorbt", "use_sample": false }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- UI: backtest forms in spendviz
