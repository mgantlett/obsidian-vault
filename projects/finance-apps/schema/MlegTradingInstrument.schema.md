---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/MlegTradingInstrument
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# MlegTradingInstrument (Schema)

Canonical YAML fragment (extracted from API):

```yaml
MlegTradingInstrument:
  type: object
  required:
    - symbol
    - instrument_type
  properties:
    symbol:
      description: The security's trading ticker symbol. This currently supports stock symbols and Options symbols in the 21 character OCC format. For example `AAPL  131124C00240000` represents a call option on AAPL expiring on 2024-11-13 with a strike price of $240. For more information on the OCC format, see [here](https://en.wikipedia.org/wiki/Option_symbol#OCC_format)
      type: string
      example: PBI   250718C00006000
    instrument_type:
      $ref: "#/components/schemas/MlegInstrumentType"
OrderTypeStrict:
  description: |
    The type of order to place.
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/MlegTradingInstrument

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (MlegTradingInstrument)
