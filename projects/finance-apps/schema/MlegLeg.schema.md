---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/MlegLeg
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# MlegLeg (Schema)

Canonical YAML fragment (extracted from API):

```yaml
MlegLeg:
  type: object
  required:
    - "instrument"
    - "action"
    - "units"
  properties:
    instrument:
      $ref: "#/components/schemas/MlegTradingInstrument"
    action:
      $ref: "#/components/schemas/MlegActionStrict"
    units:
      description: The quantity to trade. For options this represents the number of contracts. For equity this represents the number of shares.
      type: integer
      example: 1
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/MlegLeg

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (MlegLeg)
