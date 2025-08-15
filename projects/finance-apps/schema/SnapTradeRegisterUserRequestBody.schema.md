---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/SnapTradeRegisterUserRequestBody
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# SnapTradeRegisterUserRequestBody (Schema)

Canonical YAML fragment (extracted from API):

```yaml
SnapTradeRegisterUserRequestBody:
  description: Data required to register a user via SnapTrade Partner
  type: object
  required:
    - userId
  properties:
    userId:
      $ref: "#/components/schemas/UserID"
SnapTradeLoginUserRequestBody:
  description: Data to login a user via SnapTrade Partner
  type: object
  properties:
    broker:
      description: Slug of the brokerage to connect the user to. See [the integrations page](https://snaptrade.notion.site/66793431ad0b416489eaabaf248d0afb?v=3cfea70ef4254afc89704e47275a7a9a&pvs=4) for a list of supported brokerages and their slugs.
      type: string
      example: ALPACA
    immediateRedirect:
      description: When set to `true`, user will be redirected back to the partner's site instead of the connection portal. This parameter is ignored if the connection portal is loaded inside an iframe. See the [guide on ways to integrate the connection portal](/docs/implement-connection-portal) for more information.
      type: boolean
      example: true
    customRedirect:
      description: URL to redirect the user to after the user connects their brokerage account. This parameter is ignored if the connection portal is loaded inside an iframe. See the [guide on ways to integrate the connection portal](/docs/implement-connection-portal) for more information.
      type: string
      example: https://snaptrade.com
    reconnect:
      description: The UUID of the brokerage connection to be reconnected. This parameter should be left empty unless you are reconnecting a disabled connection. See the [guide on fixing broken connections](/docs/fix-broken-connections) for more information.
      type: string
      example: 8b5f262d-4bb9-365d-888a-202bd3b15fa1
    connectionType:
      description: Sets whether the connection should be read-only or trade-enabled. Defaults to read-only if not specified.
      type: string
      enum:
        - read
        - trade
      default: read
    connectionPortalVersion:
      description: Sets the connection portal version to render. Currently only v4 is supported and is the default. All other versions are deprecated and will automatically be set to v4.
      type: string
      example: v4
      enum:
        - v4
        - v3
        - v2
      default: v4
Symbol:
  # FIXME Merge this with UniversalSymbol
  description: Uniquely describes a single security + exchange combination across all brokerages.
  type: object
  properties:
    id:
      $ref: "#/components/schemas/UniversalSymbolID"
    symbol:
      description: The security's trading ticker symbol. For example "AAPL" for Apple Inc. We largely follow the [Yahoo Finance ticker format](https://help.yahoo.com/kb/SLN2310.html)(click on "Yahoo Finance Market Coverage and Data Delays"). For example, for securities traded on the Toronto Stock Exchange, the symbol has a '.TO' suffix. For securities traded on NASDAQ or NYSE, the symbol does not have a suffix.
      type: string
      example: VAB.TO
    raw_symbol:
      description: The raw symbol is `symbol` with the exchange suffix removed. For example, if `symbol` is "VAB.TO", then `raw_symbol` is "VAB".
      type: string
      example: VAB
    description:
      description: A human-readable description of the security. This is usually the company name or ETF name.
      type: string
      example: VANGUARD CDN AGGREGATE BOND INDEX ETF
      nullable: true
    currency:
      description: The currency in which the security is traded.
      allOf:
        - $ref: "#/components/schemas/Currency"
    exchange:
      description: The exchange on which the security is listed and traded.
      allOf:
        - $ref: "#/components/schemas/Exchange"
    type:
      $ref: "#/components/schemas/SecurityType"
    figi_code:
      description: This identifier is unique per security per trading venue. See section 1.4.1 of the [FIGI Standard](https://www.openfigi.com/assets/local/figi-allocation-rules.pdf) for more information. This value should be the same as the `figi_code` in the `figi_instrument` child property.
      type: string
      example: BBG000B9XRY4
      nullable: true
    figi_instrument:
      nullable: true
      allOf:
        - $ref: "#/components/schemas/FigiInstrument"
UserIDandSecret:
  type: object
  properties:
    userId:
      $ref: "#/components/schemas/UserID"
    userSecret:
      $ref: "#/components/schemas/UserSecret"
UserList:
  description: List of registered SnapTrade user IDs
  type: array
  items:
    $ref: "#/components/schemas/UserID"
  example:
    - user1
    - user2
    - user3
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/SnapTradeRegisterUserRequestBody

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (SnapTradeRegisterUserRequestBody)
