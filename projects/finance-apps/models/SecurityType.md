---
tags: [template, model, domain]
template: entity
entity: "SecurityType"
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

# SecurityType

The type of security. For example, 'Common Stock' or 'ETF'.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      description: "Unique identifier for the security type within SnapTrade."
    name:
      type: string
      description: "A human-readable description of the security type."
    description:
      type: string
      description: "A short code representing the security type."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: classify instruments and drive UI labels, filters and allowed order types.

## Example JSON
```json
{
  "id": "sec-1234",
  "name": "Common Stock",
  "description": "CS"
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (SecurityType)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
