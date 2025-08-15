---
tags: [template, model, domain]
template: entity
entity: "Brokerage"
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

# Brokerage

Describes a brokerage that SnapTrade supports.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      description: "Unique identifier for the brokerage firm. This is the UUID used to reference the brokerage in SnapTrade."
    name:
      type: string
      description: "Full name of the brokerage."
    display_name:
      type: string
      description: "A display-friendly name of the brokerage."
    description:
      type: string | null
      description: "A brief description of the brokerage."
    logo_url:
      type: string
      description: "URL to the brokerage's logo."
    slug:
      type: string
      description: "A short, unique identifier for the brokerage. It is usually the name of the brokerage in capital letters and will never change."
    url:
      type: string | null
      description: "URL to the brokerage's website."
    enabled:
      type: boolean
      description: "Whether the brokerage is enabled in SnapTrade. A disabled brokerage will not be available for new connections."
    maintenance_mode:
      type: boolean
      description: "Whether the brokerage is currently in maintenance mode. A brokerage in maintenance mode will not be available for new connections."
    allows_real_time_connections:
      type: boolean | null
      description: "Whether the brokerage allows real-time connections or not."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: describes broker-specific metadata used during onboarding, UI rendering and capability checks.
- Validation: `slug` is stable; `enabled`/`maintenance_mode` control availability.

## Example JSON
```json
{
  "id": "brk-1234-abcdef",
  "name": "Example Brokerage Inc.",
  "display_name": "Example Brokerage",
  "description": "Full-service brokerage",
  "logo_url": "https://example.com/logo.png",
  "slug": "EXAMPLE",
  "url": "https://example.com",
  "enabled": true,
  "maintenance_mode": false,
  "allows_real_time_connections": true
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (Brokerage)
- Canvas: projects/finance-apps/canvas/domain-model.canvas