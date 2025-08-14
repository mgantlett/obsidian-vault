---
tags: [meta, vault, overview, multi-project]
type: vault-overview
status: active
priority: critical
created: 2025-08-13
last-updated: 2025-08-13
managed-by: obsidian-mcp
---

# 🏛️ Development Vault Overview

*Central command center for all development projects and workflows*

## 🎯 **Active Projects**

```dataview
TABLE WITHOUT ID
  "📁 " + file.link as "Project",
  status as "Status",
  priority as "Priority",
  last-updated as "Last Updated",
  next-milestone as "Next Milestone"
FROM "projects"
WHERE type = "dashboard" OR contains(file.name, "dashboard")
SORT priority DESC, last-updated DESC
```

## 📊 **Project Health Overview**

### **Active Development**
```dataview
LIST
FROM "projects"
WHERE (type = "active-context" OR contains(file.name, "activeContext")) AND status != "completed"
SORT last-updated DESC
```

### **Recently Updated**
```dataview
TABLE WITHOUT ID
  file.link as "File",
  split(file.folder, "/")[1] as "Project",
  last-updated as "Updated"
FROM "projects"
SORT last-updated DESC
LIMIT 10
```

## 🎨 **Cross-Project Resources**

### **Universal Templates**
- **[[templates/project-setup/new-project-initialization]]** - Complete project setup guide
- **[[templates/memory-bank-templates/dashboard]]** - Generic dashboard template
- **[[templates/memory-bank-templates/activeContext]]** - Generic active context template
- **[[templates/workflow-templates/feature-development]]** - Feature planning template
- **[[templates/workflow-templates/bug-investigation]]** - Bug resolution template
- **[[templates/universal-workflow/local-workspace/custom-instructions]]** - Generic custom instructions template

### **Shared Knowledge Base**
- **[[shared/best-practices/development-standards]]** - Cross-project development standards
- **[[shared/best-practices/obsidian-workflow]]** - Workflow optimization techniques
- **[[shared/tools-and-configs/obsidian-setup]]** - Vault setup and configuration

## 🔍 **Quick Navigation**

### **Project Dashboards**
```dataview
TABLE WITHOUT ID
  "🎛️ [" + split(file.folder, "/")[1] + " Dashboard](" + file.path + ")" as "Access",
  "📅 " + last-updated as "Last Updated"
FROM "projects"
WHERE type = "dashboard" OR contains(file.name, "dashboard")
SORT file.folder ASC
```

### **Active Tasks Across All Projects**
```dataview
TASK
FROM "projects"
WHERE !completed
GROUP BY split(file.folder, "/")[1]
SORT priority DESC
```

## 📈 **Vault Analytics**

### **Project Activity Metrics**
```dataview
TABLE WITHOUT ID
  split(file.folder, "/")[1] as "Project",
  length(filter(file.lists, (t) => t.task)) as "Total Tasks",
  length(filter(file.lists, (t) => t.task AND t.completed)) as "Completed",
  length(filter(file.lists, (t) => t.task AND !t.completed)) as "Remaining"
FROM "projects"
WHERE file.lists
GROUP BY split(file.folder, "/")[1]
SORT "Remaining" DESC
```

### **Documentation Coverage**
```dataview
TABLE WITHOUT ID
  split(file.folder, "/")[1] as "Project",
  length(file.outlinks) as "Internal Links",
  length(file.inlinks) as "Backlinks",
  file.size as "Content Size"
FROM "projects"
WHERE type = "project-brief" OR contains(file.name, "projectbrief")
SORT "Internal Links" DESC
```

## 🚀 **Workflow Efficiency**

### **Template Usage**
- **Feature Templates Used**: Count of features following standardized template
- **Bug Templates Used**: Count of bugs following investigation template
- **Canvas Utilization**: Projects using visual management
- **Cross-Linking Density**: Average internal links per memory bank file

### **Success Metrics**
- ⚡ **Context Switch Time**: < 30 seconds to any project understanding
- 📋 **Project Discovery**: < 10 seconds to find relevant project info
- 🔄 **Status Updates**: < 2 minutes to update any project status
- 🎯 **Template Compliance**: 100% of projects using standardized workflows

## 🔧 **Vault Management**

### **Setup Guides**
- **[[meta/setup-guides/obsidian-requirements]]** - Plugin setup and requirements
- **[[meta/setup-guides/project-initialization]]** - New project setup checklist
- **[[meta/setup-guides/template-customization]]** - Template adaptation guide

### **Maintenance Tasks**
- [ ] Weekly: Update project statuses and priorities
- [ ] Monthly: Review and update universal templates
- [ ] Quarterly: Optimize Dataview queries and vault performance
- [ ] As needed: Add new project folders and initialize memory banks

## 🎯 **Quick Actions**

### **Start New Project**
1. **Copy Custom Instructions**: From [[meta/setup-guides/custom-instructions-template]]
2. **Customize Variables**: Replace project name, type, and tech stack
3. **Instruct Cline**: "Follow custom instructions" (auto-detects new project setup)
4. **Automatic Setup**: Cline reads [[meta/setup-guides/new-project-setup]] and creates complete 8-file structure
5. **Validation**: < 5 minutes to fully functional project workflow system

### **Switch Project Context**
1. Open target project dashboard: `projects/{project-name}/memory-bank/dashboard.md`
2. Review active context: `projects/{project-name}/memory-bank/activeContext.md`
3. Check recent progress: `projects/{project-name}/memory-bank/progress.md`
4. Access visual maps: `projects/{project-name}/canvas/`

## 🔗 **Related Resources**

- **[[templates/universal-workflow/README]]** - Complete workflow system documentation
- **[[shared/best-practices/multi-project-management]]** - Managing multiple projects effectively
- **[[meta/project-index]]** - Detailed project directory and descriptions

---

**🎛️ VAULT COMMAND CENTER**: Your gateway to efficient multi-project development workflow management!

*Powered by Obsidian Dataview - automatically aggregating insights across all development projects*