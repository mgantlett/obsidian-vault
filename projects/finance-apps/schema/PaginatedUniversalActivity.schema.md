---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/PaginatedUniversalActivity
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# PaginatedUniversalActivity (Schema)

Canonical YAML fragment (extracted from API):

```yaml
PaginatedUniversalActivity:
  description: A paginated list of UniversalActivity objects.
  type: object
  properties:
    data:
      type: array
      items:
        $ref: "#/components/schemas/AccountUniversalActivity"
    pagination:
      $ref: "#/components/schemas/PaginationDetails"
AccountUniversalActivity:
  description: A transaction or activity from an institution
  type: object
  properties:
    id:
      description: |
        Unique identifier for the transaction. This is the ID used to reference the transaction in SnapTrade.
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/PaginatedUniversalActivity

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (PaginatedUniversalActivity)
