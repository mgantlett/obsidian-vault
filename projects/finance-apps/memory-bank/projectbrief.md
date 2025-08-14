---
tags: [memory-bank, core, project-brief]
project: finance-apps
type: project-brief
status: stable
priority: critical
workstream: foundation
created: 2025-08-13
last-updated: 2025-08-13
last-action: 2025-08-13
next-milestone: foundation-documentation-complete
managed-by: obsidian-mcp
related-projects: [obsidian-workflow-enhancement]
---

# Project Brief

## Core Requirements and Goals

- **Primary Goal:** To create a Python-based trading bot that trades on Wealthsimple via SnapTrade.
- **Secondary Goals:**
  - Implement various trading strategies.
  - Provide robust backtesting and optimization capabilities.
  - Include portfolio management, lot tracking, and PnL reporting.
  - Integrate with Matrix/Element for human-in-the-loop notifications.
  - Utilize existing trading projects (SnapTrade) to focus on integration rather than building from scratch.

## Scope

- **In Scope:**
  - Trading of ETFs like BTCX.B on TSX.
  - TFSA/RRSP account compliance.
  - Flexible configuration via JSON.
  - Robust backtesting, optimization (Optuna), portfolio management, lot tracking, and PnL reporting (pandas, quantstats).
  - Matrix/Element notifications.
  - Integration with SnapTrade for core brokerage interactions.
- **Out of Scope:**
  - Reinventing core trading functionalities already available in other projects.

## Memory Bank Structure and Organization

The Memory Bank is organized into core documentation files and additional context files. **All files within the Memory Bank (both core and additional context files) are to be read at the beginning of every task and reviewed/updated when explicitly asked to "update memory bank" or when new relevant information is discovered.**

### Core Files (Located in `cline-memory-banks/finance-apps/`):
*   [[projectbrief]] - Foundation document (this file)
*   [[productContext]] - Why this project exists and user goals
*   [[activeContext]] - Current work focus and recent changes
*   [[systemPatterns]] - System architecture and design patterns
*   [[techContext]] - Technologies and development setup
*   [[progress]] - What works, what's left, current status