---
tags: [template, model, domain]
template: entity
entity: "OptionChainItem"
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

# OptionChainItem

Chain of options for a given expiry.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    expiryDate:
      type: string
      description: "The expiry date of the options."
    description:
      type: string | null
      description: "Description of the option chain."
    listingExchange:
      type: string | null
      description: "The exchange where the options are listed."
    optionExerciseType:
      type: string | null
      description: "The exercise type of the options (e.g., 'American')."
    chainPerRoot:
      type: list[ChainPerRootItem]
      description: "A list of option chains per root symbol."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `OptionChainItem` in `markbot/src/markbot/domain/models.py`.
- Related to `OptionChain` and `ChainPerRootItem`.

## Example JSON
```json
{
  "expiryDate": "2024-07-08T00:00:00-04:00",
  "description": "APPLE INC",
  "listingExchange": "OPRA",
  "optionExerciseType": "American",
  "chainPerRoot": [ { "optionRoot": "AAPL", "chainPerStrikePrice": [] } ]
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- API spec: `references/snaptrade-sdk/api.yaml` (OptionChain)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
