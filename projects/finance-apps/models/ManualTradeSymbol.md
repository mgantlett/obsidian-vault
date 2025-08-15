---
tags: [template, model, domain]
template: entity
entity: "ManualTradeSymbol"
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

# ManualTradeSymbol

Information about the security for the order.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    universal_symbol_id:
      type: string
      description: "The universal symbol ID of the security to trade."
    currency:
      type: Currency
      description: "The currency of the security."
    local_id:
      type: string | null
      description: "The local ID of the security."
    description:
      type: string | null
      description: "A description of the security."
    symbol:
      type: string | null
      description: "The security's trading ticker symbol."
    brokerage_symbol_id:
      type: string | null
      description: "The brokerage-specific symbol for the security."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: used in manual trade submissions to identify the instrument when placing orders.
- Relationships: may reference `UniversalSymbol` by ID and include `Currency` details.

## Example JSON
```json
{
  "universal_symbol_id": "8b7c6d5e-0000-1111-2222-333344445555",
  "currency": { "id": "f3a1b2c4-1234-4d5e-9a1b-0c2d3e4f5a6b", "code": "USD" },
  "local_id": "LOCAL-12345",
  "description": "Apple Inc. common stock",
  "symbol": "AAPL",
  "brokerage_symbol_id": "BRK-AAPL-001"
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (ManualTradeSymbol)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
