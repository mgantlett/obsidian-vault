---
tags: [template, model, domain]
template: entity
entity: "MlegTradingInstrument"
source: references/snaptrade-sdk/api.yaml
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

# MlegTradingInstrument

Instrument definition used for multi-leg orders (option or equity).

## SOT (YAML fragment)
```yaml
sot:
  fields:
    symbol:
      type: string
      description: "The trading ticker or OCC option symbol (21-char OCC format for options)."
    instrument_type:
      type: MlegInstrumentType
      description: "Type of instrument: OPTION or EQUITY."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Source: `references/snaptrade-sdk/api.yaml` schema `MlegTradingInstrument`.
- Usage: used by `MlegLeg` and multi-leg order forms.

## Example JSON
```json
{ "symbol": "AAPL  261218C00240000", "instrument_type": "OPTION" }
```

## Backlinks & Code references
- API schema: references/snaptrade-sdk/api.yaml (MlegTradingInstrument)
- Domain model: markbot/src/markbot/domain/models.py
- Canvas: projects/finance-apps/canvas/domain-model.canvas
