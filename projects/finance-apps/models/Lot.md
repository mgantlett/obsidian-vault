---
tags: [template, model, domain]
template: entity
entity: "Lot"
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

# Lot

Represents a single lot of a security.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      description: "Unique identifier for the lot."
    universal_symbol_id:
      type: string
      description: "The universal symbol ID of the security."
    symbol:
      type: string | null
      description: "The ticker symbol (e.g., 'AAPL')."
    description:
      type: string | null
      description: "Human-readable description of the security."
    account_id:
      type: string
      description: "The account ID that holds the lot."
    open_date:
      type: string
      description: "The date the lot was opened."
    quantity:
      type: number
      description: "The number of units in the lot."
    open_price:
      type: number
      description: "The price at which the lot was opened."
    cost_basis:
      type: number
      description: "The total cost of the lot."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `Lot` in `markbot/src/markbot/domain/models.py`.

## Example JSON
```json
{ "id": "lot-1", "universal_symbol_id": "usym-123", "symbol": "AAPL", "account_id": "acct-1", "open_date": "2024-01-02", "quantity": 10, "open_price": 150.0, "cost_basis": 1500.0 }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- Canvas: projects/finance-apps/canvas/domain-model.canvas
