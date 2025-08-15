---
tags: [template, model, domain]
template: entity
entity: "User"
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

# User

Represents a user's credentials.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    userId:
      type: string
      description: "SnapTrade User ID. This is chosen by the API partner and can be any string that is a) unique to the user, and b) immutable for the user."
    userSecret:
      type: string
      description: "SnapTrade User Secret. This is a randomly generated string and should be stored securely."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: used for authentication/identification of partner users within SnapTrade integrations.
- Validation: `userId` must be unique and stable; `userSecret` should be handled securely and not exposed.

## Example JSON
```json
{
  "userId": "partner-user-123",
  "userSecret": "s3cr3t-token-abcdef"
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (User)
- Canvas: projects/finance-apps/canvas/domain-model.canvas