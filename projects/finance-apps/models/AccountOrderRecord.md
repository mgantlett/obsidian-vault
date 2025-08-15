---
tags: [template, model, reference]
template: entity
entity: "AccountOrderRecord"
source: references/snaptrade-sdk/api.yaml
owner: reference
status: draft
cache_ttl: 3600
version: 1
migration_state: synced-from-api
sensitive: false
generated_paths: []
tests: []
examples: []
---

# AccountOrderRecord

Mirrors SnapTrade `components.schemas.AccountOrderRecord`.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    brokerage_order_id:
      type: string
      description: "Order ID returned by brokerage."
    status:
      type: AccountOrderRecordStatus
      description: "Mapped order status enum from SnapTrade."
    universal_symbol:
      type: UniversalSymbol | null
      description: "Universal symbol for equity/crypto; null for option orders."
    option_symbol:
      type: OptionsSymbol | null
      description: "Option symbol object for option orders; null for equities."
    quote_universal_symbol:
      type: UniversalSymbol | null
      description: "Quote universal symbol for crypto pair orders when quote is a crypto."
    quote_currency:
      type: Currency | null
      description: "Quote currency for crypto pair orders when quote is fiat."
    action:
      type: Action
      description: "The action/side of the order (BUY/SELL/... )."
    total_quantity:
      type: number | null
      description: "Total shares/contracts for the order. Can be fractional for equities."
    open_quantity:
      type: number | null
      description: "Remaining open quantity."
    canceled_quantity:
      type: number | null
      description: "Canceled quantity."
    filled_quantity:
      type: number | null
      description: "Filled quantity."
    execution_price:
      type: number | null
      description: "Execution price if available."
    limit_price:
      type: number | null
      description: "Limit price for limit/stop-limit orders."
    stop_price:
      type: number | null
      description: "Stop price for stop/stop-limit orders."
    order_type:
      type: string | null
      description: "Human-friendly order type (Market, Limit, Stop, StopLimit etc)."
    time_in_force:
      type: string | null
      description: "Time in force value (Day, GTC, FOK, IOC, GTD, etc)."
    time_placed:
      type: string
      format: date-time
      description: "ISO 8601 time the order was placed."
    time_updated:
      type: string | null
      format: date-time
      description: "ISO 8601 time the order was last updated."
    time_executed:
      type: string | null
      format: date-time
      description: "ISO 8601 time the order was executed."
    expiry_date:
      type: string | null
      format: date-time
      description: "Expiry date/time for GTD orders or order expiry."
    symbol:
      type: string | null
      description: "Legacy field: ticker string when present. Prefer `universal_symbol`/`option_symbol`."
    child_brokerage_order_ids:
      type: object | null
      description: "IDs for related child orders (take profit / stop loss) returned by brokerage."
  cache_ttl: 3600
  meta:
    source: references/snaptrade-sdk/api.yaml#/components/schemas/AccountOrderRecord
    owner: reference
    version: 1
```

## Notes
- Synced from SnapTrade OpenAPI `AccountOrderRecord`.
- Use `universal_symbol` for most equity/crypto cases; `option_symbol` for options.
- `child_brokerage_order_ids` can be used to map bracket order legs.

## Example JSON
```json
{
  "brokerage_order_id": "66a033fa-da74-4fcf-b527-feefdec9257e",
  "status": "EXECUTED",
  "universal_symbol": { "id": "2bcd...", "symbol": "AAPL" },
  "action": "BUY",
  "total_quantity": 100,
  "open_quantity": 0,
  "filled_quantity": 100,
  "execution_price": 150.25,
  "limit_price": null,
  "stop_price": null,
  "order_type": "Market",
  "time_in_force": "Day",
  "time_placed": "2024-08-05T00:05:57.409000Z",
  "time_updated": "2024-08-05T00:05:57.409000Z",
  "time_executed": "2024-08-05T00:05:57.409000Z"
}
```

## Backlinks & Code references
- SnapTrade API: `references/snaptrade-sdk/api.yaml#/components/schemas/AccountOrderRecord`
- Domain model: `markbot/src/markbot/domain/models.py` (AccountOrderRecord)
- Canvas: `projects/finance-apps/canvas/domain-model.canvas`

