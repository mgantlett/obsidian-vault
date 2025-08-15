---
tags: [template, model, domain]
template: entity
entity: "CryptoOrderPreview"
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

# CryptoOrderPreview

Preview of an order for crypto instruments.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    estimated_fee:
      type: object
      description: "The estimated order fee."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `CryptoOrderPreview` in `markbot/src/markbot/domain/models.py`.
- Used for order preview UI and fee estimation.

## Example JSON
```json
{ "estimated_fee": { "amount": 0.0001, "currency": "BTC" } }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- Canvas: projects/finance-apps/canvas/domain-model.canvas
