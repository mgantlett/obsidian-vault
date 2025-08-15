---
tags: [template, model, domain]
template: entity
entity: "Position"
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

# Position

Purpose: Describes a single stock/ETF/crypto/mutual fund position in an account.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    symbol:
      type: PositionSymbol
      description: "The security for the position."
    account:
      type: Account
      description: "The account that holds the position."
    units:
      type: number | null
      description: "The number of shares of the position."
    price:
      type: number | null
      description: "Last known market price for the symbol."
    open_pnl:
      type: number | null
      description: "The profit or loss on the position since it was opened."
    average_purchase_price:
      type: number | null
      description: "Cost basis _per share_ of this position."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: used by portfolio views, P&L calculations, and risk/exposure reporting.
- Relationships: links to `PositionSymbol` and `Account` entities.
- Validation: `units` and `average_purchase_price` should be non-negative where applicable; `account` must exist and be active.

## Example JSON
```json
{
  "symbol": {
    "id": "c0ffee00-aaaa-1111-2222-333344445555",
    "symbol": "AAPL",
    "exchange": { "code": "NASDAQ" }
  },
  "account": {
    "id": "acc-1234-5678-90ab-cdef",
    "name": "Main Trading Account"
  },
  "units": 100,
  "price": 174.32,
  "open_pnl": 532.00,
  "average_purchase_price": 168.47
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (Position)
- Canvas: projects/finance-apps/canvas/domain-model.canvas