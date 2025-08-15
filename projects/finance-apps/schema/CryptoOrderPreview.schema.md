---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/CryptoOrderPreview
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# CryptoOrderPreview (Schema)

Canonical YAML fragment (extracted from API):

```yaml
CryptoOrderPreview:
  description: Preview of an order.
  type: object
  properties:
    estimated_fee:
      type: object
      required: ["currency", "amount"]
      description: The estimated order fee.
      properties:
        currency:
          $ref: "#/components/schemas/CryptocurrencySymbol"
        amount:
          type: string
          format: decimal
          example: "123.45"
OrderUpdatedResponse:
  type: object
  required:
    - brokerage_order_id
  properties:
    brokerage_order_id:
      $ref: "#/components/schemas/BrokerageOrderID"
    order:
      $ref: "#/components/schemas/AccountOrderRecord"
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/CryptoOrderPreview

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (CryptoOrderPreview)
