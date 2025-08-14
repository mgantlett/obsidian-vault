---
tags: [memory-bank, workflow, guide, process]
project: finance-apps
type: workflow-guide
status: current
priority: medium
workstream: all
created: 2025-08-13
last-updated: 2025-08-13
last-action: 2025-08-13
next-milestone: trading-system-optimization
managed-by: obsidian-mcp
related-projects: []
---

# 🔄 Finance Apps - Workflow Guide

*Complete workflow documentation for finance-apps trading bot development and maintenance*

## 🎯 **Memory Bank System Overview**

### **8-File Memory Bank Structure**
This project uses a proven 8-file memory bank system for complete project context:

1. **[[dashboard]]** - Central command center with live status and navigation
2. **[[activeContext]]** - Current development focus and immediate priorities  
3. **[[progress]]** - Achievement tracking and milestone documentation
4. **[[projectbrief]]** - Project foundation, scope, and requirements
5. **[[systemPatterns]]** - Architecture patterns and design decisions
6. **[[techContext]]** - Technology stack and implementation details
7. **[[productContext]]** - User experience and product vision
8. **[[workflow-guide]]** - This file - workflow processes and procedures

### **File Hierarchy & Dependencies**
```
projectbrief.md     (Foundation)
    ├── productContext.md
    ├── systemPatterns.md  
    └── techContext.md
            ↓
    activeContext.md    (Current State)
            ↓
    progress.md         (Achievements)
            ↓
    dashboard.md        (Live Overview)
            ↓
    workflow-guide.md   (This File)
```

## ⚡ **Critical Startup Protocol**

### **For Every New Session (Memory Reset)**
**🎯 I MUST read the dashboard first, then ALL memory bank files at start of EVERY task**

1. **Dashboard First**: `read_note: projects/finance-apps/memory-bank/dashboard.md`
2. **Complete Context**: `read_multiple_notes: [projects/finance-apps/memory-bank/activeContext, projects/finance-apps/memory-bank/progress, projects/finance-apps/memory-bank/projectbrief, projects/finance-apps/memory-bank/systemPatterns, projects/finance-apps/memory-bank/techContext, projects/finance-apps/memory-bank/productContext]`
3. **Ready for Work**: Full project context recovered in < 30 seconds

### **Context Recovery Sequence**
- **Dashboard** → Current status and navigation
- **activeContext** → Immediate priorities and current work
- **progress** → What's done and what's remaining
- **projectbrief** → Core requirements and scope
- **systemPatterns** → Architecture and design decisions
- **techContext** → Technology stack and tools
- **productContext** → User goals and vision

## 🔧 **Trading System Development Workflows**

### **Strategy Development Process**
1. **Research**: Analyze market patterns and identify strategy opportunities
2. **Design**: Document strategy logic in [[systemPatterns]]
3. **Implement**: Create strategy following architecture guidelines
4. **Backtest**: Test strategy using VectorBT and Event-Driven engines
5. **Optimize**: Use Optuna for parameter optimization
6. **Document**: Update [[progress]] with results and [[activeContext]] with next steps

### **System Integration Process**
1. **Plan Integration**: Update [[activeContext]] with integration goals
2. **API Design**: Document interfaces in [[systemPatterns]]
3. **Implement**: Follow markbot ↔ spendviz architecture patterns
4. **Test Endpoints**: Verify SnapTrade API connections
5. **UI Integration**: Connect SpendViz frontend to backend services
6. **Document**: Update [[progress]] and modify [[activeContext]] for next priorities

### **Bug Investigation Process**
1. **Document Issue**: Add to [[activeContext]] with priority level
2. **Investigate**: Check [[systemPatterns]] and [[techContext]] for context
3. **Reproduce**: Create test cases to isolate the problem
4. **Root Cause**: Identify underlying cause using system knowledge
5. **Fix**: Implement solution following established patterns
6. **Verify**: Test fix against all affected components
7. **Document**: Update [[progress]] and remove from [[activeContext]]
8. **Prevent**: Add learnings to [[systemPatterns]] if applicable

### **Performance Optimization Process**
1. **Identify Bottlenecks**: Use profiling and monitoring data
2. **Analyze**: Review [[systemPatterns]] for optimization opportunities
3. **Design Solution**: Consider impact on overall architecture
4. **Implement**: Apply optimizations following best practices
5. **Benchmark**: Measure performance improvements
6. **Document**: Update [[techContext]] with optimization details

## 📊 **Memory Bank Update Workflows**

### **When to Update Memory Bank Files**

#### **Daily Updates**
- **[[activeContext]]**: After significant progress or priority changes
- **[[progress]]**: When features/tasks are completed

#### **Weekly Updates**
- **[[dashboard]]**: Review and update status information
- **[[systemPatterns]]**: Add new patterns or architectural insights

#### **As Needed Updates**
- **[[projectbrief]]**: When scope or requirements change
- **[[techContext]]**: When adding new technologies or tools
- **[[productContext]]**: When user requirements evolve
- **[[workflow-guide]]**: When processes improve or change

