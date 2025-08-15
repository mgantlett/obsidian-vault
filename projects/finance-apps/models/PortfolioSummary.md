---
tags: [template, model, domain]
template: entity
entity: "PortfolioSummary"
source: markbot/src/markbot/domain/models.py
owner: domain
status: draft
cache_ttl: 3600
version: 1
migration_state: draft
sensitive: false
generated_paths: []
tests: []
examples: []
---

# PortfolioSummary

Portfolio summary information including cash, holdings, and P&L.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    total_equity:
      type: number
      description: "Total equity across all accounts"
    total_cash:
      type: number
      description: "Total cash across all accounts"
    total_holdings_value:
      type: number
      description: "Total value of all holdings"
    total_pnl:
      type: number
      description: "Total profit/loss"
    total_pnl_percent:
      type: number
      description: "Total profit/loss percentage"
    currency:
      type: string
      description: "Currency of the portfolio values"
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `PortfolioSummary` in `markbot/src/markbot/domain/models.py`.

## Example JSON
```json
{ "total_equity": 100000.0, "total_cash": 5000.0, "total_holdings_value": 95000.0, "total_pnl": 2000.0, "total_pnl_percent": 2.04, "currency": "USD" }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- Canvas: projects/finance-apps/canvas/domain-model.canvas
