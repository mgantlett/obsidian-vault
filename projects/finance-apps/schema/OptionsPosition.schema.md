---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/OptionsPosition
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# OptionsPosition (Schema)

Canonical YAML fragment (extracted from API):

```yaml
OptionsPosition:
  description: Describes a single option position in an account.
  type: object
  properties:
    symbol:
      $ref: "#/components/schemas/OptionBrokerageSymbol"
    price:
      type: number
      example: 38.4
      description: Last known market price _per share_ of the option contract. The freshness of this price depends on the brokerage. Some brokerages provide real-time prices, while others provide delayed prices. It is recommended that you rely on your own third-party market data provider for most up to date prices.
      nullable: true
    units:
      type: number
      description: The number of contracts for this option position. A positive number indicates a long position, while a negative number indicates a short position.
      example: -50
    average_purchase_price:
      type: number
      nullable: true
      example: 4126
      description: Cost basis _per contract_ of this option position. To get the cost basis _per share_, divide this value by the number of shares per contract (usually 100).
    currency:
      deprecated: true
      description: The currency of the price. This field is deprecated and will be removed in a future version. The currency of the price is determined by the currency of the underlying security.
      nullable: true
      allOf:
        - $ref: "#/components/schemas/Currency"
OptionStrategy:
  type: object
  properties:
    id:
      $ref: "#/components/schemas/Id"
    underlying_symbol_id:
      $ref: "#/components/schemas/UniversalSymbol"
    strategy_type:
      type: string
      example: BUTTERFLY
    number_of_legs:
      type: number
      example: 2
    legs:
      type: array
      items:
        properties:
          option_symbol_id:
            type: string
            example: AAPLC20221111
          index:
            type: number
            example: 1
          action:
            type: string
            example: BUY_TO_OPEN
          quantity:
            type: number
            example: 10
StrategyQuotes:
  type: object
  properties:
    strategy:
      $ref: "#/components/schemas/OptionStrategy"
    open_price:
      $ref: "#/components/schemas/Price"
    bid_price:
      $ref: "#/components/schemas/Price"
    ask_price:
      $ref: "#/components/schemas/Price"
    volatility:
      type: number
      example: 0.141
    greek:
      type: object
      properties:
        delta:
          type: number
          example: 0.1
        gamma:
          type: number
          example: 0.1
        theta:
          type: number
          example: 0.1
        vega:
          type: number
          example: 0.1
        rho:
          type: number
          example: 0.1
StrategyOrderRecord:
  description: Strategy order record
  type: object
  properties:
    strategy:
      $ref: "#/components/schemas/OptionStrategy"
    status:
      type: string
      enum:
        - PENDING
        - ACCEPTED
        - FAILED
        - REJECTED
        - CANCELED
        - PARTIAL_CANCELED
        - CANCEL_PENDING
        - EXECUTED
        - PARTIAL
        - REPLACE_PENDING
        - REPLACED
        - STOPPED
        - SUSPENDED
        - EXPIRED
        - QUEUED
        - TRIGGERED
        - ACTIVATED
        - PENDING_RISK_REVIEW
        - CONTINGENT_ORDER
    filled_quantity:
      type: number
      example: 10
    open_quantity:
      type: number
      example: 10
    closed_quantity:
      type: number
      example: 10
    order_type:
      $ref: "#/components/schemas/OrderType"
    time_in_force:
      $ref: "#/components/schemas/TimeInForce"
    limit_price:
      $ref: "#/components/schemas/Price"
    execution_price:
      $ref: "#/components/schemas/Price"
    time_placed:
      $ref: "#/components/schemas/Time"
    time_updated:
      $ref: "#/components/schemas/Time"
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/OptionsPosition

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (OptionsPosition)
