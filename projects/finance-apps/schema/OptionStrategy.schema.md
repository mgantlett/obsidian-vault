---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/OptionStrategy
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# OptionStrategy (Schema)

Canonical YAML fragment (extracted from API):

```yaml
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/OptionStrategy

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (OptionStrategy)
