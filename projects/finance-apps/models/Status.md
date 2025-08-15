---
tags: [template, model, domain]
template: entity
entity: "Status"
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

# Status

Status of API.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    timestamp:
      type: string
      description: "The timestamp of the status check."
    online:
      type: boolean
      description: "Whether the API is online or not."
    status:
      type: string | null
      description: "The status message."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: health checks and monitoring dashboards.
- Validation: `timestamp` should be ISO-8601.

## Example JSON
```json
{
  "timestamp": "2025-08-14T09:30:00Z",
  "online": true,
  "status": "ok"
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (Status)
- Canvas: projects/finance-apps/canvas/domain-model.canvas