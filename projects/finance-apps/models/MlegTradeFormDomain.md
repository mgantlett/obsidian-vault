---
tags: [template, model, domain]
template: entity
entity: "MlegTradeFormDomain"
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

# MlegTradeFormDomain

Inputs for placing a multi-leg order with the brokerage.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    order_type:
      type: string
      description: "The type of order to place."
    time_in_force:
      type: string
      description: "The Time in Force type for the order."
    legs:
      type: list[MlegLeg]
      description: "The legs of the order."
    limit_price:
      type: number | null
      description: "The limit price."
    stop_price:
      type: number | null
      description: "The stop price."
    price_effect:
      type: string | null
      description: "The desired price_effect for LIMIT and STOP_LOSS_LIMIT orders."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `MlegTradeFormDomain` in `markbot/src/markbot/domain/models.py`.
- References `MlegLeg` model for leg definitions.

## Example JSON
```json
{ "order_type": "LIMIT", "time_in_force": "GTC", "legs": [ { "symbol": "AAPL", "units": 1 } ], "limit_price": 1.23 }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- Related model: `projects/finance-apps/models/MlegLeg.md`
- Canvas: projects/finance-apps/canvas/domain-model.canvas
