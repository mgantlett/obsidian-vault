---
tags: [schema, domain, position]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: markbot/src/markbot/domain/models.py#Position
owner: infra
created: 2025-08-14
last-updated: 2025-08-14
---

# Position (Schema)

Canonical YAML schema for the Position entity.

```yaml
title: Position
description: "Describes a single security position held in an account"
properties:
  symbol:
    $ref: '#/components/schemas/PositionSymbol'
    description: "The security for the position."
  account:
    $ref: '#/components/schemas/Account'
    description: "The account that holds the position."
  units:
    type: [number, null]
    description: "The number of shares of the position."
  price:
    type: [number, null]
    description: "Last known market price for the symbol."
  open_pnl:
    type: [number, null]
    description: "The profit or loss on the position since it was opened."
  average_purchase_price:
    type: [number, null]
    description: "Cost basis per share of this position."
required: [symbol, account]
redis_indexes:
  - name: positions_by_account
    fields: [account]
    type: tag

cache_ttl: 3600
```

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

## Notes
- Used by portfolio views, P&L calculations, and risk/exposure reporting.
- Relationships: links to `PositionSymbol` and `Account` entities.
- Validation: `units` and `average_purchase_price` should be non-negative; `account` must exist and be active.

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (Position)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
