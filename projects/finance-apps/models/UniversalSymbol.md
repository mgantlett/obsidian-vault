---
tags: [template, model, domain]
template: entity
entity: "UniversalSymbol"
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

# UniversalSymbol

Uniquely describes a single security + exchange combination across all brokerages.

## SOT (YAML fragment)
```yaml
sot:
  fields:
    id:
      type: string
      primary_key: true
      description: "Unique identifier for the symbol within SnapTrade. This is the ID used to reference the symbol in SnapTrade API calls."
    symbol:
      type: string
      description: "The security's trading ticker symbol. For example 'AAPL' for Apple Inc."
    raw_symbol:
      type: string
      description: "The raw symbol is `symbol` with the exchange suffix removed. For example, if `symbol` is 'VAB.TO', then `raw_symbol` is 'VAB'."
    description:
      type: string | null
      description: "A human-readable description of the security. This is usually the company name or ETF name."
    currency:
      type: Currency
      description: "The currency in which the security is traded."
    exchange:
      type: Exchange
      description: "The exchange on which the security is listed and traded."
    type:
      type: string
      description: "The type of security."
  cache_ttl: 3600
  meta:
    owner: infra
    version: 1
```

## Notes
- Usage: used by pricing, order placement, display and mapping layers.
- Relationships: links to `Currency` and `Exchange` entities; used by `PositionSymbol` and `AccountOrderRecord`.
- Validation: ensure `symbol` + `exchange` pair resolves uniquely in upstream providers.

## Example JSON

```json
{
  "id": "8b7c6d5e-0000-1111-2222-333344445555",
  "symbol": "AAPL",
  "raw_symbol": "AAPL:NASDAQ",
  "description": "Apple Inc. common stock",
  "currency": {
    "code": "USD"
  },
  "exchange": {
    "code": "NASDAQ"
  },
  "type": "equity"
}
```



## Backlinks & Code references
- Domain model: `markbot/src/markbot/domain/models.py` (UniversalSymbol)
- Canvas: projects/finance-apps/canvas/domain-model.canvas
