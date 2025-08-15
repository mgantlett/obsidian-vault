---
tags: [template, model, domain]
template: entity
entity: "ManualTradeBalance"
source: references/snaptrade-sdk/api.yaml
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

# ManualTradeBalance

Estimated remaining balance of the account after the trade is executed.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    account:
      type: AccountSimple
      description: "The account that the trade was placed in."
    currency:
      type: Currency
      description: "The currency of the trade."
    cash:
      type: number | null
      description: "Estimated amount of cash remaining in the account after the trade. At the moment this is the same as `remaining_cash` under `trade_impacts`."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Example JSON
```json
{
  "account": { "id": "acc-1234-5678", "name": "Main Trading Account" },
  "currency": { "id": "f3a1b2c4-...", "code": "USD", "name": "United States Dollar" },
  "cash": 10000.00
}
```

## Backlinks & Code references
- API schema: references/snaptrade-sdk/api.yaml (ManualTradeBalance)
- Domain model: markbot/src/markbot/domain/models.py
