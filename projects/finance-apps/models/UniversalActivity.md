---
tags: [template, model, domain]
template: entity
entity: "UniversalActivity"
source: markbot/src/markbot/domain/models.py
owner: infra
status: draft
cache_ttl: 3600
version: 1
migration_state: draft
sensitive: false
generated_paths: []
tests: []
examples: []
---

# UniversalActivity

A transaction or activity from an institution.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      description: "Unique identifier for the transaction."
    account:
      type: Account
      description: "The account that the transaction is associated with."
    universal_symbol:
      type: UniversalSymbol
      description: "The security for the transaction."
    description:
      type: string
      description: "A human-readable description of the transaction."
    trade_date:
      type: string
      description: "The recorded time for the transaction."
    settlement_date:
      type: string
      description: "The date on which the transaction is settled."
    action:
      type: string
      description: "A string representing the type of transaction."
    quantity:
      type: float
      description: "The number of units of the security for the transaction."
    price:
      type: float
      description: "The price of the security for the transaction."
    commission:
      type: float
      description: "Any fee associated with the transaction if provided by the brokerage."
    amount:
      type: float
      description: "The amount of the transaction denominated in `currency`."
    currency:
      type: string
      description: "The currency in which the transaction `price` and `amount` is denominated."
    type:
      type: string
      description: "A string representing the type of transaction."
    option_type:
      type: string | null
      description: "If an option `BUY` or `SELL` transaction, this further specifies the type of action."
    expiry_date:
      type: string | null
      description: "The option expiration date."
    strike_price:
      type: float | null
      description: "The option strike price."
    external_transaction_description:
      type: string | null
      description: "External transaction description."
    external_transaction_id:
      type: string | null
      description: "Reference ID from brokerage used to identify related transactions."
    marketplace:
      type: string | null
      description: "The institution that the transaction is associated with."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: canonical representation of transactions for ledgering, reconciliation and activity feeds.
- Relationships: references `Account` and `UniversalSymbol` models.
- Validation: monetary fields align with `currency` and dates use ISO-8601.

## Example JSON
```json
{
  "id": "txn-abcdef-123456",
  "account": { "id": "acc-1234-5678" },
  "universal_symbol": { "id": "...", "symbol": "AAPL", "exchange": { "code": "NASDAQ" } },
  "description": "Buy 10 AAPL",
  "trade_date": "2025-08-14T12:00:00Z",
  "settlement_date": "2025-08-16",
  "action": "BUY",
  "quantity": 10,
  "price": 174.5,
  "commission": 1.0,
  "amount": 1745.0,
  "currency": "USD",
  "type": "trade"
}
```

## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (UniversalActivity)
- Canvas: projects/finance-apps/canvas/domain-model.canvas