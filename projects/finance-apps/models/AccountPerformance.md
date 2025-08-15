---
tags: [template, model, domain]
template: entity
entity: "AccountPerformance"
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

# AccountPerformance

Performance metrics for a single account.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    account_id:
      type: string
      description: "The ID of the account."
    account_name:
      type: string
      description: "The name of the account."
    performance:
      type: PerformanceMetrics
      description: "The performance metrics for the account."
    symbols:
      type: list[string]
      description: "List of symbols backtested for this account."
    symbol_details:
      type: list[object] | null
      description: "Detailed performance breakdown by symbol."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `AccountPerformance` in `markbot/src/markbot/domain/models.py`.

## Example JSON
```json
{ "account_id": "acct-1", "account_name": "Main", "performance": { "total_return": 5.3, "currency": "USD" }, "symbols": ["AAPL"], "symbol_details": null }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- Canvas: projects/finance-apps/canvas/domain-model.canvas
