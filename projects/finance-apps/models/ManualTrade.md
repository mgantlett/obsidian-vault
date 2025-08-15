---
tags: [template, model, domain]
template: entity
entity: "ManualTrade"
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

# ManualTrade

Contains the details of a submitted order.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      description: "Unique identifier for the submitted order through SnapTrade."
    account:
      type: string
      description: "The account ID that the order was placed in."
    order_type:
      type: string
      description: "The type of order to place."
    time_in_force:
      type: string
      description: "The Time in Force type for the order."
    symbol:
      type: ManualTradeSymbol
      description: "Information about the security for the order."
    action:
      type: string
      description: "The action describes the intent or side of a trade."
    units:
      type: number | null
      description: "Number of shares for the order."
    price:
      type: number | null
      description: "Trade Price if limit or stop limit order."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: payload returned/recorded for manual trade submissions via the API/UI.
- Validation: `units` and `price` requirements depend on `order_type`.

## Example JSON
```json
{
  "id": "mt-abcdef-123456",
  "account": "acc-1234-5678",
  "order_type": "limit",
  "time_in_force": "GTC",
  "symbol": { "universal_symbol_id": "8b7c6d5e-...", "symbol": "AAPL", "currency": { "code": "USD" } },
  "action": "BUY",
  "units": 10,
  "price": 172.5
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (ManualTrade)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
