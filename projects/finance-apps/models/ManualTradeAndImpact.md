---
tags: [template, model, domain]
template: entity
entity: "ManualTradeAndImpact"
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

# ManualTradeAndImpact

Represents a manual trade and its impact on the account.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    trade:
      type: ManualTrade
      description: "The details of the manual trade."
    trade_impacts:
      type: list[ManualTradeImpact]
      description: "The financial impacts of the trade."
    combined_remaining_balance:
      type: ManualTradeBalance
      description: "The remaining balance after the trade."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: returned by the trade impact simulation endpoint to show both the trade object and the estimated impacts across affected accounts.
- Relationships: composes ManualTrade, ManualTradeImpact and ManualTradeBalance.

## Example JSON
```json
{
  "trade": { "id": "trade-123", "account": "acc-1234", "order_type": "Market", "time_in_force": "GTC", "symbol": { "universal_symbol_id": "..." }, "action": "BUY", "units": 10 },
  "trade_impacts": [ { "account": "acc-1234", "currency": "USD", "remaining_cash": 10000.0, "estimated_commission": 1.25 } ],
  "combined_remaining_balance": { "account": { "id": "acc-1234", "name": "Main" }, "currency": { "code": "USD" }, "cash": 10000.0 }
}
```

## Backlinks & Code references
- API schema: references/snaptrade-sdk/api.yaml (ManualTradeAndImpact)
- Domain model: markbot/src/markbot/domain/models.py
