---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/StopLoss
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# StopLoss (Schema)

Canonical YAML fragment (extracted from API):

```yaml
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/StopLoss

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (StopLoss)
