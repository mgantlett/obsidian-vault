---
tags: [template, model, domain]
template: entity
entity: "SymbolsQuotes"
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

# SymbolsQuotes

Represents real-time market quotes for a symbol.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    symbol:
      type: UniversalSymbol
      description: "The symbol for which the quote is."
    bid_price:
      type: number | null
      description: "Current bid price."
    ask_price:
      type: number | null
      description: "Current ask price."
    last_trade_price:
      type: number | null
      description: "Last traded price."
    last_trade_size:
      type: number | null
      description: "Size of the last trade."
    last_trade_tick:
      type: string | null
      description: "Tick direction of the last trade."
    last_trade_time:
      type: string | null
      description: "Timestamp of the last trade."
    volume:
      type: integer | null
      description: "Trading volume for the day."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: provide market data to UI components, alerts, and valuation pipelines.
- Validation: numeric fields may be null when quote data is unavailable.

## Example JSON
```json
{
  "symbol": { "id": "...", "symbol": "AAPL", "exchange": { "code": "NASDAQ" } },
  "bid_price": 174.25,
  "ask_price": 174.30,
  "last_trade_price": 174.28,
  "last_trade_size": 100,
  "last_trade_tick": "+",
  "last_trade_time": "2025-08-14T09:30:00Z",
  "volume": 1200000
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (SymbolsQuotes)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
