---
tags: [template, model, domain]
template: entity
entity: "PerformanceCustom"
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

# PerformanceCustom

Performance Custom Response Object

## SOT (YAML fragment)
```yaml
sot:
  fields:
    total_equity_timeframe:
      type: list[object]
      description: "A list of historical equity values for the account."
    contributions:
      type: float
      description: "Total contributions made to the account in the timeframe."
    contribution_timeframe:
      type: list[object]
      description: "A list of historical contribution values for the account."
    withdrawal_timeframe:
      type: list[object]
      description: "A list of historical withdrawal values for the account."
    contribution_streak:
      type: int | null
      description: "Current streak of consecutive months where contributions were made."
    contribution_months_contributed:
      type: int | null
      description: "Number of months in the timeframe with contributions."
    contribution_total_months:
      type: int | null
      description: "Total months in timeframe."
    dividends:
      type: float | null
      description: "Total dividends received over the timeframe."
    dividend_income_timeframe:
      type: list[object]
      description: "A list of historical dividend income values for the account."
    monthly_dividends:
      type: float | null
      description: "Average dividends received per month over the timeframe."
    bad_tickers:
      type: list[string]
      description: "list of tickers which may not be supported or may not have accurate price data."
    dividend_yield:
      type: float | null
      description: "The dividend yield of the account."
    earnings:
      type: float | null
      description: "Total earnings in the account."
    e_per_share:
      type: float | null
      description: "Earnings per share."
    p_e_ratio:
      type: float | null
      description: "Price to earnings ratio."
    passive_income:
      type: float | null
      description: "Passive income in the account."
    rate_of_return:
      type: float | null
      description: "The return rate over the timeframe."
    return_on_investment:
      type: float | null
      description: "Return on investment."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: detailed custom performance response for analytics and reporting endpoints.
- Validation: timeframe arrays must be chronological and numeric values valid floats.

## Example JSON
```json
{
  "total_equity_timeframe": [],
  "contributions": 1000.0,
  "contribution_timeframe": [],
  "withdrawal_timeframe": [],
  "contribution_streak": 3,
  "contribution_months_contributed": 3,
  "contribution_total_months": 12,
  "dividends": 50.0,
  "dividend_income_timeframe": [],
  "monthly_dividends": 4.17,
  "bad_tickers": ["XYZ"],
  "dividend_yield": 0.02,
  "earnings": 200.0,
  "e_per_share": 2.5,
  "p_e_ratio": 15.0,
  "passive_income": 100.0,
  "rate_of_return": 0.12,
  "return_on_investment": 0.12
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (PerformanceCustom)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
