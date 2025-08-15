---
tags: [template, model, domain]
template: entity
entity: "MlegLeg"
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

# MlegLeg

A single leg in a multi-leg options/equity order.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    instrument:
      type: MlegTradingInstrument
      description: "Instrument for the leg (option or equity)."
    action:
      type: MlegActionStrict
      description: "Leg action (BUY, SELL, BUY_TO_OPEN, etc)."
    units:
      type: integer
      description: "Quantity for the leg (contracts for options, shares for equity)."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Source: OpenAPI references/snaptrade-sdk/api.yaml schema `MlegLeg`.
- Usage: used by multi-leg option order request/response models (MlegTradeForm, MlegOrderResponse).

## Example JSON
```json
{
  "instrument": { "symbol": "AAPL  261218C00240000", "instrument_type": "OPTION" },
  "action": "BUY_TO_OPEN",
  "units": 1
}
```

## Backlinks
- API schema: references/snaptrade-sdk/api.yaml (MlegLeg)
- Domain model: markbot/src/markbot/domain/models.py
