---
tags: [template, model, domain]
template: entity
entity: "Balance"
source: markbot/src/markbot/domain/models.py
owner: infra
status: draft
cache_ttl: 3600
version: 1
migration_state: draft
sensitive: false
generated_paths: []
tests: []
examples: []
---

# Balance

Purpose: Holds balance information for a single currency in an account.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    currency:
      type: Currency
      description: "The currency of the balance."
    cash:
      type: float
      description: "The amount of available cash in the account denominated in the currency of the `currency` field."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: represents cash balances per currency within an account.
- Relationships: nested `Currency` object providing `code` and `name`.
- Validation: `cash` is a numeric amount, typically >= 0; currency must reference a valid `Currency`.

## Example JSON
```json
{
  "currency": {
    "id": "f3a1b2c4-1234-4d5e-9a1b-0c2d3e4f5a6b",
    "code": "USD",
    "name": "United States Dollar"
  },
  "cash": 1234.56
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (Balance)
- Canvas: projects/finance-apps/canvas/domain-model.canvas