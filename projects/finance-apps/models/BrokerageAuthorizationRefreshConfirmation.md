---
tags: [template, model, domain]
template: entity
entity: "BrokerageAuthorizationRefreshConfirmation"
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

# BrokerageAuthorizationRefreshConfirmation

Confirmation that the syncs have been scheduled.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    detail:
      type: string
      description: "Refresh confirmation details."
    import_id:
      type: string
      description: "The import ID of the refresh."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: returned after scheduling a refresh for a brokerage authorization.
- Validation: `import_id` is typically a UUID or unique operation id.

## Example JSON
```json
{
  "detail": "Refresh scheduled",
  "import_id": "import-abcdef-123456"
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (BrokerageAuthorizationRefreshConfirmation)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
