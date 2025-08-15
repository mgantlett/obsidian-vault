---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/AccountOrderRecordStatus
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# AccountOrderRecordStatus (Schema)

Canonical YAML fragment (extracted from API):

```yaml
AccountOrderRecordStatus:
  description: Indicates the status of an order. SnapTrade does a best effort to map brokerage statuses to statuses in this enum.
  type: string
  enum:
    - NONE
    - PENDING
    - ACCEPTED
    - FAILED
    - REJECTED
    - CANCELED
    - PARTIAL_CANCELED
    - CANCEL_PENDING
    - EXECUTED
    - PARTIAL
    - REPLACE_PENDING
    - REPLACED
    - STOPPED
    - SUSPENDED
    - EXPIRED
    - QUEUED
    - TRIGGERED
    - ACTIVATED
    - PENDING_RISK_REVIEW
    - CONTINGENT_ORDER
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/AccountOrderRecordStatus

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (AccountOrderRecordStatus)
