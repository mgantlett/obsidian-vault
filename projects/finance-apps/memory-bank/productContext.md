---
tags: [memory-bank, core, product, user-goals]
project: finance-apps
type: product-context
status: current
priority: medium
workstream: product
created: 2025-08-13
last-updated: 2025-08-13
last-action: 2025-08-13
next-milestone: user-experience-enhancement
managed-by: obsidian-mcp
related-projects: [obsidian-workflow-enhancement]
---

# Product Context

## Problem Statement

The project aims to create a sophisticated, Python-based trading bot that leverages the [[snaptrade]] API for trading on various brokerage platforms, including **Wealthsimple**. The primary challenge is to ensure robust and direct integration with SnapTrade while building a highly customizable and feature-rich automated trading system.

### Core Problems Addressed

1. **Manual Trading Inefficiency**: Eliminate time-consuming manual trading decisions
2. **Emotional Trading**: Remove human emotion from trading decisions through algorithmic strategies
3. **Backtesting Complexity**: Provide sophisticated backtesting without building infrastructure from scratch
4. **Portfolio Management**: Automate portfolio tracking, lot management, and P&L reporting
5. **Integration Challenges**: Seamlessly connect with existing brokerage systems via SnapTrade

## User Goals

### Primary User Objectives

Users want a trading bot that can:

#### 🎯 **Core Trading Capabilities**
- **ETF Trading**: Trade ETFs like `BTCX.B` on TSX within TFSA/RRSP accounts
- **Strategy Flexibility**: Implement and customize various [[trading-strategies]]
- **Account Compliance**: Ensure TFSA/RRSP account regulation compliance
- **Multi-Asset Support**: Handle stocks, ETFs, and crypto through unified interface

#### ⚙️ **Configuration & Customization**
- **JSON Configuration**: Flexible strategy and system configuration via JSON files
- **Parameter Tuning**: Adjust strategy parameters without code changes
- **Environment Setup**: Easy development and production environment management
- **Template System**: Reusable configuration templates for different strategies

#### 📊 **Analysis & Optimization**
- **Backtesting Engine**: Robust historical performance testing
- **Strategy Optimization**: [[optuna]] integration for hyperparameter optimization
- **Performance Analytics**: Comprehensive metrics via [[quantstats]] integration
- **Comparative Analysis**: Side-by-side strategy performance comparison

#### 💼 **Portfolio Management**
- **Lot Tracking**: Detailed lot-level position tracking
- **P&L Reporting**: Real-time and historical profit/loss analysis
- **Risk Management**: Portfolio-level risk assessment and controls
- **Position Sizing**: Automated position sizing based on risk parameters

#### 🔔 **Human-in-the-Loop Integration**
- **Matrix/Element Notifications**: Real-time alerts for trading decisions
- **Manual Intervention**: Ability to pause, override, or modify automated decisions
- **Approval Workflows**: Configure which decisions require human approval
- **Status Monitoring**: Real-time system health and trading status updates

### Secondary User Objectives

#### 🔗 **Integration & Connectivity**
- **SnapTrade Integration**: Leverage existing SnapTrade infrastructure vs building from scratch
- **Multi-Broker Support**: Future expansion to additional brokers through SnapTrade
- **API Accessibility**: RESTful API for third-party integrations
- **Web Interface**: User-friendly web dashboard via [[spendviz]] integration

#### 🛠️ **Development & Maintenance**
- **Code Quality**: Type-safe, well-documented, maintainable codebase
- **Testing Framework**: Comprehensive unit and integration testing
- **Deployment Automation**: Docker-based deployment with minimal setup
- **Documentation**: Clear documentation for configuration and extension

## User Experience Vision

### 🎨 **Intended User Journey**

1. **Setup & Configuration**
   - Quick Docker Compose setup
   - JSON-based strategy configuration
   - SnapTrade account linking
   - Test connection verification

