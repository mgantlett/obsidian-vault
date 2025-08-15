---
tags: [schema, domain, account]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/Account
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# Account (Schema)

Canonical YAML schema for the Account entity (source: SnapTrade OpenAPI).

```yaml
title: Account
description: "Mirrors SnapTrade Account schema"
properties:
  id:
    type: string
    description: "Unique identifier for the connected brokerage account (UUID)."
  brokerage_authorization:
    type: string
    description: "Brokerage authorization UUID."
  name:
    type: [string, null]
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
    $ref: '#/components/schemas/AccountSyncStatus'
    description: "Contains status update for the account sync process between SnapTrade and the brokerage."
  balance:
    $ref: '#/components/schemas/AccountBalance'
    description: "Contains balance related information for the account (per-currency balances)."
  status:
    type: [string, null]
    enum: [open, closed, archived]
    description: "The current status of the account as reported by the brokerage."
  raw_type:
    type: [string, null]
    description: "The raw account type value provided by the brokerage (may be deprecated)."
  meta:
    type: [object, null]
    description: "Deprecated brokerage-specific metadata."
  portfolio_group:
    type: [string, null]
    description: "Portfolio Group ID (deprecated)."
  cash_restrictions:
    type: [array, null]
    description: "Deprecated cash restrictions."
required: [id]
redis_indexes:
  - name: account_by_auth
    fields: [brokerage_authorization]
    type: tag

cache_ttl: 3600
```

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

## Notes
- Synced from SnapTrade OpenAPI `Account` schema.
- Use `brokerage_authorization` to join to `BrokerageAuthorization` and `id` to join to internal account records.

## Backlinks & Code references
- SnapTrade API: references/snaptrade-sdk/api.yaml#/components/schemas/Account
- Domain model: markbot/src/markbot/domain/models.py (Account)
