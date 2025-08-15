---
tags: [template, model, domain]
template: entity
entity: "OrderUpdatedResponse"
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

# OrderUpdatedResponse

Response returned when an order is updated.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    brokerage_order_id:
      type: string
      description: "The brokerage order ID."
    order:
      type: AccountOrderRecord
      description: "The updated order record."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `OrderUpdatedResponse` in `markbot/src/markbot/domain/models.py`.

## Example JSON
```json
{ "brokerage_order_id": "abc-123", "order": { "id": "leg-1", "status": "FILLED" } }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- Canvas: projects/finance-apps/canvas/domain-model.canvas
