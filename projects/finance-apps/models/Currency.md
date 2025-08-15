---
tags: [template, model, domain]
template: entity
entity: "Currency"
source: markbot/src/markbot/domain/models.py
owner: infra
status: draft
cache_ttl: 3600
version: 1
last_exported: null
migration_state: draft
sensitive: false
generated_paths: []
tests: []
examples: []
---

# Currency

Short one-line purpose / intent for this entity.
Represents a currency used for pricing, settlement and display across systems.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      primary_key: true
      description: "Unique identifier for the currency. This is the UUID used to reference the currency in SnapTrade."
    code:
      type: string
      description: "The ISO-4217 currency code for the currency."
    name:
      type: string
      description: "A human-friendly name of the currency."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: referenced by pricing, instruments and reporting layers.
- Relationships: referenced by `UniversalSymbol.currency` and account balances.
- Validation: `code` should follow ISO-4217 where possible.
- Migration: ensure mapping of legacy codes before switching.

## Example JSON
```json
{
  "id": "f3a1b2c4-1234-4d5e-9a1b-0c2d3e4f5a6b",
  "code": "USD",
  "name": "United States Dollar"
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (Currency)