---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/TakeProfit
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# TakeProfit (Schema)

Canonical YAML fragment (extracted from API):

```yaml
TakeProfit:
  description: Details of the take profit order. Only to be used when order_class = BRACKET.
  type: object
  properties:
    limit_price:
      type: string
      example: "49.95"
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/TakeProfit

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (TakeProfit)
