---
tags: [template, model, domain]
template: entity
entity: "BrokerageAuthorizationDisabledConfirmation"
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

# BrokerageAuthorizationDisabledConfirmation

Confirmation that the connection has been disabled.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    detail:
      type: string
      description: "Connection disabled confirmation."
    disabled:
      type: boolean
      description: "Whether the brokerage authorization is disabled or not."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: returned after disabling a brokerage authorization; useful for UI feedback and audit logs.

## Example JSON
```json
{
  "detail": "Connection disabled",
  "disabled": true
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (BrokerageAuthorizationDisabledConfirmation)
- Canvas: projects/finance-apps/canvas/domain-model.canvas