---
tags: [template, model, domain]
template: entity
entity: "PositionSymbol"
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

# PositionSymbol

Uniquely describes a security for the position within an account.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    symbol:
      type: UniversalSymbol
      description: "The universal symbol for the security."
    id:
      type: string
      primary_key: true
      description: "The brokerage-specific symbol for the security."
    description:
      type: string
      description: "A description of the security."
    local_id:
      type: string | null
      description: "The local ID of the security."
    is_quotable:
      type: boolean | null
      description: "Whether the security is quotable."
    is_tradable:
      type: boolean | null
      description: "Whether the security is tradable."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: used by portfolio/position representations and order placement logic.
- Relationships: contains `UniversalSymbol` and links to `Position` entities.
- Validation: `symbol` should resolve to an existing `UniversalSymbol` and `is_tradable` should be validated against brokerage capabilities.

## Example JSON
```json
{
  "id": "c0ffee00-aaaa-1111-2222-333344445555",
  "symbol": {
    "id": "8b7c6d5e-0000-1111-2222-333344445555",
    "symbol": "AAPL",
    "exchange": { "code": "NASDAQ" }
  },
  "description": "Position-level symbol for long AAPL holding",
  "local_id": "LOCAL-12345",
  "is_quotable": true,
  "is_tradable": true
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (PositionSymbol)
- Canvas: projects/finance-apps/canvas/domain-model.canvas