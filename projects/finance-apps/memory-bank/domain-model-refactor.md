---
tags: [memory-bank, architecture, domain-model, refactor]
project: finance-apps
type: technical-analysis
status: analysis-complete
priority: critical
workstream: infrastructure
created: 2025-08-14
last-updated: 2025-08-14
last-action: comprehensive-analysis
next-milestone: unified-architecture-implementation
managed-by: obsidian-mcp
related-projects: []
---

# 🏗️ Domain Model Architecture Refactor Analysis

*Comprehensive analysis of current model chaos and unified architecture strategy*

## 🚨 **Critical Architecture Issue: Domain Model Chaos**

### **Current State Analysis**

Our domain models are **scattered across 3 incompatible layers** causing significant development friction and performance issues:

#### **📊 Layer 1: Python Domain Models** (`markbot/src/markbot/domain/models.py`)
- **40+ Pydantic models** covering complete SnapTrade API
- **Rich nested relationships**: Currency, Exchange, UniversalSymbol with proper typing
- **Recent additions**: `Lot`, `Candle` models with symbol/description fields
- **Form models**: ManualTradeForm, BacktestRequestForm, OptimizationRequestForm
- **Performance models**: PortfolioSummary, AccountPerformance, PerformanceMetrics

**Key Models Identified:**
```python
# Core Trading Entities
Account, Position, Trade, UniversalActivity, AccountOrderRecord
Lot, Candle, PortfolioSummary, PerformanceMetrics

# Reference Data
Currency, Exchange, UniversalSymbol, SecurityType, Brokerage
BrokerageAuthorization, TradingInstrument

# Trading Operations
ManualTrade, TradeImpact, OptionsPosition, SymbolsQuotes
OptionChainItem, ChainPerRootItem, ChainPerStrikePriceItem

# Request Forms
ManualTradeFormDomain, BacktestRequestForm, OptimizationRequestForm
```

#### **💾 Layer 2: SQLAlchemy ORM Models** (`markbot/src/markbot/db/models.py`)
- **Only 2 models**: `Lot` and `Candle` tables
- **Recently added**: `symbol` and `description` fields for display purposes
- **Critical Gap**: **Missing 95% of domain entities** - no persistence for accounts, positions, orders, reference data
- **Performance Impact**: No caching, repeated API calls for unchanging data

#### **🎨 Layer 3: TypeScript Models** (`spendviz/src/store/markbot.ts`)
- **6 basic interfaces**: Position, Trade, Portfolio, Lot, Candle, Strategy
- **Field inconsistencies**: `symbol_ticker` vs `symbol`, nested structure differences
- **Maintenance burden**: Manual synchronization with backend changes
- **Limited coverage**: Missing most domain entities available in Python

### **🔥 Impact Analysis**

#### **Performance Issues**
- 🐌 **Repeated API Calls**: No cache for reference data (symbols, accounts, exchanges)
- 📡 **Network Dependency**: Frontend requires constant SnapTrade connectivity
- ⏱️ **Slow Load Times**: Every symbol lookup hits external API
- 💸 **API Cost**: Unnecessary calls for static reference data

#### **Development Friction**
- 🔧 **Manual Sync**: TypeScript interfaces updated manually
- 🐛 **Field Mismatches**: `ticker` vs `symbol` causing display issues
- 📝 **Documentation Drift**: Models become inconsistent over time
- 🚫 **Breaking Changes**: Frontend breaks when backend models change

#### **Scalability Concerns**
- 📊 **No Offline Mode**: Requires constant API connectivity
- 🔄 **No Incremental Updates**: Full data refresh every time
- 📈 **Limited Analytics**: Can't perform complex queries on historical data
- 🏢 **Enterprise Readiness**: Missing audit trails and data lineage

## 🎯 **Unified Architecture Strategy**

### **Phase 1: Schema-First Design Foundation**

#### **1.1 Unified Schema Definition**
Create `markbot/schemas/unified_domain.yaml` as single source of truth:

```yaml
entities:
  UniversalSymbol:
    fields:
      id: {type: string, primary_key: true}
      symbol: {type: string, index: true}  # e.g., "AAPL"
      raw_symbol: {type: string}           # e.g., "AAPL" (without exchange)
      description: {type: string}          # e.g., "Apple Inc."
      currency_id: {type: string, foreign_key: "Currency.id"}
      exchange_id: {type: string, foreign_key: "Exchange.id"}
      type: {type: string}                 # e.g., "stock", "etf"
      last_updated: {type: datetime}
    cache_ttl: 86400  # 24 hours
    
  Account:
    fields:
      id: {type: string, primary_key: true}
      name: {type: string}
      number: {type: string}
      institution_name: {type: string}
      brokerage_authorization_id: {type: string}
      created_date: {type: datetime}
      status: {type: string}
      last_synced: {type: datetime}
    cache_ttl: 3600   # 1 hour
```

