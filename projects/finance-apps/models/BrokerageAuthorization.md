---
tags: [template, model, domain]
template: entity
entity: "BrokerageAuthorization"
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

# BrokerageAuthorization

A single connection with a brokerage.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      description: "Unique identifier for the connection. This is the UUID used to reference the connection in SnapTrade."
    created:
      type: string
      description: "Timestamp of when the connection was established in SnapTrade."
    updated:
      type: string
      description: "Timestamp of when the connection was last updated in SnapTrade."
    brokerage:
      type: Brokerage
      description: "The brokerage associated with the authorization."
    name:
      type: string | null
      description: "A short, human-readable name for the connection."
    type:
      type: string
      description: "Whether the connection is read-only or trade-enabled."
    disabled:
      type: boolean
      description: "Whether the connection is disabled."
    disabled_date:
      type: string | null
      description: "Timestamp of when the connection was disabled in SnapTrade."
    meta:
      type: object
      description: "Additional data about the connection."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: represents an authenticated connection to a brokerage for a user.
- Validation: `id`, `created`, and `brokerage` should be present; `meta` may contain provider-specific details.

## Example JSON
```json
{
  "id": "auth-abcdef-123456",
  "created": "2025-01-10T12:34:56Z",
  "updated": "2025-07-01T08:00:00Z",
  "brokerage": { "id": "brk-1234-abcdef", "name": "Example Brokerage" },
  "name": "Primary Connection",
  "type": "trade-enabled",
  "disabled": false,
  "disabled_date": null,
  "meta": {}
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (BrokerageAuthorization)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
