---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/MlegOrderResponse
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# MlegOrderResponse (Schema)

Canonical YAML fragment (extracted from API):

```yaml
MlegOrderResponse:
  type: object
  required:
    - brokerage_order_id
    - orders
  properties:
    brokerage_order_id:
      $ref: "#/components/schemas/BrokerageOrderID"
    orders:
      type: array
      items:
        $ref: "#/components/schemas/AccountOrderRecord"
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/MlegOrderResponse

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (MlegOrderResponse)
