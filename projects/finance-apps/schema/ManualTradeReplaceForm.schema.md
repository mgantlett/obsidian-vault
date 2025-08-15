---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/ManualTradeReplaceForm
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# ManualTradeReplaceForm (Schema)

Canonical YAML fragment (extracted from API):

```yaml
ManualTradeReplaceForm:
  description: Inputs for replacing an order with the brokerage.
  type: object
  required:
    - brokerage_order_id
    - action
    - order_type
    - time_in_force
  properties:
    brokerage_order_id:
      $ref: "#/components/schemas/BrokerageOrderID"
    action:
      $ref: "#/components/schemas/ActionStrict"
    order_type:
      $ref: "#/components/schemas/OrderTypeStrict"
    time_in_force:
      $ref: "#/components/schemas/TimeInForceStrict"
    price:
      description: The limit price for `Limit` and `StopLimit` orders.
      type: number
      example: 31.33
      nullable: true
    symbol:
      description: The security's trading ticker symbol
      type: string
      example: AAPL
    stop:
      description: The price at which a stop order is triggered for `Stop` and `StopLimit` orders.
      type: number
      example: 31.33
      nullable: true
    units:
      nullable: true
      allOf:
        - $ref: "#/components/schemas/Units"
ManualTradeFormWithOptions:
  description: Inputs for placing an order with the brokerage.
  type: object
  required:
    - account_id
    - action
    - order_type
    - time_in_force
  properties:
    account_id:
      $ref: "#/components/schemas/AccountID"
    action:
      $ref: "#/components/schemas/ActionStrictWithOptions"
    universal_symbol_id:
      description: The universal symbol ID of the security to trade. Must be 'null' if `symbol` is provided, otherwise must be provided.
      nullable: true
      allOf:
        - $ref: "#/components/schemas/UniversalSymbolID"
    symbol:
      description: The security's trading ticker symbol. If 'symbol' is provided, then 'universal_symbol_id' must be 'null'.
      type: string
      example: AAPL
      nullable: true
    order_type:
      $ref: "#/components/schemas/OrderTypeStrict"
    time_in_force:
      $ref: "#/components/schemas/TimeInForceStrict"
    price:
      description: The limit price for `Limit` and `StopLimit` orders.
      type: number
      example: 31.33
      nullable: true
    stop:
      description: The price at which a stop order is triggered for `Stop` and `StopLimit` orders.
      type: number
      example: 31.33
      nullable: true
    units:
      description: For Equity orders, this represents the number of shares for the order. This can be a decimal for fractional orders. Must be `null` if `notional_value` is provided. If placing an Option order, this field represents the number of contracts to buy or sell. (e.g., 1 contract = 100 shares).
      nullable: true
      allOf:
        - $ref: "#/components/schemas/Units"
    notional_value:
      nullable: true
      allOf:
        - $ref: "#/components/schemas/NotionalValue"
ManualTradeFormBracket:
  description: Inputs for placing an order with the brokerage.
  type: object
  required:
    - action
    - order_type
    - time_in_force
    - stop_loss
    - take_profit
    - instrument
  properties:
    action:
      $ref: "#/components/schemas/ActionStrictWithOptions"
    symbol:
      description: The security's trading ticker symbol.
      type: string
      example: AAPL
    instrument:
      $ref: "#/components/schemas/TradingInstrument"
    order_type:
      $ref: "#/components/schemas/OrderTypeStrict"
    time_in_force:
      $ref: "#/components/schemas/TimeInForceStrict"
    price:
      description: The limit price for `Limit` and `StopLimit` orders.
      type: number
      example: 31.33
      nullable: true
    stop:
      description: The price at which a stop order is triggered for `Stop` and `StopLimit` orders.
      type: number
      example: 31.33
      nullable: true
    units:
      $ref: "#/components/schemas/Units"
    stop_loss:
      $ref: "#/components/schemas/StopLoss"
    take_profit:
      $ref: "#/components/schemas/TakeProfit"
ValidatedTradeBody:
  type: object
  properties:
    wait_to_confirm:
      nullable: true
      example: true
      type: boolean
      description: Optional, defaults to true. Determines if a wait is performed to check on order status. If false, latency will be reduced but orders returned will be more likely to be of status `PENDING` as we will not wait to check on the status before responding to the request.
CryptoTradingInstrument:
  type: object
  required:
    - symbol
    - type
  properties:
    symbol:
      description: The instrument's trading ticker symbol
      type: string
      example: BTC
    type:
      description: The instrument's type
      type: string
      enum:
        - CRYPTOCURRENCY
        - CRYPTOCURRENCY_PAIR
TradingInstrument:
  type: object
  required:
    - symbol
    - type
  properties:
    symbol:
      description: The instrument's trading ticker symbol
      type: string
      example: AAPL
    type:
      description: The instrument's type
      type: string
      enum:
        - EQUITY
        - CRYPTOCURRENCY
        - CRYPTOCURRENCY_PAIR
BrokerageInstrumentsResponse:
  type: object
  properties:
    instruments:
      type: array
      items:
        $ref: "#/components/schemas/BrokerageInstrument"
BrokerageInstrument:
  type: object
  properties:
    symbol:
      description: The instrument's trading symbol / ticker.
      type: string
      example: AAPL
    exchange_mic:
      description: The MIC code of the exchange where the instrument is traded.
      type: string
      example: XNAS
      nullable: true
    tradeable:
      description: Whether the instrument is tradeable through the brokerage. `null` if the tradeability is unknown.
      type: boolean
      example: true
      nullable: true
    fractionable:
      description: Whether the instrument allows fractional units. `null` if the fractionability is unknown.
      type: boolean
      example: true
      nullable: true
    universal_symbol_id:
      description: The universal symbol ID of the instrument. This is the ID used to reference the instrument in SnapTrade API calls.
      type: string
      format: uuid
      example: 2bcd7cc3-e922-4976-bce1-9858296801c3
      nullable: true
MlegTradingInstrument:
  type: object
  required:
    - symbol
    - instrument_type
  properties:
    symbol:
      description: The security's trading ticker symbol. This currently supports stock symbols and Options symbols in the 21 character OCC format. For example `AAPL  131124C00240000` represents a call option on AAPL expiring on 2024-11-13 with a strike price of $240. For more information on the OCC format, see [here](https://en.wikipedia.org/wiki/Option_symbol#OCC_format)
      type: string
      example: PBI   250718C00006000
    instrument_type:
      $ref: "#/components/schemas/MlegInstrumentType"
OrderTypeStrict:
  description: |
    The type of order to place.
```

## Notes
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/ManualTradeReplaceForm

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (ManualTradeReplaceForm)
