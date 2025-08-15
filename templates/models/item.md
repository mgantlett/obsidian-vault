---
tags: [template, model, domain]
template: entity
entity: "{{EntityName}}"
source: markbot/src/markbot/domain/models.py
owner: infra
status: draft
cache_ttl: 3600
version: 1
last_exported: null
migration_state: draft       # draft | in-progress | migrated
sensitive: false
generated_paths: []
tests: []
examples: []
---

# {{EntityName}}

Short one-line purpose / intent for this entity.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      primary_key: true
      description: "UUID"
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Used by frontend for display and by backtesting/caching layers.
- TTL: 24h — suitable for infrequent updates.
- Backlinks & generated artifacts listed in `generated_paths` frontmatter.

Additional guidance:
- Usage: which services / endpoints read/write this entity.
- Relationships: FK hints (field -> target), cardinality, and whether Canvas arrows override.
- Serialization: expected JSON shape, nullability, aliasing.
- Validation: important constraints and common error cases.
- Migration: migration steps, data backfill hints, and acceptance criteria for "migrated".
- Tests: unit/integration test names that should validate model parity.
- Security/privacy: any sensitive fields and retention rules.
- Change log: short history of model changes.

## Example JSON
```json
{
  "id": "example_id",
  "field1": "value"
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py`
- Generated code paths: `markbot/codegen/generated_models.py`, `spendviz/src/types/unified_models.ts`
- Canvas: projects/finance-apps/canvas/domain-model.canvas
