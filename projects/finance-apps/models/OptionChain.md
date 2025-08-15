---
tags: [template, model, domain]
template: entity
entity: "OptionChain"
source: references/snaptrade-sdk/api.yaml
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

# OptionChain

Options chain response structure returned by SnapTrade.

## SOT (YAML fragment)
```yaml
sot:
  type: array
  items:
    fields:
      expiryDate:
        type: string
        description: "Expiry date for the chain page."
      description:
        type: string
        description: "Human readable description (e.g. underlying company)."
      listingExchange:
        type: string
        description: "Listing exchange code."
      optionExerciseType:
        type: string
        description: "Option exercise type (American/European)."
      chainPerRoot:
        type: array
        items:
          fields:
            optionRoot:
              type: string
            chainPerStrikePrice:
              type: array
              items:
                fields:
                  strikePrice:
                    type: number | null
                  callSymbolId:
                    type: integer | null
                  putSymbolId:
                    type: integer | null
    cache_ttl: 3600
    meta:
      owner: infra
      version: 1
```

## Notes
- Mirrors `components.schemas.OptionChain` in the SnapTrade OpenAPI spec.
- Useful for option chain browsing and building OptionChainItem/Strike-level entities.

## Example (trimmed)
```json
[
  {
    "expiryDate": "2024-07-08T00:00:00-04:00",
    "description": "APPLE INC",
    "listingExchange": "OPRA",
    "optionExerciseType": "American",
    "chainPerRoot": [
      {
        "optionRoot": "AAPL",
        "chainPerStrikePrice": [
          { "strikePrice": 70, "callSymbolId": 42816081, "putSymbolId": 42816129 }
        ]
      }
    ]
  }
]
```

## Backlinks & Code references
- API schema: references/snaptrade-sdk/api.yaml (OptionChain)
- Domain model: markbot/src/markbot/domain/models.py
- Canvas: projects/finance-apps/canvas/domain-model.canvas
