---
tags: [template, model, domain]
template: entity
entity: "ChainPerStrikePriceItem"
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

# ChainPerStrikePriceItem

Represents an item in the option chain for a specific strike price.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    strikePrice:
      type: integer | null
      description: "The strike price of the option."
    callSymbolId:
      type: integer | null
      description: "The symbol ID of the call option."
    putSymbolId:
      type: integer | null
      description: "The symbol ID of the put option."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `ChainPerStrikePriceItem` in `markbot/src/markbot/domain/models.py` and `OptionChain` structures in `references/snaptrade-sdk/api.yaml`.

## Example JSON
```json
{ "strikePrice": 70, "callSymbolId": 42816081, "putSymbolId": 42816129 }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- API spec: `references/snaptrade-sdk/api.yaml` (OptionChain)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
