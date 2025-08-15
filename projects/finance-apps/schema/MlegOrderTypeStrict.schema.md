---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/MlegOrderTypeStrict
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# MlegOrderTypeStrict (Schema)

Canonical YAML fragment (extracted from API):

```yaml
MlegOrderTypeStrict:
  example: MARKET
  type: string
  enum:
    - MARKET
    - LIMIT
    - STOP_LOSS_MARKET
    - STOP_LOSS_LIMIT
  description: The type of order to place.
MlegInstrumentType:
  description: The instrument's type
  type: string
  enum:
    - OPTION
    - EQUITY
TimeInForce:
  description: |
    Trade time in force examples:
      * FOK - Fill Or Kill
      * Day - Day
      * GTC - Good Til Canceled
      * GTD - Good Til Date
  type: string
ActionStrict:
  description: The action describes the intent or side of a trade. This is either `BUY` or `SELL`.
  type: string
  enum:
    - BUY
    - SELL
MlegActionStrict:
  description: The action describes the intent and side of a trade. For equities, this is either `BUY` or `SELL`. For options, this is one of `BUY_TO_OPEN`, `BUY_TO_CLOSE`, `SELL_TO_OPEN`, `SELL_TO_CLOSE`.
  type: string
  enum:
    - BUY
    - SELL
    - BUY_TO_OPEN
    - BUY_TO_CLOSE
    - SELL_TO_OPEN
    - SELL_TO_CLOSE
  example: BUY_TO_OPEN
ActionStrictWithOptions:
  description: The action describes the intent or side of a trade. This is either `BUY` or `SELL` for Equity symbols or `BUY_TO_OPEN`, `BUY_TO_CLOSE`, `SELL_TO_OPEN` or `SELL_TO_CLOSE` for Options.
  type: string
  enum:
    - BUY
    - SELL
    - BUY_TO_OPEN
    - BUY_TO_CLOSE
    - SELL_TO_OPEN
    - SELL_TO_CLOSE
Action:
  type: string
  description: >
    The action describes the intent or side of a trade. This is usually `BUY` or `SELL` but can include other potential values like the following depending on the specific brokerage.
      - BUY
      - SELL
      - BUY_COVER
      - SELL_SHORT
      - BUY_OPEN
      - BUY_CLOSE
      - SELL_OPEN
      - SELL_CLOSE
Units:
  description: Number of shares for the order. This can be a decimal for fractional orders. Must be `null` if `notional_value` is provided.
  type: number
  example: 10.5
Price:
  description: Trade Price if limit or stop limit order
  type: number
  nullable: true
  example: 31.33
NotionalValue:
  description: Total notional amount for the order. Must be `null` if `units` is provided. Can only work with `Market` for `order_type` and `Day` for `time_in_force`. This is only available for certain brokerages. Please check the [integrations doc](https://snaptrade.notion.site/66793431ad0b416489eaabaf248d0afb?v=e7bbcbf9f272441593f93decde660687) for more information.
  oneOf:
    - type: string
    - type: number
  example: 100.00
StopLoss:
  description: Details of the stop loss order. Only to be used when order_class = BRACKET. stop_price is required, limit_price is optional
  type: object
  properties:
    stop_price:
      type: string
      example: "48.55"
    limit_price:
      type: string
      nullable: true
      example: "48.50"
TakeProfit:
  description: Details of the take profit order. Only to be used when order_class = BRACKET.
  type: object
  properties:
    limit_price:
      type: string
      example: "49.95"
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/MlegOrderTypeStrict

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (MlegOrderTypeStrict)
