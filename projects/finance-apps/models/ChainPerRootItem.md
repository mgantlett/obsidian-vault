---
tags: [template, model, domain]
template: entity
entity: "ChainPerRootItem"
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

# ChainPerRootItem

Represents an item in the option chain for a specific root.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    optionRoot:
      type: string | null
      description: "The root of the option."
    chainPerStrikePrice:
      type: list[ChainPerStrikePriceItem]
      description: "The option chain per strike price."
    multiplier:
      type: integer | null
      description: "The multiplier of the option."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `ChainPerRootItem` in `markbot/src/markbot/domain/models.py` and part of `OptionChain` in `references/snaptrade-sdk/api.yaml`.

## Example JSON
```json
{
  "optionRoot": "AAPL",
  "chainPerStrikePrice": [ { "strikePrice": 70, "callSymbolId": 42816081, "putSymbolId": 42816129 } ],
  "multiplier": 100
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- API spec: `references/snaptrade-sdk/api.yaml` (OptionChain)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