### **Memory Bank Update Process**
1. **Identify Changes**: What new information needs to be documented?
2. **Choose Files**: Which memory bank files need updates?
3. **Update Content**: Make specific, clear updates
4. **Cross-Reference**: Ensure links between files remain accurate
5. **Validate**: Check that updates serve future context recovery

## 🎨 **Obsidian Integration Workflows**

### **Canvas Usage**
- **[[projects/finance-apps/canvas/system-architecture]]**: Visual markbot ↔ spendviz integration
- **[[projects/finance-apps/canvas/strategy-development]]**: Strategy development process visualization
- **[[projects/finance-apps/canvas/issue-resolution]]**: Debugging and problem-solving framework

### **MCP Tool Usage**
- **read_note**: Read single memory bank files
- **read_multiple_notes**: Efficient batch reading for context recovery
- **update_note**: Make targeted updates to memory bank files
- **search_vault**: Find information across all project documentation
- **create_note**: Add new documentation when needed

### **Cross-Project Navigation**
- **[[meta/vault-overview]]**: Multi-project dashboard
- **[[meta/project-index]]**: Directory of all projects
- **Templates**: [[templates/memory-bank/]] for new project setup

## 🚀 **Trading Platform Specific Workflows**

### **Python+FastAPI Development Patterns**
- **API Endpoints**: RESTful design following FastAPI conventions
- **Data Models**: Pydantic models for request/response validation
- **Database Integration**: SQLAlchemy ORM patterns
- **Testing**: Pytest with fixture patterns for API testing

### **Technology Stack Workflows**
- **Python**: Follow PEP 8, use type hints, async/await patterns
- **FastAPI**: Dependency injection, automatic API documentation
- **React**: Component-based architecture, hooks patterns
- **SQLite**: Database migrations with Alembic

### **Trading System Workflows**
- **Strategy Testing**: VectorBT for vectorized backtesting
- **Parameter Optimization**: Optuna for hyperparameter tuning
- **Data Management**: Efficient candle and lot data storage
- **API Integration**: SnapTrade API for live trading data

## 🔍 **Troubleshooting Workflows**

### **Context Recovery Issues**
**Problem**: Can't understand current project state
**Solution**: 
1. Read [[dashboard]] for overview
2. Read [[activeContext]] for current focus
3. Check [[progress]] for recent changes
4. Review [[projectbrief]] for foundational context

### **Trading System Issues**
**Problem**: Strategy performance problems
**Solution**:
1. Check [[systemPatterns]] for architecture constraints
2. Review [[techContext]] for technology limitations
3. Use [[progress]] to understand what has been tested
4. Update [[activeContext]] with investigation findings

### **Integration Issues**
**Problem**: API connectivity or data flow problems
**Solution**:
1. Check [[systemPatterns]] for integration architecture
2. Review [[techContext]] for API configuration
3. Test individual components following established patterns
4. Document findings in [[activeContext]]

## 📈 **Success Metrics**

### **Workflow Effectiveness**
- ⚡ **Context Recovery**: < 30 seconds from memory reset to full understanding
- 📋 **Task Clarity**: < 10 seconds to identify current priorities
- 🔄 **Update Speed**: < 2 minutes to update project status
- 🎯 **Process Consistency**: 100% adherence to established workflows

### **Trading System Quality**
- 📊 **Strategy Performance**: Consistent Sharpe ratio improvements
- 🔧 **System Reliability**: 99%+ uptime for trading operations
- ⚡ **Response Times**: < 100ms for API endpoints
- 🎯 **Test Coverage**: > 90% code coverage for critical components

## 🔄 **Workflow Evolution**

### **Process Improvement**
- **Regular Review**: Monthly workflow assessment
- **Adaptation**: Modify processes based on trading system needs
- **Documentation**: Update this guide when workflows change
- **Knowledge Sharing**: Apply learnings to other trading projects

### **Trading System Enhancement**
- **Strategy Development**: Continuous improvement of trading algorithms
- **Performance Optimization**: Regular system performance reviews
- **Risk Management**: Enhanced position sizing and risk controls
- **User Experience**: Ongoing improvement of SpendViz interface

## 🔗 **Related Resources**

### **Project Documentation**
- [[dashboard]] - Central project command center
- [[activeContext]] - Current development priorities
- [[systemPatterns]] - Architecture and design patterns
- [[techContext]] - Technology stack and tools
- [[progress]] - Trading system development progress
- [[productContext]] - User goals and trading platform vision

### **Vault-Wide Resources**
- [[meta/setup-guides/new-project-setup]] - Project initialization guide
- [[meta/vault-overview]] - Multi-project command center
- [[templates/memory-bank/]] - Template system for new projects

### **External Documentation**
- **SnapTrade API**: Trading data and execution
- **VectorBT**: Backtesting framework
- **Optuna**: Hyperparameter optimization
- **FastAPI**: Web framework documentation

---

**🔄 TRADING WORKFLOW MASTERY**: Complete process documentation enabling consistent, efficient finance-apps development!

*Enhanced workflow powered by Obsidian native features and proven memory bank methodology*