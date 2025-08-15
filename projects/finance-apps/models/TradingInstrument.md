---
tags: [template, model, domain]
template: entity
entity: "TradingInstrument"
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

# TradingInstrument

A trading instrument.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    symbol:
      type: UniversalSymbol
      description: "The symbol of the trading instrument."
    brokerage_id:
      type: string
      description: "The brokerage ID of the trading instrument."
    name:
      type: string
      description: "The name of the trading instrument."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: represents an instrument record tied to a brokerage listing and canonical universal symbol.
- Relationships: references `UniversalSymbol` and may be used in brokerage-specific mappings.

## Example JSON
```json
{
  "symbol": { "id": "...", "symbol": "AAPL", "exchange": { "code": "NASDAQ" } },
  "brokerage_id": "brk-instr-1234",
  "name": "Apple Inc."
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (TradingInstrument)
- Canvas: projects/finance-apps/canvas/domain-model.canvas