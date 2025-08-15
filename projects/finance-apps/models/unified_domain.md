---
tags: [models, unified-schema, memory-bank]
project: finance-apps
type: model-schema
status: draft
---

# Unified Domain Schema (YAML)

This note contains the single source-of-truth unified domain schema. It's intended to be the canonical YAML that drives code generation for Pydantic, SQLAlchemy and TypeScript interfaces.

## Purpose
- Human-editable canonical schema for domain entities
- Source for codegen pipeline (markbot/codegen)
- Basis for Obsidian Canvas visualization: `projects/finance-apps/canvas/unified-model.canvas`

## Schema (YAML)
```yaml
entities:
  Account:
    fields:
      id:
        type: any
        primary_key: true
      brokerage_authorization:
        type: any
      name:
        type: any
      number:
        type: any
      institution_name:
        type: any
      created_date:
        type: any
      sync_status:
        type: any
      balance:
        type: any
      status:
        type: any
      raw_type:
        type: any
    cache_ttl: 3600
  AccountOrderRecord:
    fields:
      brokerage_order_id:
        type: any
      status:
        type: any
      symbol:
        type: any
      universal_symbol:
        type: any
      action:
        type: any
      total_quantity:
        type: any
      open_quantity:
        type: any
      canceled_quantity:
        type: any
      filled_quantity:
        type: any
      execution_price:
        type: any
      limit_price:
        type: any
      stop_price:
        type: any
      order_type:
        type: any
      time_in_force:
        type: any
      time_placed:
        type: any
      time_updated:
        type: any
      time_executed:
        type: any
      expiry_date:
        type: any
    cache_ttl: 3600
  BrokerageAuthorization:
    fields:
      id:
        type: any
        primary_key: true
      created:
        type: any
      updated:
        type: any
      brokerage:
        type: any
      name:
        type: any
      type:
        type: any
      disabled:
        type: any
      disabled_date:
        type: any
      meta:
        type: any
    cache_ttl: 3600
  Candle:
    fields:
      universal_symbol_id:
        type: any
      symbol:
        type: any
      description:
        type: any
      timestamp:
        type: any
      open:
        type: any
      high:
        type: any
      low:
        type: any
      close:
        type: any
      volume:
        type: any
    cache_ttl: 3600
  Lot:
    fields:
      id:
        type: any
        primary_key: true
      universal_symbol_id:
        type: any
      symbol:
        type: any
      description:
        type: any
      account_id:
        type: any
      open_date:
        type: any
      quantity:
        type: any
      open_price:
        type: any
      cost_basis:
        type: any
    cache_ttl: 3600
  PerformanceMetrics:
    fields:
      total_return:
        type: any
      sharpe_ratio:
        type: any
      max_drawdown:
        type: any
      volatility:
        type: any
      currency:
        type: any
    cache_ttl: 3600
  PortfolioSummary:
    fields:
      total_equity:
        type: any
      total_cash:
        type: any
      total_holdings_value:
        type: any
      total_pnl:
        type: any
      total_pnl_percent:
        type: any
      currency:
        type: any
    cache_ttl: 3600
  Position:
    fields:
      symbol:
        type: any
      account:
        type: any
      units:
        type: any
      price:
        type: any
      open_pnl:
        type: any
      average_purchase_price:
        type: any
    cache_ttl: 3600
  Trade:
    fields:
      id:
        type: any
        primary_key: true
      account:
        type: any
      symbol:
        type: any
      action:
        type: any
      order_type:
        type: any
      price:
        type: any
      quantity:
        type: any
      time_in_force:
        type: any
      status:
        type: any
      created_date:
        type: any
      updated_date:
        type: any
    cache_ttl: 3600
  UniversalSymbol:
    fields:
      id:
        type: any
        primary_key: true
      symbol:
        type: any
      raw_symbol:
        type: any
      description:
        type: any
      currency:
        type: any
      exchange:
        type: any
      type:
        type: any
    cache_ttl: 86400
```

## Next steps
- Create Obsidian Canvas at `projects/finance-apps/canvas/unified-model.canvas` with entity cards for top-level entities (UniversalSymbol, Account, Lot, Candle, Trade, Position, PortfolioSummary).
- Run the codegen pipeline to generate Pydantic/SQLAlchemy/TS interfaces from this YAML.

---
