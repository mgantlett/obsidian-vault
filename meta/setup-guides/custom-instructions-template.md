---
tags: [template, setup, custom-instructions]
type: template
status: active
priority: high
created: 2025-08-13
last-updated: 2025-08-13
managed-by: obsidian-mcp
---

# Smart Custom Instructions Template for Projects

*Copy this file to your project's `.clinerules/custom-instructions.md` and customize*

## 📋 **Instructions for Use**

1. **Copy this file** to `{PROJECT_PATH}/.clinerules/custom-instructions.md`
2. **Replace all placeholders** (items in `{BRACKETS}`) with actual project values
3. **Tell Cline**: "Follow custom instructions" (workflow auto-detected)
4. **Cline automatically detects**: New project setup vs. existing project workflow

---

# {PROJECT_NAME} Cline Configuration

## 🎯 **Project Variables**
- **PROJECT_NAME**: {PROJECT_NAME}
- **PROJECT_TITLE**: {PROJECT_TITLE}
- **PROJECT_TYPE**: {PROJECT_TYPE} # Options: web-app, mobile-app, data-science, api-service, desktop-app, cli-tool
- **PRIMARY_TECH_STACK**: {PRIMARY_TECH_STACK} # e.g., React+Node.js, Python+FastAPI, Flutter, etc.
- **PRIMARY_LANGUAGE**: {PRIMARY_LANGUAGE}

## 📍 **Memory Bank Location**
**Primary**: `projects/{PROJECT_NAME}/memory-bank/`  
**Dashboard**: `projects/{PROJECT_NAME}/memory-bank/dashboard.md`

## 🔄 **Smart Workflow Detection**

### **IF Memory Bank Exists (Ongoing Development)**
⚡ **Critical Startup Protocol - I MUST read dashboard first, then ALL memory bank files at start of EVERY task**

1. **Dashboard First**: `read_note: projects/{PROJECT_NAME}/memory-bank/dashboard.md`
2. **Complete Context**: `read_multiple_notes: [projects/{PROJECT_NAME}/memory-bank/activeContext, projects/{PROJECT_NAME}/memory-bank/progress, projects/{PROJECT_NAME}/memory-bank/projectbrief, projects/{PROJECT_NAME}/memory-bank/systemPatterns, projects/{PROJECT_NAME}/memory-bank/techContext, projects/{PROJECT_NAME}/memory-bank/productContext, projects/{PROJECT_NAME}/memory-bank/workflow-guide]`
3. **Follow Workflow**: Use workflow-guide.md for development processes
4. **Context Recovery**: < 30 seconds to full project understanding

### **IF Memory Bank Missing (New Project Setup)**
🚀 **Project Initialization Protocol**

1. **Read Setup Guide**: `read_note: meta/setup-guides/new-project-setup`
2. **Follow Step-by-Step**: Complete project initialization process
3. **Initialize Memory Bank**: Create all 8 memory bank files with project customization
4. **Setup Canvas**: Create visual project maps
5. **Validate Setup**: Ensure dashboard and linking work correctly

## 🔧 **Obsidian MCP Tools Available - REQUIRED FOR MANAGING MEMORY BANK**
- **read_note**: Read single note (`path`)
- **read_multiple_notes**: Read multiple notes efficiently (`paths[]`)
- **update_note**: Update existing content (`path`, `edits[]`, `dryRun`)
- **create_note**: Create new notes (`path`, `content`)
- **search_vault**: Search across all content (`query`)
- **list_notes**: List vault contents (`folder?`)
- **manage_folder**: Folder operations (`operation`, `path`, `newPath?`)
- **move_note**: Move/rename notes (`sourcePath`, `destinationPath`)
- **delete_note**: Delete notes (`path`)
- **auto_backlink_vault**: Auto-link content (`dryRun`, `excludePatterns[]`, etc.)

## 📊 **Memory Bank System (8 Files)**
1. **dashboard.md** - Central command center with live status
2. **activeContext.md** - Current development focus and priorities
3. **progress.md** - Achievement tracking and milestones
4. **projectbrief.md** - Project scope, requirements, and foundation
5. **systemPatterns.md** - Architecture patterns and design decisions
6. **techContext.md** - Technology stack and implementation details
7. **productContext.md** - User experience and product vision
8. **workflow-guide.md** - Development processes and procedures

## 🎯 **Quick Context Recovery (30-second rule)**
**For New Sessions**: Dashboard → activeContext → workflow-guide → current task focus  
**For Deep Work**: Follow memory bank hierarchy as documented in dashboard

---

**🎯 SMART WORKFLOW**: Auto-detects project state and follows appropriate workflow for maximum efficiency!