---
tags: [template, model, reference]
template: entity
entity: "Account"
source: references/snaptrade-sdk/api.yaml
owner: reference
status: draft
cache_ttl: 3600
version: 1
migration_state: synced-from-api
sensitive: false
generated_paths: []
tests: []
examples: []
---

# Account

Mirrors SnapTrade `components.schemas.Account`.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      description: "Unique identifier for the connected brokerage account (UUID)."
    brokerage_authorization:
      type: string
      description: "Brokerage authorization UUID."
    name:
      type: string | null
      description: "Display name for the account."
    number:
      type: string
      description: "Account number assigned by the brokerage."
    institution_name:
      type: string
      description: "Name of the brokerage that holds the account."
    created_date:
      type: string
      format: date-time
      description: "ISO 8601 timestamp for when the account was created in SnapTrade."
    sync_status:
      type: AccountSyncStatus
      description: "Contains status update for the account sync process between SnapTrade and the brokerage."
    balance:
      type: AccountBalance
      description: "Contains balance related information for the account (per-currency balances)."
    status:
      type: string | null
      enum: [open, closed, archived]
      description: "The current status of the account as reported by the brokerage."
    raw_type:
      type: string | null
      description: "The raw account type value provided by the brokerage (may be deprecated)."
    meta:
      type: object | null
      description: "Deprecated brokerage-specific metadata."
    portfolio_group:
      type: string | null
      description: "Portfolio Group ID (deprecated)."
    cash_restrictions:
      type: array | null
      description: "Deprecated cash restrictions."
  cache_ttl: 3600
  meta:
    source: references/snaptrade-sdk/api.yaml#/components/schemas/Account
    owner: reference
    version: 1
```

## Notes
- Synced from SnapTrade OpenAPI `Account` schema.
- Use `brokerage_authorization` to join to `BrokerageAuthorization` and `id` to join to internal account records.

## Example JSON
```json
{
  "id": "917c8734-8470-4a3e-a18f-57c3f2ee6631",
  "brokerage_authorization": "87b24961-b51e-4db8-9226-f198f6518a89",
  "name": "Robinhood Individual",
  "number": "Q6542138443",
  "institution_name": "Robinhood",
  "created_date": "2024-07-23T22:50:22.761390Z",
  "sync_status": {},
  "balance": {},
  "status": "open",
  "raw_type": "Margin"
}
```

## Backlinks & Code references
- SnapTrade API: `references/snaptrade-sdk/api.yaml#/components/schemas/Account`
- Domain model: `markbot/src/markbot/domain/models.py` (Account)
- Canvas: `projects/finance-apps/canvas/domain-model.canvas`
