---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/CryptoOrderForm
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# CryptoOrderForm (Schema)

Canonical YAML fragment (extracted from API):

```yaml
CryptoOrderForm:
  type: object
  required:
    - "instrument"
    - "side"
    - "type"
    - "time_in_force"
    - "amount"
  properties:
    instrument:
      $ref: "#/components/schemas/CryptoTradingInstrument"
    side:
      $ref: "#/components/schemas/ActionStrict"
    type:
      type: string
      enum:
        - MARKET
        - LIMIT
        - STOP_LOSS_MARKET
        - STOP_LOSS_LIMIT
        - TAKE_PROFIT_MARKET
        - TAKE_PROFIT_LIMIT
      description: The type of order to place.
    time_in_force:
      description: >
        The Time in Force type for the order. This field indicates how long the order will remain active before it is executed or expires.
          - `GTC` - Good Til Canceled. The order is valid until it is executed or canceled.
          - `FOK` - Fill Or Kill. The order must be executed in its entirety immediately or be canceled completely.
          - `IOC` - Immediate Or Cancel. The order must be executed immediately. Any portion of the order that cannot be filled immediately will be canceled.
          - `GTD` - Good Til Date. The order is valid until the specified date.
      type: string
      enum:
        - GTC
        - FOK
        - IOC
        - GTD
    amount:
      description: The amount of the base currency to buy or sell.
      type: string
      format: decimal
      example: "123.45"
    limit_price:
      description: The limit price. Required if the order type is LIMIT, STOP_LOSS_LIMIT or TAKE_PROFIT_LIMIT.
      type: string
      format: decimal
      example: "123.45"
    stop_price:
      description: The stop price. Required if the order type is STOP_LOSS_MARKET, STOP_LOSS_LIMIT, TAKE_PROFIT_MARKET or TAKE_PROFIT_LIMIT.
      type: string
      format: decimal
      example: "123.45"
    post_only:
      type: boolean
      example: false
      description: >
        Valid and required only for order type LIMIT.
        If true orders that would be filled immediately are rejected to avoid incurring TAKER fees.
    expiration_date:
      type: string
      format: date-time
      example: "2024-01-01T00:00:00Z"
      description: The expiration date of the order. Required if the time_in_force is GTD.
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/CryptoOrderForm

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (CryptoOrderForm)
