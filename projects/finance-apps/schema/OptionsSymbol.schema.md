---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/OptionsSymbol
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# OptionsSymbol (Schema)

Canonical YAML fragment (extracted from API):

```yaml
OptionsSymbol:
  description: Uniquely describes an option security + exchange combination across all brokerages.
  type: object
  required:
    - id
    - ticker
    - option_type
    - strike_price
    - expiration_date
    - underlying_symbol
  properties:
    id:
      $ref: "#/components/schemas/OptionSymbolID"
    ticker:
      description: The [OCC symbol](https://en.wikipedia.org/wiki/Option_symbol) for the option.
      type: string
      example: AAPL  261218C00240000
    option_type:
      description: The type of option. Either "CALL" or "PUT".
      type: string
      enum:
        - CALL
        - PUT
      example: CALL
    strike_price:
      description: The option strike price.
      type: number
      example: 240
    expiration_date:
      description: The option expiration date.
      type: string
      format: date
      example: "2026-12-18"
    is_mini_option:
      description: Whether the option is a mini option. Mini options have 10 underlying shares per contract instead of the standard 100.
      type: boolean
      example: false
    underlying_symbol:
      $ref: "#/components/schemas/UnderlyingSymbol"
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/OptionsSymbol

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (OptionsSymbol)
