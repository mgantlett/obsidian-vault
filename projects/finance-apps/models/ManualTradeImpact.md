---
tags: [template, model, domain]
template: entity
entity: "ManualTradeImpact"
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

# ManualTradeImpact

Impact of a trade on an account.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    account:
      type: string
      description: "The account ID that the trade was placed in."
    currency:
      type: string
      description: "The currency of the trade."
    remaining_cash:
      type: number | null
      description: "Estimated amount of cash remaining in the account after the trade."
    estimated_commission:
      type: number | null
      description: "Estimated commission for the trade."
    forex_fees:
      type: number | null
      description: "Estimated foreign transaction fees for the trade."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: preview endpoints return this to show estimated account-level impacts of a manual trade.

## Example JSON
```json
{
  "account": "acc-1234-5678",
  "currency": "USD",
  "remaining_cash": 10000.0,
  "estimated_commission": 1.25,
  "forex_fees": 0.0
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (ManualTradeImpact)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
