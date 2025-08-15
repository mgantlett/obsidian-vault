---
tags: [template, model, domain]
template: entity
entity: "BrokerageInstrument"
source: references/snaptrade-sdk/api.yaml
owner: reference
status: draft
cache_ttl: 3600
version: 1
migration_state: synced-from-api
sensitive: false
generated_paths: []
tests: []
examples: []
---

# BrokerageInstrument

Represents an instrument as defined by a brokerage (SnapTrade schema: BrokerageInstrument).

## SOT (YAML fragment)
```yaml
sot:
  fields:
    symbol:
      type: string
      description: "The instrument's trading symbol / ticker."
    exchange_mic:
      type: string | null
      description: "MIC code of the exchange where the instrument is traded."
    tradeable:
      type: boolean | null
      description: "Whether the instrument is tradeable through the brokerage."
    fractionable:
      type: boolean | null
      description: "Whether fractional units are supported for this instrument."
    universal_symbol_id:
      type: string | null
      description: "Universal symbol UUID used in SnapTrade API calls."
  cache_ttl: 3600
  meta:
    source: references/snaptrade-sdk/api.yaml#/components/schemas/BrokerageInstrument
    owner: reference
    version: 1
```

## Notes
- Synced from SnapTrade OpenAPI components.schemas.BrokerageInstrument.
- Use `universal_symbol_id` to link to the project's `UniversalSymbol` entity when available.

## Example JSON
```json
{
  "symbol": "AAPL",
  "exchange_mic": "XNAS",
  "tradeable": true,
  "fractionable": true,
  "universal_symbol_id": "2bcd7cc3-e922-4976-bce1-9858296801c3"
}
```

## Backlinks & Code references
- SnapTrade API: `references/snaptrade-sdk/api.yaml` (components.schemas.BrokerageInstrument)
- Domain models: `markbot/src/markbot/domain/models.py`
- Canvas: `projects/finance-apps/canvas/domain-model.canvas`
