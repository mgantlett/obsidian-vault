---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/Units
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# Units (Schema)

Canonical YAML fragment (extracted from API):

```yaml
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/Units

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (Units)
