---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/CancelOrderResponse
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# CancelOrderResponse (Schema)

Canonical YAML fragment (extracted from API):

```yaml
CancelOrderResponse:
  type: object
  required:
    - brokerage_order_id
  properties:
    brokerage_order_id:
      $ref: "#/components/schemas/BrokerageOrderID"
    raw_response:
      type: object
      nullable: true
      description: The raw response from the brokerage.
      example: {
        "order_id": "1234567890",
        "status": "CANCELLED"
      }
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/CancelOrderResponse

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (CancelOrderResponse)
