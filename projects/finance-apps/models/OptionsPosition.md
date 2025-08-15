---
tags: [template, model, domain]
template: entity
entity: "OptionsPosition"
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

# OptionsPosition

Describes a single option position in an account.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    symbol:
      type: UniversalSymbol
      description: "The symbol of the options position."
    price:
      type: float
      description: "Last known market price _per share_ of the option contract."
    currency:
      type: string
      description: "The currency of the price."
    average_entry_price:
      type: float
      description: "Cost basis _per contract_ of this option position."
    multiplier:
      type: int
      description: "The multiplier of the option contract."
    open_quantity:
      type: int
      description: "The number of contracts for this option position."
    closed_quantity:
      type: int
      description: "The number of contracts that have been closed."
    pnl:
      type: float
      description: "The profit or loss on the position since it was opened."
    type:
      type: string
      description: "The type of the options position."
    legs:
      type: list[OptionLeg]
      description: "The legs of the options position."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: represents details required for options P&L, margin and multi-leg representation.
- Relationships: composes `OptionLeg` entries and references `UniversalSymbol`.
- Validation: `multiplier` and `open_quantity` should be integers; `average_entry_price` per contract.

## Example JSON
```json
{
  "symbol": { "id": "...", "symbol": "AAPL220917C00175000" },
  "price": 12.5,
  "currency": "USD",
  "average_entry_price": 10.0,
  "multiplier": 100,
  "open_quantity": 2,
  "closed_quantity": 0,
  "pnl": 5.0,
  "type": "call",
  "legs": [ { "action": "buy", "option_symbol": { "id": "..." }, "ratio": 1 } ]
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (OptionsPosition)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
