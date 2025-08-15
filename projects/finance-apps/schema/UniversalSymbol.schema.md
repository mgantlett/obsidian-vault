---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/UniversalSymbol
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# UniversalSymbol (Schema)

Canonical YAML fragment (extracted from API):

```yaml
UniversalSymbol:
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
    currencies:
      deprecated: true
      description: This field is deprecated and should not be used. Please reach out to SnapTrade support if you have a valid usecase for this.
      type: array
      items:
        $ref: "#/components/schemas/Currency"
  required:
    - id
    - symbol
    - raw_symbol
    - currency
    - type
    - currencies
UnderlyingSymbol:
  # FIXME: Why is this different from UniversalSymbol
  description: Symbol object for the underlying security of an option.
  type: object
  properties:
    id:
      $ref: "#/components/schemas/UniversalSymbolID"
    symbol:
      description: The security's trading ticker symbol. For example "AAPL" for Apple Inc. We largely follow the [Yahoo Finance ticker format](https://help.yahoo.com/kb/SLN2310.html)(click on "Yahoo Finance Market Coverage and Data Delays"). For example, for securities traded on the Toronto Stock Exchange, the symbol has a '.TO' suffix. For securities traded on NASDAQ or NYSE, the symbol does not have a suffix.
      type: string
      example: SPY
    raw_symbol:
      description: The raw symbol is `symbol` with the exchange suffix removed. For example, if `symbol` is "VAB.TO", then `raw_symbol` is "VAB".
      type: string
      example: VAB
    description:
      description: A human-readable description of the security. This is usually the company name or ETF name.
      type: string
      example: SPDR S&P 500 ETF Trust
      nullable: true
    currency:
      description: The currency in which the security is traded.
      allOf:
        - $ref: "#/components/schemas/Currency"
    exchange:
      description: The exchange on which the security is listed and traded.
      allOf:
        - $ref: "#/components/schemas/USExchange"
    type:
      description: The type of security. For example, "Common Stock" or "ETF".
      allOf:
        - $ref: "#/components/schemas/SecurityType"
    figi_code:
      description: This identifier is unique per security per trading venue. See section 1.4.1 of the [FIGI Standard](https://www.openfigi.com/assets/local/figi-allocation-rules.pdf) for more information. This value should be the same as the `figi_code` in the `figi_instrument` child property.
      type: string
      example: BBG000B9XRY4
      nullable: true
    figi_instrument:
      nullable: true
      allOf:
        - $ref: "#/components/schemas/FigiInstrument"
    currencies:
      deprecated: true
      description: This field is deprecated and should not be used. Please reach out to SnapTrade support if you have a valid usecase for this.
      type: array
      items:
        $ref: "#/components/schemas/Currency"
OptionsSymbol:
  description: Uniquely describes an option security + exchange combination across all brokerages.
  type: object
  required:
    - id
    - ticker
    - option_type
    - strike_price
    - expiration_date
    - underlying_symbol
  properties:
    id:
      $ref: "#/components/schemas/OptionSymbolID"
    ticker:
      description: The [OCC symbol](https://en.wikipedia.org/wiki/Option_symbol) for the option.
      type: string
      example: AAPL  261218C00240000
    option_type:
      description: The type of option. Either "CALL" or "PUT".
      type: string
      enum:
        - CALL
        - PUT
      example: CALL
    strike_price:
      description: The option strike price.
      type: number
      example: 240
    expiration_date:
      description: The option expiration date.
      type: string
      format: date
      example: "2026-12-18"
    is_mini_option:
      description: Whether the option is a mini option. Mini options have 10 underlying shares per contract instead of the standard 100.
      type: boolean
      example: false
    underlying_symbol:
      $ref: "#/components/schemas/UnderlyingSymbol"
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/UniversalSymbol

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (UniversalSymbol)
