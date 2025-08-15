---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/StrategyQuotes
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# StrategyQuotes (Schema)

Canonical YAML fragment (extracted from API):

```yaml
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/StrategyQuotes

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (StrategyQuotes)
