---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/PaginationDetails
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# PaginationDetails (Schema)

Canonical YAML fragment (extracted from API):

```yaml
PaginationDetails:
  description: Details about the pagination of the results.
  type: object
  properties:
    offset:
      type: integer
      example: 0
      description: The starting point of the paginated results.
    limit:
      type: integer
      example: 100
      description: The maximum number of items to return in the response.
    total:
      type: integer
      example: 1000
      description: The total number of items available to be returned over the API.
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/PaginationDetails

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (PaginationDetails)
