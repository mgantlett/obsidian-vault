---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/CryptocurrencySymbol
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# CryptocurrencySymbol (Schema)

Canonical YAML fragment (extracted from API):

```yaml
CryptocurrencySymbol:
  description: Symbol to identify a cryptocurrency or fiat currency on a crypto exchange. Fiat currencies symbols are ISO-4217 codes.
  type: string
  example: BTC
CryptocurrencyBaseSymbol:
  description: >
    The base currency of a pair (e.g., "BTC" in BTC/USD).
    Either fiat or cryptocurrency symbol, for fiat use ISO-4217 codes.
  type: string
  example: BTC
CryptocurrencyQuoteSymbol:
  description: >
    The quote currency of a pair (e.g., "USD" in BTC/USD).
    Either fiat or cryptocurrency symbol, for fiat use ISO-4217 codes.
  type: string
  example: USD
CryptocurrencyPairSymbol:
  description: Cryptocurrency pair instrument symbol
  type: string
  example: BTC-USD
CryptocurrencyPair:
  description: A cryptocurrency pair instrument.
  type: object
  required: ["base", "quote"]
  properties:
    symbol:
      $ref: "#/components/schemas/CryptocurrencyPairSymbol"
    base:
      $ref: "#/components/schemas/CryptocurrencyBaseSymbol"
    quote:
      $ref: "#/components/schemas/CryptocurrencyQuoteSymbol"
CryptocurrencyPairQuote:
  type: object
  required: ["bid", "ask"]
  properties:
    bid:
      description: The highest price a buyer is willing to pay.
      type: string
      format: decimal
      example: "123.45"
    ask:
      description: The lowest price a seller is willing to accept.
      type: string
      format: decimal
      example: "123.45"
    mid:
      description: The market mid price.
      type: string
      format: decimal
      example: "123.45"
    timestamp:
      description: The timestamp of the quote.
      type: string
      format: date-time
      example: 2024-01-24T15:00:00Z
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/CryptocurrencySymbol

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (CryptocurrencySymbol)
