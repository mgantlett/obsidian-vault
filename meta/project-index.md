---
tags: [meta, project-index, navigation]
type: project-index
status: active
priority: high
created: 2025-08-13
last-updated: 2025-08-13
managed-by: obsidian-mcp
---

# 📁 Project Index

*Comprehensive directory of all development projects in the vault*

## 🎯 **Active Projects**

### **Finance Apps** 📈
- **Type**: Trading Bot & Financial Analytics
- **Status**: Active Development
- **Technologies**: Python (Flask, SnapTrade), React (TypeScript), SQLite
- **Command Center**: [[projects/finance-apps/memory-bank/dashboard]]
- **Description**: Automated trading bot with web interface, strategy optimization, and portfolio management

**Quick Access:**
- 🎛️ **Dashboard**: [[projects/finance-apps/memory-bank/dashboard]]
- 📋 **Current Focus**: [[projects/finance-apps/memory-bank/activeContext]]
- 📊 **Progress**: [[projects/finance-apps/memory-bank/progress]]
- 🏗️ **Architecture**: [[projects/finance-apps/memory-bank/systemPatterns]]
- 🎨 **Visual Maps**: [[projects/finance-apps/canvas/system-architecture]]

---

## 📋 **Project Template Structure**

### **Standard Project Layout**
```
projects/{project-name}/
├── memory-bank/                    # Core documentation
│   ├── dashboard.md               # Project command center
│   ├── activeContext.md           # Current priorities
│   ├── progress.md                # Achievement tracking
│   ├── projectbrief.md            # Foundation document
│   ├── systemPatterns.md          # Architecture patterns
│   ├── techContext.md             # Technology stack
│   ├── productContext.md          # User goals
│   └── workflow-guide.md          # Project-specific procedures
└── canvas/                        # Visual project maps
    ├── system-architecture.canvas # System overview
    ├── feature-development.canvas # Development workflow
    └── issue-resolution.canvas   # Problem-solving process
```

### **Local Workspace Integration**
Each project should have:
- **`.clinerules/custom-instructions.md`** - Cline workspace configuration
- **Project-specific references** to vault paths
- **MCP integration** for seamless Obsidian access

## 🌟 **Universal Resources**

### **Templates** 📝
- **[[templates/workflow-templates/feature-development]]** - Feature planning template
- **[[templates/workflow-templates/bug-investigation]]** - Bug resolution template
- **[[templates/universal-workflow/README]]** - Complete workflow system
- **[[templates/universal-workflow/local-workspace/custom-instructions]]** - Generic custom-instructions template

### **Canvas Templates** 🎨
- **System Architecture** - Visual system overview template
- **Feature Development** - Development workflow template
- **Issue Resolution** - Problem-solving process template

### **Setup Guides** 🔧
- **[[meta/setup-guides/obsidian-requirements]]** - Plugin setup and requirements
- **[[meta/setup-guides/project-initialization]]** - New project setup checklist
- **[[meta/setup-guides/template-customization]]** - Template adaptation guide

## 🚀 **Quick Actions**

### **Start New Project**
1. **Create project folder**: `projects/{project-name}/`
2. **Copy memory bank templates** from `templates/memory-bank-templates/`
3. **Copy canvas templates** from `templates/canvas-templates/`
4. **Customize project-specific content**
5. **Create local custom-instructions** from template
6. **Update project index** with new project details

### **Switch Between Projects**
1. **Use vault overview**: [[meta/vault-overview]] for multi-project dashboard
2. **Direct project access**: Navigate to `projects/{project-name}/memory-bank/dashboard.md`
3. **Update local custom-instructions** to point to target project
4. **Leverage cross-project templates** and shared resources

## 📊 **Project Analytics**

### **Project Comparison Matrix**
```dataview
TABLE WITHOUT ID
  split(file.folder, "/")[1] as "Project",
  status as "Status",
  priority as "Priority",
  last-updated as "Last Updated"
FROM "projects"
WHERE type = "dashboard" OR contains(file.name, "dashboard")
SORT priority DESC, last-updated DESC
```

### **Cross-Project Task Summary**
```dataview
TABLE WITHOUT ID
  split(file.folder, "/")[1] as "Project",
  length(filter(file.lists, (t) => t.task AND !t.completed)) as "Open Tasks",
  length(filter(file.lists, (t) => t.task AND t.completed)) as "Completed Tasks"
FROM "projects"
WHERE file.lists
GROUP BY split(file.folder, "/")[1]
SORT "Open Tasks" DESC
```

## 🎯 **Project Categories**

### **By Technology Stack**
- **Python Projects**: finance-apps
- **Web Applications**: finance-apps (spendviz)
- **Mobile Apps**: (future projects)
- **DevOps/Infrastructure**: (future projects)

### **By Development Stage**
- **Active Development**: finance-apps
- **Maintenance Mode**: (none currently)
- **Archived Projects**: (none currently)
- **Planned Projects**: (TBD)

### **By Domain**
- **Financial Technology**: finance-apps
- **Web Development**: (future projects)
- **Data Analytics**: (future projects)
- **Machine Learning**: (future projects)

## 🔗 **Navigation Shortcuts**

### **Quick Project Access**
- **Finance Apps**: [[projects/finance-apps/memory-bank/dashboard]]
- **New Project Setup**: [[templates/universal-workflow/README]]
- **Vault Management**: [[meta/vault-overview]]

### **Template Library**
- **Feature Development**: [[templates/workflow-templates/feature-development]]
- **Bug Investigation**: [[templates/workflow-templates/bug-investigation]]
- **Custom Instructions**: [[templates/universal-workflow/local-workspace/custom-instructions]]

### **Setup & Configuration**
- **Obsidian Setup**: [[meta/setup-guides/obsidian-requirements]]
- **Project Initialization**: [[meta/setup-guides/project-initialization]]
- **Template Customization**: [[meta/setup-guides/template-customization]]

---

**📁 PROJECT INDEX**: Your comprehensive guide to navigating and managing multiple development projects efficiently!

*Multi-project vault structure - scalable, organized, and optimized for cross-project learning and resource sharing*