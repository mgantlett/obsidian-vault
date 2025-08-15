---
tags: [template, model,domain]
template: entity
entity: "Candle"
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

# Candle

Represents a single candle in a time series.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    universal_symbol_id:
      type: string
      description: "The universal symbol ID of the security."
    symbol:
      type: string | null
      description: "The ticker symbol (e.g., 'AAPL')."
    description:
      type: string | null
      description: "Human-readable description of the security."
    timestamp:
      type: string
      description: "The timestamp of the candle."
    open:
      type: number
      description: "The opening price of the candle."
    high:
      type: number
      description: "The highest price of the candle."
    low:
      type: number
      description: "The lowest price of the candle."
    close:
      type: number
      description: "The closing price of the candle."
    volume:
      type: integer
      description: "The trading volume of the candle."
  cache_ttl: 3600
  meta:
    owner: domain
    version: 1
```

## Notes
- Mirrors `Candle` in `markbot/src/markbot/domain/models.py`.

## Example JSON
```json
{ "universal_symbol_id": "usym-1", "symbol": "AAPL", "timestamp": "2024-01-02T09:30:00Z", "open": 150.0, "high": 152.0, "low": 149.5, "close": 151.0, "volume": 120000 }
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- Canvas: projects/finance-apps/canvas/domain-model.canvas
