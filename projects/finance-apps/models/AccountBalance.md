---
tags: [template, model, reference]
template: entity
entity: "AccountBalance"
source: references/snaptrade-sdk/api.yaml
owner: reference
status: draft
cache_ttl: 3600
version: 1
migration_state: synced-from-api
sensitive: false
generated_paths: []
tests: []
examples: []
---

# AccountBalance

Mirrors SnapTrade `components.schemas.AccountBalance`.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    total:
      type: object | null
      description: "Total market value object containing amount and currency."
      properties:
        amount:
          type: number
          description: "Total value denominated in the currency field."
          example: 15363.23
          nullable: true
        currency:
          type: string
          description: "ISO-4217 currency code for the amount."
          example: USD
    balances:
      type: list[Balance] | null
      description: "Per-currency balances for the account."
  cache_ttl: 3600
  meta:
    source: references/snaptrade-sdk/api.yaml#/components/schemas/AccountBalance
    owner: reference
    version: 1
```

## Notes
- `total` mirrors the nested object returned by SnapTrade (amount + currency).
- `balances` should reference the `Balance` entity defined in SOT for per-currency details.

## Example JSON
```json
{
  "total": { "amount": 15363.23, "currency": "USD" },
  "balances": [
    { "currency": { "id": "87b2...", "code": "USD", "name": "United States Dollar" }, "cash": 300.71 },
    { "currency": { "id": "a1b2...", "code": "CAD", "name": "Canadian Dollar" }, "cash": 1000.00 }
  ]
}
```

## Backlinks & Code references
- SnapTrade API: `references/snaptrade-sdk/api.yaml#/components/schemas/AccountBalance`
- Domain model: `markbot/src/markbot/domain/models.py` (AccountBalance)
- Canvas: `projects/finance-apps/canvas/domain-model.canvas`
