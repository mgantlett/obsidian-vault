---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/SecurityType
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# SecurityType (Schema)

Canonical YAML fragment (extracted from API):

```yaml
SecurityType:
  type: object
  description: The type of security. For example, "Common Stock" or "ETF".
  properties:
    id:
      $ref: "#/components/schemas/SecurityTypeID"
    code:
      description: |
        A short code representing the security type. For example, "cs" for Common Stock. Here are some common values:
          - `ad` - ADR
          - `bnd` - Bond
          - `cs` - Common Stock
          - `cef` - Closed End Fund
          - `crypto` - Cryptocurrency
          - `et` - ETF
          - `oef` - Open Ended Fund
          - `ps` - Preferred Stock
          - `rt` - Right
          - `struct` - Structured Product
          - `ut` - Unit
          - `wi` - When Issued
          - `wt` - Warrant
      type: string
      example: cs
    description:
      description: A human-readable description of the security type. For example, "Common Stock" or "ETF".
      type: string
      example: Common Stock
    is_supported:
      deprecated: true
      description: This field is deprecated and should not be used. Please reach out to SnapTrade support if you have a valid usecase for this.
      type: boolean
      example: true
Time:
  description: Time
  type: string
  example: 2022-01-21T15:11:19.217000-05:00
BrokerageType:
  description: Type of brokerage. Currently supports traditional brokerages and crypto exchanges.
  type: object
  properties:
    id:
      $ref: "#/components/schemas/Id"
    name:
      type: string
      example: Traditional Brokerage
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/SecurityType

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (SecurityType)
