---
tags: [template, model, domain]
template: entity
entity: "Exchange"
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

# Exchange

Purpose: Represents a trading/exchange venue (MIC, timezone, trading hours).

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      primary_key: true
      description: "UUID for the exchange"
    code:
      type: string
      description: "Short code used internally (e.g., NYSE)"
    mic_code:
      type: string | null
      description: "Market Identifier Code (MIC) where available"
    name:
      type: string
      description: "Full name of the exchange"
    timezone:
      type: string | null
      description: "IANA timezone for trading hours (e.g., America/New_York)"
    start_time:
      type: string | null
      description: "Local trading session open time (HH:MM)"
    close_time:
      type: string | null
      description: "Local trading session close time (HH:MM)"
    suffix:
      type: string | null
      description: "Optional symbol suffix used by some data providers"
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: used by symbol resolution, market hours, and display logic.
- Relationships: referenced by `UniversalSymbol.exchange`.
- Migration: verify MIC/code mappings against external provider data.

## Example JSON
```json
{
  "id": "e1d2c3b4-1111-2222-3333-444455556666",
  "code": "NYSE",
  "mic_code": "XNYS",
  "name": "New York Stock Exchange",
  "timezone": "America/New_York",
  "start_time": "09:30",
  "close_time": "16:00",
  "suffix": null
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- Canvas: projects/finance-apps/canvas/domain-model.canvas