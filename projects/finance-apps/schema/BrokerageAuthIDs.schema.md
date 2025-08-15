---
tags: [schema, domain, auto-generated]
project: finance-apps
type: schema
managed-by: obsidian-mcp
schema_version: 1.0
source: references/snaptrade-sdk/api.yaml#/components/schemas/BrokerageAuthIDs
owner: reference
created: 2025-08-14
last-updated: 2025-08-14
---

# BrokerageAuthIDs (Schema)

Canonical YAML fragment (extracted from API):

```yaml
BrokerageAuthIDs:
  description: Comma separated list of brokerage authorization IDs
  type: string
  example: 917c8734-8470-4a3e-a18f-57c3f2ee6631,65e839a3-9103-4cfb-9b72-2071ef80c5f2
AccountHoldings:
  description: Account Holdings
  type: object
  properties:
    account:
      $ref: "#/components/schemas/SnapTradeHoldingsAccount"
    balances:
      type: array
      nullable: true
      items:
        $ref: "#/components/schemas/Balance"
    positions:
      type: array
      nullable: true
      items:
        $ref: "#/components/schemas/Position"
    total_value:
      $ref: "#/components/schemas/SnapTradeHoldingsTotalValue"
AccountHoldingsAccount:
  description: A wrapper object containing holdings information for a single account.
  type: object
  properties:
    account:
      $ref: "#/components/schemas/Account"
    balances:
      type: array
      nullable: true
      description: List of balances for the account. Each element of the list has a distinct currency. Some brokerages like Questrade [allows holding multiple currencies in the same account](https://www.questrade.com/learning/questrade-basics/balances-and-reports/understanding-your-account-balances).
      items:
        $ref: "#/components/schemas/Balance"
    positions:
      type: array
      nullable: true
      description: List of stock/ETF/crypto/mutual fund positions in the account.
      items:
        $ref: "#/components/schemas/Position"
    option_positions:
      type: array
      nullable: true
      description: List of option positions in the account.
      items:
        $ref: "#/components/schemas/OptionsPosition"
    orders:
      type: array
      nullable: true
      description: List of recent orders in the account, including both pending and executed orders. Note that option orders are included in this list. Option orders will have a null `universal_symbol` field and a non-null `option_symbol` field.
      items:
        $ref: "#/components/schemas/AccountOrderRecord"
    total_value:
      $ref: "#/components/schemas/SnapTradeHoldingsTotalValue"
RecentOrdersResponse:
  description: List of orders executed within the last 24 hours
  type: object
  properties:
    orders:
      type: array
      description: List of orders executed in the last 24 hours
      items:
        $ref: "#/components/schemas/AccountOrderRecord"
RateOfReturnResponse:
  description: List of return rates with their timeframe
  type: object
  properties:
    data:
      type: array
      description: List of return percentages
      items:
        $ref: "#/components/schemas/RateOfReturnObject"
RateOfReturnObject:
  description: Individual rate of return object with return percent and timeframe
  type: object
  properties:
    timeframe:
      type: string
      enum:
        - ALL
        - 1Y
        - 6M
        - 3M
        - 1M
      description: The timeframe this return percent is reflecting
      example: ALL
    return_percent:
      type: number
      description: The percent return of the portfolio, directly from the brokerage. 5.97 indicates a 5.97% return over the timeframe
      example: 5.97
    created_date:
      type: string
      description: The date this was fetched
      format: date-time
      example: 2024-07-30T22:51:49.746270Z
AccountOrderRecord:
  description: Describes a single recent order in an account. Each record here represents a single order leg. For multi-leg orders, there will be multiple records.
  type: object
  properties:
    brokerage_order_id:
      $ref: "#/components/schemas/BrokerageOrderID"
    status:
      $ref: "#/components/schemas/AccountOrderRecordStatus"
    universal_symbol:
      description: Contains information about the security that the order is for. This field is only present for stock/ETF/crypto/mutual fund orders. For option orders, this field will be null and the `option_symbol` field will be populated.
      allOf:
        - $ref: "#/components/schemas/UniversalSymbol"
    option_symbol:
      description: Contains information about the option contract that the order is for. This field is only present for option orders. For stock/ETF/crypto/mutual fund orders, this field will be null and the `universal_symbol` field will be populated.
      allOf:
        - $ref: "#/components/schemas/OptionsSymbol"
    quote_universal_symbol:
      description: Quote cryptocurrency. This field is only present for cryptocurrency pair orders with a cryptocurrency as quote.
      allOf:
        - $ref: "#/components/schemas/UniversalSymbol"
    quote_currency:
      description: Quote currency. This field is only present for cryptocurrency pair orders with a fiat currency as quote.
      allOf:
        - $ref: "#/components/schemas/Currency"
    action:
      $ref: "#/components/schemas/Action"
    total_quantity:
      description: The total number of shares or contracts of the order. This should be the sum of the filled, canceled, and open quantities. Can be a decimal number for fractional shares.
      nullable: true
      type: number
      example: 100
    open_quantity:
      description: The number of shares or contracts that are still open (waiting for execution). Can be a decimal number for fractional shares.
      nullable: true
      type: number
      example: 10
    canceled_quantity:
      description: The number of shares or contracts that have been canceled. Can be a decimal number for fractional shares.
      nullable: true
      type: number
      example: 10
    filled_quantity:
      description: The number of shares or contracts that have been filled. Can be a decimal number for fractional shares.
      nullable: true
      type: number
      example: 80
    execution_price:
      description: The price at which the order was executed.
      nullable: true
      type: number
      example: 12.34
    limit_price:
      description: The limit price is maximum price one is willing to pay for a buy order or the minimum price one is willing to accept for a sell order. Should only apply to `Limit` and `StopLimit` orders.
      nullable: true
      type: number
      example: 12.34
    stop_price:
      description: The stop price is the price at which a stop order is triggered. Should only apply to `Stop` and `StopLimit` orders.
      nullable: true
      type: number
      example: 12.50
    order_type:
      description: The type of order placed. The most common values are `Market`, `Limit`, `Stop`, and `StopLimit`. We try our best to map brokerage order types to these values. When mapping fails, we will return the brokerage's order type value.
      nullable: true
      type: string
      example: Market
    time_in_force:
      description: >
        The Time in Force type for the order. This field indicates how long the order will remain active before it is executed or expires. We try our best to map brokerage time in force values to the following. When mapping fails, we will return the brokerage's time in force value.
          - `Day` - Day. The order is valid only for the trading day on which it is placed.
          - `GTC` - Good Til Canceled. The order is valid until it is executed or canceled.
          - `FOK` - Fill Or Kill. The order must be executed in its entirety immediately or be canceled completely.
          - `IOC` - Immediate Or Cancel. The order must be executed immediately. Any portion of the order that cannot be filled immediately will be canceled.
          - `GTD` - Good Til Date. The order is valid until the specified date.
          - `MOO` - Market On Open. The order is to be executed at the day's opening price.
          - `EHP` - Extended Hours P.M. The order is to be placed during extended hour trading, after markets close.
      type: string
    time_placed:
      description: The time the order was placed. This is the time the order was submitted to the brokerage.
      type: string
      format: date-time
      example: 2024-07-30T22:51:49.746270Z
    time_updated:
      description: The time the order was last updated in the brokerage system. This value is not always available from the brokerage.
      nullable: true
      type: string
      format: date-time
      example: 2024-08-05T00:05:57.409000Z
    time_executed:
      description: The time the order was executed in the brokerage system. This value is not always available from the brokerage.
      nullable: true
      type: string
      format: date-time
      example: 2024-08-05T00:05:57.409000Z
    expiry_date:
      description: The time the order expires. This value is not always available from the brokerage.
      nullable: true
      type: string
      format: date-time
      example: 2024-08-05T00:05:57.409000Z
    symbol:
      $ref: "#/components/schemas/BrokerageSymbolID"
    child_brokerage_order_ids:
      nullable: true
      allOf:
        - $ref: "#/components/schemas/ChildBrokerageOrderIDs"
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
- Source: references/snaptrade-sdk/api.yaml#/components/schemas/BrokerageAuthIDs

## Backlinks & Code references
- Domain model: markbot/src/markbot/domain/models.py (BrokerageAuthIDs)
