---
tags: [template, model,domain]
template: entity
entity: "TradeImpact"
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

# TradeImpact

Represents the estimated impact of a trade on an account.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    estimated_commissions:
      type: float
      description: "Estimated commissions for the trade."
    estimated_total_amount:
      type: float
      description: "Estimated total amount of the trade."
    side:
      type: string
      description: "The side of the trade (e.g., 'buy', 'sell')."
    symbol:
      type: UniversalSymbol
      description: "The symbol being traded."
    filled_quantity:
      type: int
      description: "The quantity of the trade that was filled."
    action:
      type: string
      description: "The action of the trade (e.g., 'BUY', 'SELL')."
    price:
      type: float
      description: "The price at which the trade was executed."
    currency:
      type: string
      description: "The currency of the trade."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: returned by calculators/previews to show costs and fill/impact estimates prior to order submission.
- Validation: monetary fields should align with `currency` and quantities be integers.

## Example JSON
```json
{
  "estimated_commissions": 1.25,
  "estimated_total_amount": 1725.00,
  "side": "buy",
  "symbol": { "id": "...", "symbol": "AAPL", "exchange": { "code": "NASDAQ" } },
  "filled_quantity": 10,
  "action": "BUY",
  "price": 172.5,
  "currency": "USD"
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (TradeImpact)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
