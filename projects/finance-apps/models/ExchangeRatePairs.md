---
tags: [template, model, domain]
template: entity
entity: "ExchangeRatePairs"
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

# ExchangeRatePairs

Represents an exchange rate pair between two currencies.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    src:
      type: Currency
      description: "The source currency."
    dst:
      type: Currency
      description: "The destination currency."
    exchange_rate:
      type: number
      description: "The exchange rate."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `ExchangeRatePairs` in `markbot/src/markbot/domain/models.py`.
- `Currency` is a referenced type (see unified domain schemas).

## Example JSON
```json
{ "src": "USD", "dst": "CAD", "exchange_rate": 1.3445 }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- Unified schemas: `markbot/schemas/unified_domain.yaml`
- Canvas: projects/finance-apps/canvas/domain-model.canvas
