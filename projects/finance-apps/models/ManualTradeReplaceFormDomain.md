---
tags: [template, model, domain]
template: entity
entity: "ManualTradeReplaceFormDomain"
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

# ManualTradeReplaceFormDomain

Inputs for replacing an order with the brokerage.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    account_id:
      type: string
      description: "The account ID to place the order in."
    action:
      type: string
      description: "The action of the trade."
    order_type:
      type: string
      description: "The type of order to place."
    time_in_force:
      type: string
      description: "The Time in Force type for the order."
    units:
      type: number
      description: "Number of shares for the order."
    price:
      type: number | null
      description: "Trade Price if limit or stop limit order."
    universal_symbol_id:
      type: string
      description: "The universal symbol ID of the security to trade."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `ManualTradeReplaceFormDomain` in `markbot/src/markbot/domain/models.py`.

## Example JSON
```json
{ "account_id": "acct-1", "action": "SELL", "order_type": "LIMIT", "time_in_force": "GTC", "units": 5, "price": 160.0, "universal_symbol_id": "usym-1" }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- UI: spendviz trading replacement flows
