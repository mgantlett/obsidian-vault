---
tags: [template, model, domain]
template: entity
entity: "AccountSimple"
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

# AccountSimple

A lightweight representation of a single account at a brokerage.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      description: "Unique identifier for the connected brokerage account."
    name:
      type: string | null
      description: "A display name for the account."
    number:
      type: string
      description: "The account number assigned by the brokerage."
    sync_status:
      type: AccountSyncStatus | null
      description: "Contains status update for the account sync process between SnapTrade and the brokerage."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: use in lists and lightweight endpoints where full Account payload is unnecessary.
- Relationships: references `AccountSyncStatus` when available.

## Example JSON
```json
{
  "id": "acc-1234-5678",
  "name": "Main Trading Account",
  "number": "12345678",
  "sync_status": { "transactions": {"status":"complete"}, "holdings": {"status":"complete"} }
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (AccountSimple)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
