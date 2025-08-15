---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/WebhookBase
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# WebhookBase (Schema)

Canonical YAML fragment (extracted from API):

```yaml
WebhookBase:
  description: The base webhook content
  type: object
  properties:
    webookId:
      type: string
      example: 06fe1fd7-fc50-43a7-b564-8a2c5f3bab44
    clientId:
      type: string
      example: WEALTHYCHIPMUNK
    eventTimestamp:
      type: string
      example: 2022-01-21T15:11:19.217000-05:00
    userId:
      type: string
      example: external_user@test.com
encryptedResponse:
  description: >
    This response consists of 2 different components that must be
    decrypted to obtain the decrypted message
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/WebhookBase

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (WebhookBase)
