---
tags: [memory-bank, workflow, guide, process]
project: {PROJECT_NAME}
type: workflow-guide
status: current
priority: medium
workstream: all
created: {DATE}
last-updated: {DATE}
last-action: {DATE}
next-milestone: {NEXT_MILESTONE}
managed-by: obsidian-mcp
related-projects: []
---

# 🔄 {PROJECT_TITLE} - Workflow Guide

*Complete workflow documentation for {PROJECT_NAME} development and maintenance*

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

1. **Dashboard First**: `read_note: projects/{PROJECT_NAME}/memory-bank/dashboard.md`
2. **Complete Context**: `read_multiple_notes: [projects/{PROJECT_NAME}/memory-bank/activeContext, projects/{PROJECT_NAME}/memory-bank/progress, projects/{PROJECT_NAME}/memory-bank/projectbrief, projects/{PROJECT_NAME}/memory-bank/systemPatterns, projects/{PROJECT_NAME}/memory-bank/techContext, projects/{PROJECT_NAME}/memory-bank/productContext]`
3. **Ready for Work**: Full project context recovered in < 30 seconds

### **Context Recovery Sequence**
- **Dashboard** → Current status and navigation
- **activeContext** → Immediate priorities and current work
- **progress** → What's done and what's remaining
- **projectbrief** → Core requirements and scope
- **systemPatterns** → Architecture and design decisions
- **techContext** → Technology stack and tools
- **productContext** → User goals and vision

## 🔧 **Development Workflows**

### **Feature Development Process**
1. **Plan**: Update [[activeContext]] with feature goals
2. **Design**: Document patterns in [[systemPatterns]] if needed
3. **Implement**: Follow architecture guidelines
4. **Test**: Verify against requirements in [[projectbrief]]
5. **Document**: Update [[progress]] with achievements
6. **Update Context**: Modify [[activeContext]] for next priorities

### **Bug Investigation Process**
1. **Document Issue**: Add to [[activeContext]] with priority
2. **Investigate**: Check [[systemPatterns]] and [[techContext]] for context
3. **Root Cause**: Identify underlying cause
4. **Fix**: Implement solution following established patterns
5. **Verify**: Test fix thoroughly
6. **Document**: Update [[progress]] and remove from [[activeContext]]
7. **Prevent**: Add learnings to [[systemPatterns]] if applicable

### **Architecture Decision Process**
1. **Context**: Review [[projectbrief]] requirements
2. **Options**: Evaluate alternatives considering [[techContext]]
3. **Decision**: Choose approach based on project goals
4. **Document**: Add to [[systemPatterns]] with rationale
5. **Implement**: Follow documented decision
6. **Validate**: Ensure decision serves [[productContext]] goals

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
- **[[projects/{PROJECT_NAME}/canvas/system-architecture]]**: Visual system understanding
- **[[projects/{PROJECT_NAME}/canvas/feature-development]]**: Development process visualization
- **[[projects/{PROJECT_NAME}/canvas/issue-resolution]]**: Problem-solving framework

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

## 🚀 **Project-Specific Workflows**

### **{PROJECT_TYPE} Development Patterns**
{PROJECT_SPECIFIC_WORKFLOWS}

### **Technology Stack Workflows**
- **{PRIMARY_LANGUAGE}**: {LANGUAGE_SPECIFIC_PATTERNS}
- **{PRIMARY_FRAMEWORK}**: {FRAMEWORK_SPECIFIC_PATTERNS}
- **{DATABASE_SYSTEM}**: {DATABASE_SPECIFIC_PATTERNS}

### **Testing & Quality Workflows**
- **Unit Testing**: {UNIT_TEST_WORKFLOW}
- **Integration Testing**: {INTEGRATION_TEST_WORKFLOW}
- **Code Review**: {CODE_REVIEW_PROCESS}
- **Deployment**: {DEPLOYMENT_WORKFLOW}

## 🔍 **Troubleshooting Workflows**

### **Context Recovery Issues**
**Problem**: Can't understand current project state
**Solution**: 
1. Read [[dashboard]] for overview
2. Read [[activeContext]] for current focus
3. Check [[progress]] for recent changes
4. Review [[projectbrief]] for foundational context

### **Missing Information**
**Problem**: Needed information not in memory bank
**Solution**:
1. Use `search_vault` to find information across project
2. Check related Canvas files for visual context
3. Update relevant memory bank file with findings

### **Workflow Confusion**
**Problem**: Unclear how to proceed with task
**Solution**:
1. Check [[activeContext]] for current priorities
2. Review [[systemPatterns]] for established approaches
3. Consult [[workflow-guide]] (this file) for process guidance

## 📈 **Success Metrics**

### **Workflow Effectiveness**
- ⚡ **Context Recovery**: < 30 seconds from memory reset to full understanding
- 📋 **Task Clarity**: < 10 seconds to identify current priorities
- 🔄 **Update Speed**: < 2 minutes to update project status
- 🎯 **Process Consistency**: 100% adherence to established workflows

### **Documentation Quality**
- 🔗 **Link Density**: 5+ internal links per memory bank file
- 📊 **Coverage**: All major features and decisions documented
- 🎨 **Visual Aid**: Canvas files provide clear system understanding
- 🔍 **Searchability**: Information easily discoverable via search

## 🔄 **Workflow Evolution**

### **Process Improvement**
- **Regular Review**: Monthly workflow assessment
- **Adaptation**: Modify processes based on project needs
- **Documentation**: Update this guide when workflows change
- **Knowledge Sharing**: Apply learnings to other projects

### **Template Enhancement**
- **Pattern Recognition**: Identify reusable workflow patterns
- **Template Updates**: Improve templates based on real usage
- **Cross-Project Learning**: Share insights between projects

## 🔗 **Related Resources**

### **Project Documentation**
- [[dashboard]] - Central project command center
- [[activeContext]] - Current development priorities
- [[systemPatterns]] - Architecture and design patterns
- [[techContext]] - Technology stack and tools

### **Vault-Wide Resources**
- [[meta/setup-guides/new-project-setup]] - Project initialization guide
- [[meta/vault-overview]] - Multi-project command center
- [[templates/memory-bank/]] - Template system for new projects

---

**🔄 WORKFLOW MASTERY**: Complete process documentation enabling consistent, efficient {PROJECT_NAME} development!

*Enhanced workflow powered by Obsidian native features and proven memory bank methodology*