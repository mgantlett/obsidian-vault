---
tags: [template, model, domain]
template: entity
entity: "Trade"
source: markbot/src/markbot/domain/models.py
owner: infra
status: draft
cache_ttl: 3600
version: 1
migration_state: draft
sensitive: false
generated_paths: []
tests: []
examples: []
---

# Trade

Represents a single trade record.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      description: "The unique identifier for the trade."
    account:
      type: Account
      description: "The account in which the trade occurred."
    symbol:
      type: UniversalSymbol
      description: "The symbol that was traded."
    action:
      type: string
      description: "The action of the trade (e.g., 'BUY', 'SELL')."
    order_type:
      type: string
      description: "The type of order used for the trade."
    price:
      type: float
      description: "The price per unit for the trade."
    quantity:
      type: int
      description: "The number of units traded."
    time_in_force:
      type: string
      description: "The time in force for the trade order."
    status:
      type: string
      description: "The status of the trade."
    created_date:
      type: string
      description: "The date the trade was created."
    updated_date:
      type: string
      description: "The date the trade was last updated."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: canonical trade records for execution history and P&L calculation.
- Validation: timestamps should be ISO-8601; numeric fields validated against fills and orders.

## Example JSON
```json
{
  "id": "trade-abcdef-123456",
  "account": { "id": "acc-1234-5678" },
  "symbol": { "id": "...", "symbol": "AAPL" },
  "action": "BUY",
  "order_type": "market",
  "price": 174.5,
  "quantity": 10,
  "time_in_force": "GTC",
  "status": "filled",
  "created_date": "2025-08-14T12:00:00Z",
  "updated_date": "2025-08-14T12:00:03Z"
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (Trade)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
