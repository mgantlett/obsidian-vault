---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/LoginRedirectURI
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# LoginRedirectURI (Schema)

Canonical YAML fragment (extracted from API):

```yaml
LoginRedirectURI:
  description: Redirect uri upon successful login
  type: object
  properties:
    redirectURI:
      description: Connection Portal link to redirect user to connect a brokerage account.
      type: string
      example: https://app.snaptrade.com/snapTrade/redeemToken?token=npVKchZrL0MYIHTusGfADT74r4xXpHkmbxbQDmt0RINLXbQ5cWsvGkPSgMQRxz8/cnxjzL9T2NWLuHuDyidHiCNeXXTb/tVhzC2olSyfxWW6DRrkUppArGCdmkIHyBMzog6C55P8yoqzcGer5Hml0Q%3D%3D&clientId=WEALTHLY&broker=ROBINHOOD&connectionPortalVersion=v4&sessionId=cf371bb4-a475-4f17-ab94-d0fee699960d
    sessionId:
      description: ID to identify the connection portal session.
      type: string
      example: cf371bb4-a475-4f17-ab94-d0fee699960d
ClientID:
  description: SnapTrade Client ID (generated and provided to partner by SnapTrade)
  type: string
  example: SNAPTRADETEST
UserID:
  description: SnapTrade User ID. This is chosen by the API partner and can be any string that is a) unique to the user, and b) immutable for the user. It is recommended to NOT use email addresses for this property because they are usually not immutable.
  type: string
  example: snaptrade-user-123
UserSecret:
  description: SnapTrade User Secret. This is a randomly generated string and should be stored securely. If compromised, please rotate it via the [rotate user secret endpoint](/reference/Authentication/Authentication_resetSnapTradeUserSecret).
  type: string
  example: adf2aa34-8219-40f7-a6b3-60156985cc61
PerformanceCustom:
  description: Performance Custom Response Object
  type: object
  properties:
    totalEquityTimeframe:
      type: array
      items:
        $ref: "#/components/schemas/PastValue"
    contributions:
      $ref: "#/components/schemas/NetContributions"
    contributionTimeframe:
      type: array
      items:
        $ref: "#/components/schemas/PastValue"
    contributionTimeframeCumulative:
      type: array
      items:
        $ref: "#/components/schemas/PastValue"
    withdrawalTimeframe:
      type: array
      items:
        $ref: "#/components/schemas/PastValue"
    contributionStreak:
      type: number
      example: 5
      description: Current streak of cosecutive months where contributions were made
      nullable: true
    contributionMonthsContributed:
      type: number
      example: 10
      description: Number of months in the timeframe with contributions
      nullable: true
    contributionTotalMonths:
      type: number
      example: 13
      description: Total months in timeframe
      nullable: true
    dividends:
      type: array
      items:
        $ref: "#/components/schemas/NetDividend"
    dividendIncome:
      type: number
      description: Total dividends received over the timeframe
      example: 135.97
      nullable: true
    monthlyDividends:
      type: number
      description: Average dividends received per month over the timeframe
      example: 26.37
      nullable: true
    badTickers:
      type: array
      items:
        type: string
        example: MAW105
        nullable: true
      description:
        list of tickers which may not be supported or may not have accurate
        price data
    dividendTimeline:
      type: array
      items:
        $ref: "#/components/schemas/MonthlyDividends"
    commissions:
      type: number
      example: 3.26
      description: commissions incurred during the timeframe
      nullable: true
    forexFees:
      type: number
      example: 5.26
      description: forex fees incurred during the timeframe
      nullable: true
    fees:
      type: number
      example: 2.72
      description: other fees incurred during the timeframe
      nullable: true
    rateOfReturn:
      type: number
      example: 0.082312367452
      description:
        The return rate over the timeframe. Annualized if timeframe is
        longer than 1 year
      nullable: true
    returnRateTimeframe:
      type: array
      items:
        $ref: "#/components/schemas/SubPeriodReturnRate"
    detailedMode:
      type: boolean
      description:
        Whether the user has detailed mode enabled (more frequent data
        points for totalEquity and contribution timeframes)
SubPeriodReturnRate:
  type: object
  properties:
    periodStart:
      $ref: "#/components/schemas/ReportingDate"
    periodEnd:
      $ref: "#/components/schemas/ReportingDate"
    rateOfReturn:
      type: number
      example: 0.012312367452
      description: The return rate for the given period
      nullable: true
DividendAtDate:
  type: object
  properties:
    symbol:
      type: string
      example: AAPL
      description: The ticker of the symbol that the dividend came from
      nullable: true
    amount:
      type: number
      example: 6.82
      description: The amount received from the dividend
      nullable: true
    currency:
      type: string
      example: CAD
      description: The currency of the amount
PartnerData:
  description: Configurations for your SnapTrade Client ID, including allowed brokerages and data access.
  type: object
  properties:
    slug:
      type: string
      description: A short, unique identifier for your company or product.
      example: WEALTHLY
    name:
      type: string
      description: Your company or product name.
      example: Wealthly
    logo_url:
      type: string
      description: URL to your company or product logo.
      example: https://example.com/logo.png
    allowed_brokerages:
      type: array
      description: Brokerages that can be accessed by your Client ID.
      items:
        $ref: "#/components/schemas/Brokerage"
    can_access_trades:
      type: boolean
      description: Whether trading is enabled for your SnapTrade Client ID.
      example: true
    can_access_holdings:
      type: boolean
      description: Whether holdings data is enabled for your SnapTrade Client ID.
      example: true
    can_access_account_history:
      type: boolean
      description: Whether account historical transactions is enabled for your SnapTrade Client ID.
      example: true
    can_access_reference_data:
      type: boolean
      description: Whether reference data is enabled for your SnapTrade Client ID.
      example: true
    can_access_portfolio_management:
      type: boolean
      description: Whether portfolio management is enabled for your SnapTrade Client ID.
      example: true
    can_access_orders:
      type: boolean
      description: Whether recent order history is enabled for your SnapTrade Client ID.
      example: true
    redirect_uri:
      type: string
      description: URI to redirect user back to after user is done adding brokerage connections.
      example: https://example.com/oauth/snaptrade
    pin_required:
      deprecated: true
      type: boolean
      description: Shows if pin is required by users to access connection page. This field has been deprecated.
      example: false
Position:
  description: Describes a single stock/ETF/crypto/mutual fund position in an account.
  type: object
  properties:
    symbol:
      $ref: "#/components/schemas/PositionSymbol"
    units:
      description: The number of shares of the position. This can be fractional or integer units.
      type: number
      example: 40
      nullable: true
    price:
      type: number
      example: 113.15
      description: Last known market price for the symbol. The freshness of this price depends on the brokerage. Some brokerages provide real-time prices, while others provide delayed prices. It is recommended that you rely on your own third-party market data provider for most up to date prices.
      nullable: true
    open_pnl:
      type: number
      description: The profit or loss on the position since it was opened. This is calculated as the difference between the current market value of the position and the total cost of the position. It is recommended to calculate this value using the average purchase price and the current market price yourself, instead of relying on this field.
      example: 0.44
      nullable: true
    average_purchase_price:
      type: number
      nullable: true
      example: 108.3353
      description: Cost basis _per share_ of this position.
    fractional_units:
      deprecated: true
      description:
        Deprecated, use the `units` field for both fractional and integer
        units going forward
      type: number
      nullable: true
      example: 1.44
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/LoginRedirectURI

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (LoginRedirectURI)
