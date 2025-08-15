---
tags: [template, model, domain]
template: entity
entity: "PerformanceMetrics"
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

# PerformanceMetrics

Performance metrics for portfolio analysis.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    total_return:
      type: number | null
      description: "Total return percentage"
    sharpe_ratio:
      type: number | null
      description: "Sharpe ratio"
    max_drawdown:
      type: number | null
      description: "Maximum drawdown percentage"
    volatility:
      type: number | null
      description: "Volatility"
    currency:
      type: string
      description: "Currency of the performance metrics"
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `PerformanceMetrics` in `markbot/src/markbot/domain/models.py`.

## Example JSON
```json
{ "total_return": 12.5, "sharpe_ratio": 1.2, "max_drawdown": 5.3, "volatility": 8.1, "currency": "USD" }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- Canvas: projects/finance-apps/canvas/domain-model.canvas