2. **Strategy Development**
   - Choose from pre-built strategies ([[rsi-strategy]], [[momentum-strategy]], [[trend-following-strategy]])
   - Customize parameters via configuration files
   - Backtest strategies with historical data
   - Optimize parameters using [[optuna]]

3. **Deployment & Monitoring**
   - Deploy strategies to live trading
   - Monitor performance via [[command-center]] web interface
   - Receive notifications via Matrix/Element
   - Review and approve critical decisions

4. **Analysis & Improvement**
   - Analyze performance via detailed reports
   - Compare strategy effectiveness
   - Adjust parameters based on results
   - Scale successful strategies

### 🏆 **Success Criteria**

#### **Usability Metrics**
- ⏱️ **Setup Time**: < 30 minutes from clone to first backtest
- 🎯 **Strategy Deployment**: < 5 minutes to deploy new strategy
- 📊 **Performance Visibility**: Real-time dashboard with key metrics
- 🔔 **Alert Response**: < 1 minute notification delivery

#### **Reliability Metrics**
- 🔄 **System Uptime**: 99.5% availability during market hours
- 🛡️ **Error Recovery**: Automatic recovery from transient failures
- 💾 **Data Integrity**: Zero data loss in order and position tracking
- 🔐 **Security**: Secure credential management and API access

#### **Performance Metrics**
- 📈 **Strategy Performance**: Consistently profitable strategies
- ⚡ **Execution Speed**: < 2 second order execution time
- 🧠 **Optimization Quality**: Improved Sharpe ratios through parameter tuning
- 📊 **Reporting Accuracy**: 100% accurate P&L and position tracking

### 🎭 **User Personas**

#### **Primary Persona: Algorithmic Trader**
- **Background**: Experienced in manual trading, wants automation
- **Goals**: Reduce emotional decisions, scale trading strategies
- **Pain Points**: Time-consuming manual analysis, missed opportunities
- **Technical Level**: Comfortable with JSON configuration, basic Python

#### **Secondary Persona: Quantitative Analyst**
- **Background**: Strong mathematical/statistical background
- **Goals**: Develop and test sophisticated trading algorithms
- **Pain Points**: Infrastructure complexity, backtesting limitations
- **Technical Level**: Advanced Python, statistical modeling expertise

#### **Tertiary Persona: Casual Investor**
- **Background**: Limited trading experience, wants passive income
- **Goals**: Simple, reliable automated trading
- **Pain Points**: Complexity of existing solutions, lack of guidance
- **Technical Level**: Basic computer skills, prefers GUI interfaces

## Integration Philosophy

### 🔄 **"Don't Reinvent the Wheel" Principle**

The project philosophy emphasizes leveraging existing, proven solutions rather than building from scratch:

- **SnapTrade API**: Core brokerage integration instead of direct broker APIs
- **VectorBT**: Professional backtesting engine vs custom implementation
- **Optuna**: Industry-standard optimization vs custom algorithms
- **Quantstats**: Proven analytics vs custom metrics
- **SQLAlchemy**: Mature ORM vs custom database layer

### 🎯 **Focus Areas**

**What We Build:**
- Strategy implementation and orchestration
- User experience and interface design
- Configuration and deployment automation
- Integration glue between existing tools
- Domain-specific business logic

**What We Integrate:**
- Market data feeds (YFinance, SnapTrade)
- Execution infrastructure (SnapTrade)
- Analytics engines (VectorBT, Quantstats)
- Optimization frameworks (Optuna)
- Notification systems (Matrix/Element)

## 🔗 **Related Documentation**

- [[projectbrief]] - Core requirements and project scope
- [[systemPatterns]] - Technical architecture supporting user goals
- [[techContext]] - Technology choices aligned with user needs
- [[activeContext]] - Current development priorities
- [[progress]] - Achievement of user-facing features

---

*Product context enhanced with Obsidian linking for better understanding of user journey and system relationships*