---
tags: [template, model, domain]
template: entity
entity: "AccountSyncStatus"
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

# AccountSyncStatus

Contains status update for the account sync process between SnapTrade and the brokerage.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    transactions:
      type: object | null
      description: "Status of account transaction sync."
    holdings:
      type: object | null
      description: "Status of account holdings sync."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: surface per-account sync progress, errors and timestamps for diagnostics and UI.
- Validation: fields typically contain status maps (e.g., {"last_sync": "2025-08-14T...", "status": "complete"}).

## Example JSON
```json
{
  "transactions": { "last_sync": "2025-08-14T09:30:00Z", "status": "complete" },
  "holdings": { "last_sync": "2025-08-14T09:31:00Z", "status": "in_progress" }
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (AccountSyncStatus)
- Canvas: projects/finance-apps/canvas/domain-model.canvas