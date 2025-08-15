---
tags: [template, model, domain]
template: entity
entity: "PartnerData"
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

# PartnerData

Configurations for your SnapTrade Client ID, including allowed brokerages and data access.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    name:
      type: string
      description: "Your company or product name."
    slug:
      type: string
      description: "A short, unique identifier for your company or product."
    logo_url:
      type: string
      description: "URL to your company or product logo."
    pin_required:
      type: boolean
      description: "Shows if pin is required by users to access connection page."
    can_access_trades:
      type: boolean
      description: "Whether trading is enabled for your SnapTrade Client ID."
    can_access_holdings:
      type: boolean
      description: "Whether holdings data is enabled for your SnapTrade Client ID."
    can_access_account_history:
      type: boolean
      description: "Whether account historical transactions is enabled for your SnapTrade Client ID."
    can_access_portfolio_management:
      type: boolean
      description: "Whether portfolio management is enabled for your SnapTrade Client ID."
    can_access_orders:
      type: boolean
      description: "Whether recent order history is enabled for your SnapTrade Client ID."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: partner-level capability flags and branding used during onboarding and UI flows.
- Validation: boolean flags control feature availability for the partner.

## Example JSON
```json
{
  "name": "Acme Finance",
  "slug": "ACME",
  "logo_url": "https://acme.example/logo.png",
  "pin_required": false,
  "can_access_trades": true,
  "can_access_holdings": true,
  "can_access_account_history": true,
  "can_access_portfolio_management": false,
  "can_access_orders": true
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (PartnerData)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
