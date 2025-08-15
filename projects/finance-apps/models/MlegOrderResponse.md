---
tags: [template, model, domain]
template: entity
entity: "MlegOrderResponse"
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

# MlegOrderResponse

Represents the response from placing a multi-leg order.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    brokerage_order_id:
      type: string
      description: "The brokerage order ID for the multi-leg order."
    orders:
      type: list[AccountOrderRecord]
      description: "A list of individual orders created for each leg."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `MlegOrderResponse` in `markbot/src/markbot/domain/models.py`.
- Used by options multi-leg order flows and order tracking.

## Example JSON
```json
{
  "brokerage_order_id": "66a033fa-da74-4fcf-b527-feefdec9257e",
  "orders": [ { "brokerage_order_id": "leg-1", "status": "PENDING" } ]
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (MlegOrderResponse)
- API spec: `references/snaptrade-sdk/api.yaml` (MlegOrderResponse)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
