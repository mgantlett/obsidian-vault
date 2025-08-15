---
tags: [template, model, domain]
template: entity
entity: "OptionLeg"
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

# OptionLeg

Option Leg.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    action:
      type: string
      description: "The action of the leg (e.g., 'buy', 'sell')."
    option_symbol:
      type: UniversalSymbol
      description: "The symbol of the option leg."
    ratio:
      type: int
      description: "The ratio of the leg."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: represents a single leg within an options multi-leg position or order.
- Relationships: references `UniversalSymbol` for the option contract.

## Example JSON
```json
{
  "action": "buy",
  "option_symbol": { "id": "...", "symbol": "AAPL220917C00175000", "exchange": { "code": "OPR" } },
  "ratio": 1
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (OptionLeg)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