#### **1.2 Code Generation Pipeline**
Build generators for:

```python
# markbot/codegen/generators.py
class UnifiedModelGenerator:
    def generate_pydantic_models(self) -> str:
        """Generate Python Pydantic models"""
    
    def generate_sqlalchemy_models(self) -> str:
        """Generate SQLAlchemy ORM models"""
    
    def generate_typescript_interfaces(self) -> str:
        """Generate TypeScript interfaces"""
    
    def generate_api_schemas(self) -> str:
        """Generate OpenAPI/FastAPI schemas"""
```

### **Phase 2: Intelligent Cache Layer**

#### **2.1 Cache Architecture**
```python
# markbot/services/unified_cache_service.py
class UnifiedCacheService:
    """Intelligent caching with TTL and sync strategies"""
    
    def get_symbol(self, symbol_id: str) -> UniversalSymbol:
        # 1. Check SQLite cache
        # 2. Validate TTL
        # 3. Fetch from SnapTrade if needed
        # 4. Update cache
        # 5. Return unified model
    
    def batch_sync_symbols(self, symbol_ids: list[str]):
        """Efficient batch operations"""
    
    def schedule_cache_refresh(self):
        """Background sync with SnapTrade"""
```

#### **2.2 Cache Schema Design**
```sql
-- Unified cache tables
CREATE TABLE symbol_cache (
  id TEXT PRIMARY KEY,
  symbol TEXT NOT NULL,
  description TEXT,
  exchange_code TEXT,
  currency_code TEXT,
  cache_timestamp DATETIME,
  cache_expiry DATETIME
);

CREATE TABLE account_cache (
  id TEXT PRIMARY KEY,
  name TEXT,
  institution_name TEXT,
  status TEXT,
  cache_timestamp DATETIME,
  cache_expiry DATETIME
);
```

### **Phase 3: Migration Strategy**

#### **3.1 Gradual Migration Approach**
1. **Parallel Operation**: Run old and new systems side-by-side
2. **API Versioning**: Support both `/v1/` and `/v2/` endpoints
3. **Feature Flags**: Toggle unified models per endpoint
4. **Data Migration**: Populate cache from existing data
5. **Frontend Gradual Update**: Update components one by one

#### **3.2 Risk Mitigation**
- **Fallback Mechanism**: Cache miss → SnapTrade API → Cache update
- **Data Validation**: Compare unified vs original API responses
- **Performance Monitoring**: Track cache hit rates and response times
- **Rollback Strategy**: Quick switch back to original architecture

## 📈 **Expected Benefits**

### **Performance Improvements**
- ⚡ **10x Faster**: Cache-first approach eliminates redundant API calls
- 📊 **Offline Capability**: Work with cached data when API unavailable
- 🔄 **Smart Sync**: Only fetch changed data based on TTL
- 📈 **Scalable**: Handle more users without API rate limits

### **Development Experience**
- 🤖 **Auto-Generated Types**: No manual TypeScript synchronization
- 🔒 **Type Safety**: Guaranteed consistency across all layers
- 🛠️ **Single Source of Truth**: Schema changes propagate automatically
- 📚 **Self-Documenting**: Generated APIs include proper documentation

### **Enterprise Features**
- 📊 **Rich Analytics**: Complex queries on cached historical data
- 🔍 **Audit Trails**: Track all data access and modifications
- 🏢 **Compliance Ready**: Data lineage and retention policies
- 🔐 **Security**: Centralized data access controls

## 🗺️ **Implementation Roadmap**

### **Week 1: Foundation**
- [ ] Create unified schema definition (YAML)
- [ ] Build code generation pipeline
- [ ] Generate initial unified models
- [ ] Create cache service architecture

### **Week 2: Cache Layer**
- [ ] Implement SQLite cache tables
- [ ] Build intelligent cache service
- [ ] Add TTL and sync strategies
- [ ] Create batch operations for performance

### **Week 3: API Integration**
- [ ] Update trading data APIs to use cache
- [ ] Implement fallback mechanisms
- [ ] Add cache health monitoring
- [ ] Performance testing and optimization

### **Week 4: Frontend Migration**
- [ ] Generate and integrate TypeScript interfaces
- [ ] Update React components to use new models
- [ ] Implement optimistic updates
- [ ] End-to-end testing and validation

## 🔗 **Related Documentation**

- [[systemPatterns]] - Current DDD architecture patterns
- [[techContext]] - Technology stack and implementation details
- [[activeContext]] - Current development priorities
- [[progress]] - Implementation progress tracking

---

*This analysis represents a comprehensive strategy to transform our fragmented domain model architecture into a unified, performant, and maintainable system that will scale with our trading platform's growth.*