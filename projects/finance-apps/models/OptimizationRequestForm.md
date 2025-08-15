---
tags: [template, model, domain]
template: entity
entity: "OptimizationRequestForm"
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

# OptimizationRequestForm

Inputs for running strategy optimization with Optuna.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    strategy:
      type: string
      description: "The trading strategy to optimize."
    n_trials:
      type: integer
      description: "Number of optimization trials to run."
    engine:
      type: string
      description: "The backtesting engine to use."
    use_sample:
      type: boolean
      description: "Use sample portfolio instead of real one."
    direction:
      type: string
      description: "Optimization direction (maximize or minimize)."
    symbols:
      type: list[string] | null
      description: "Optional list of symbols to test on."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `OptimizationRequestForm` in `markbot/src/markbot/domain/models.py`.

## Example JSON
```json
{ "strategy": "my-strategy", "n_trials": 100, "engine": "vectorbt", "direction": "maximize" }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- UI: optimization controls in spendviz
