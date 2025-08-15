---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/SnapTradeLoginUserRequestBody
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# SnapTradeLoginUserRequestBody (Schema)

Canonical YAML fragment (extracted from API):

```yaml
SnapTradeLoginUserRequestBody:
  content:
    application/json:
      schema:
        $ref: "#/components/schemas/SnapTradeLoginUserRequestBody"
ManualTradeFormRequestBody:
  required: true
  content:
    application/json:
      schema:
        $ref: "#/components/schemas/ManualTradeForm"
ManualTradeFormRequestBodyWithOptions:
  required: true
  content:
    application/json:
      schema:
        $ref: "#/components/schemas/ManualTradeFormWithOptions"
ManualTradeFormRequestBodyBracket:
  required: true
  content:
    application/json:
      schema:
        $ref: "#/components/schemas/ManualTradeFormBracket"
ManualTradeReplaceFormRequestBody:
  required: true
  content:
    application/json:
      schema:
        $ref: "#/components/schemas/ManualTradeReplaceForm"
ValidatedTradeRequestBody:
  required: false
  content:
    application/json:
      schema:
        $ref: "#/components/schemas/ValidatedTradeBody"
CancelOrderRequestBody:
  required: true
  content:
    application/json:
      schema:
        type: object
        properties:
          brokerage_order_id:
            $ref: "#/components/schemas/BrokerageOrderID"
OptionStrategyRequestBody:
  required: true
  content:
    application/json:
      schema:
        type: object
        required: ["underlying_symbol_id", "legs", "strategy_type"]
        properties:
          underlying_symbol_id:
            $ref: "#/components/schemas/Id"
          legs:
            type: array
            items:
              $ref: "#/components/schemas/OptionLeg"
          strategy_type:
            type: string
            enum:
              - CUSTOM
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/SnapTradeLoginUserRequestBody

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (SnapTradeLoginUserRequestBody)
