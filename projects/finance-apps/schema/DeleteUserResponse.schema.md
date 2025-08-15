---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/DeleteUserResponse
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# DeleteUserResponse (Schema)

Canonical YAML fragment (extracted from API):

```yaml
DeleteUserResponse:
  type: object
  properties:
    status:
      description: This is always `deleted` when a user is queued for deletion.
      type: string
      example: deleted
    detail:
      description: Human friendly message about the deletion status.
      type: string
      example: User queued for deletion; please wait for webhook for confirmation.
    userId:
      $ref: "#/components/schemas/UserID"
BrokerageAuthorizationTypeReadOnly:
  type: object
  properties:
    id:
      $ref: "#/components/schemas/Id"
    type:
      type: string
      enum:
        - read
        - trade
    auth_type:
      type: string
      enum:
        - OAUTH
        - SCRAPE
        - UNOFFICIAL_API
        - TOKEN
    brokerage:
      type: object
      properties:
        id:
          $ref: "#/components/schemas/Id"
        name:
          type: string
          example: Questrade
          description: Full name of the brokerage.
        slug:
          type: string
          example: QUESTRADE
          description:
            A unique identifier for that brokerage. It is usually the name of the brokerage in
            capital letters and will never change.
Brokerage:
  description: Describes a brokerage that SnapTrade supports.
  type: object
  properties:
    id:
      description: Unique identifier for the brokerage firm. This is the UUID used to reference the brokerage in SnapTrade.
      type: string
      format: uuid
      example: ebf91a5b-0920-4266-9e36-f6cfe8c40946
    slug:
      description: A short, unique identifier for the brokerage. It is usually the name of the brokerage in capital letters and will never change.
      type: string
      example: ROBINHOOD
    name:
      description: Full name of the brokerage.
      type: string
      example: Robinhood
    display_name:
      description: A display-friendly name of the brokerage.
      type: string
      example: Robinhood
    description:
      description: A brief description of the brokerage.
      type: string
      example: Robinhood is an American multinational financial services corporation based in Menlo Park, California.
    aws_s3_logo_url:
      description: URL to the brokerage's logo.
      type: string
      format: url
      example: https://passiv-brokerage-logos.s3.ca-central-1.amazonaws.com/robinhood-logo.png
    aws_s3_square_logo_url:
      description: URL to the brokerage's logo in square format.
      type: string
      format: url
      example: https://passiv-brokerage-logos.s3.ca-central-1.amazonaws.com/robinhood-logo-square.png
      nullable: true
    url:
      description: URL to the brokerage's website.
      type: string
      format: url
      example: https://robinhood.com
    enabled:
      description: Whether the brokerage is enabled in SnapTrade. A disabled brokerage will not be available for new connections.
      type: boolean
      example: true
    maintenance_mode:
      description: Whether the brokerage is currently in maintenance mode. A brokerage in maintenance mode will not be available for new connections.
      type: boolean
      example: true
    allows_trading:
      description: Whether the brokerage allows trading through SnapTrade.
      type: boolean
      nullable: true
      example: true
    allows_fractional_units:
      deprecated: true
      description: This field is deprecated. Please contact us if you have a valid use case for it.
      type: boolean
      nullable: true
      example: true
    has_reporting:
      deprecated: true
      description: This field is deprecated. Please contact us if you have a valid use case for it.
      type: boolean
      nullable: true
      example: true
    is_real_time_connection:
      deprecated: true
      description: This field is deprecated. Please contact us if you have a valid use case for it.
      type: boolean
      example: true
    brokerage_type:
      $ref: "#/components/schemas/BrokerageType"
    exchanges:
      deprecated: true
      description: This field is deprecated. Please contact us if you have a valid use case for it.
      type: array
      items: {}
      example:
        - 2bcd7cc3-e922-4976-bce1-9858296801c3
        - 4bcd8cc3-c122-4974-dc21-1858296801f4
    open_url:
      deprecated: true
      description: This field is deprecated.
      type: string
      format: url
      nullable: true
BrokerageAuthorization:
  description: |
    A single connection with a brokerage. Note that `Connection` and `Brokerage Authorization` are interchangeable, but the term `Connection` is preferred and used in the doc for consistency.
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/DeleteUserResponse

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (DeleteUserResponse)
