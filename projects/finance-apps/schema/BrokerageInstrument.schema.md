---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/BrokerageInstrument
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# BrokerageInstrument (Schema)

Canonical YAML fragment (extracted from API):

```yaml
BrokerageInstrument:
  type: object
  properties:
    symbol:
      description: The instrument's trading symbol / ticker.
      type: string
      example: AAPL
    exchange_mic:
      description: The MIC code of the exchange where the instrument is traded.
      type: string
      example: XNAS
      nullable: true
    tradeable:
      description: Whether the instrument is tradeable through the brokerage. `null` if the tradeability is unknown.
      type: boolean
      example: true
      nullable: true
    fractionable:
      description: Whether the instrument allows fractional units. `null` if the fractionability is unknown.
      type: boolean
      example: true
      nullable: true
    universal_symbol_id:
      description: The universal symbol ID of the instrument. This is the ID used to reference the instrument in SnapTrade API calls.
      type: string
      format: uuid
      example: 2bcd7cc3-e922-4976-bce1-9858296801c3
      nullable: true
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/BrokerageInstrument

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (BrokerageInstrument)
