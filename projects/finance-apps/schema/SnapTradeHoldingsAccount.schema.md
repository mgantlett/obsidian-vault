---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/SnapTradeHoldingsAccount
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# SnapTradeHoldingsAccount (Schema)

Canonical YAML fragment (extracted from API):

```yaml
SnapTradeHoldingsAccount:
  description: SnapTradeUser Investment Account
  type: object
  properties:
    id:
      $ref: "#/components/schemas/Id"
    brokerage_authorization:
      $ref: "#/components/schemas/BrokerageAuthorization"
    portfolio_group:
      $ref: "#/components/schemas/Id"
    name:
      type: string
      example: Registered Retirement Savings Account
      nullable: true
    number:
      type: string
      example: Q6542138443
    institution_name:
      type: string
      example: Alpaca
    sync_status:
      $ref: "#/components/schemas/AccountSyncStatus"
    meta:
      type: object
      example:
        type: Margin
        status: ACTIVE
        institution_name: Alpaca
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/SnapTradeHoldingsAccount

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (SnapTradeHoldingsAccount)
