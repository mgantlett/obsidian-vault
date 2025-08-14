---
tags: [memory-bank, dashboard, overview]
project: {PROJECT_NAME}
type: dashboard
status: current
priority: critical
workstream: all
created: {DATE}
last-updated: {DATE}
last-action: {DATE}
next-milestone: project-setup-completion
managed-by: obsidian-mcp
related-projects: []
---

# 🎛️ {PROJECT_TITLE} Command Dashboard

*Central command center for the {PROJECT_NAME} project*

## 🎯 **Current Status Overview**

```dataview
TABLE WITHOUT ID
  file.link as "Area",
  status as "Status",
  priority as "Priority",
  workstream as "Workstream",
  next-milestone as "Next Milestone",
  last-updated as "Last Updated"
FROM "projects/{PROJECT_NAME}/memory-bank"
WHERE type != "dashboard"
SORT priority DESC, last-updated DESC
```

## 📋 **Active Tasks & Next Steps**

### **Critical Priority Items**
```dataview
LIST
FROM "projects/{PROJECT_NAME}/memory-bank"
WHERE priority = "critical" AND status != "completed"
SORT last-updated DESC
```

### **High Priority Items**
```dataview
LIST
FROM "projects/{PROJECT_NAME}/memory-bank"
WHERE priority = "high" AND status != "completed"
SORT last-updated DESC
```

## 🔄 **Recent Activity**

```dataview
TABLE WITHOUT ID
  file.link as "File",
  last-action as "Last Action",
  last-updated as "Updated"
FROM "projects/{PROJECT_NAME}/memory-bank"
SORT last-updated DESC
LIMIT 5
```

## 🏗️ **Workstream Status**

### **Backend Development**
```dataview
LIST
FROM "projects/{PROJECT_NAME}/memory-bank"
WHERE workstream = "backend" OR workstream = "all"
```

### **Frontend Development**
```dataview
LIST
FROM "projects/{PROJECT_NAME}/memory-bank"
WHERE workstream = "frontend" OR workstream = "all"
```

### **Integration & Testing**
```dataview
LIST
FROM "projects/{PROJECT_NAME}/memory-bank"
WHERE workstream = "integration" OR workstream = "all"
```

### **Optimization & Enhancement**
```dataview
LIST
FROM "projects/{PROJECT_NAME}/memory-bank"
WHERE workstream = "optimization" OR workstream = "all"
```

## 📊 **Project Health Metrics**

### **Completion Status**
- **Completed Systems**: ✅ {LIST_COMPLETED_FEATURES}
- **Active Development**: 🔄 {CURRENT_FOCUS_AREAS}
- **Planned Features**: 📅 {UPCOMING_FEATURES}

### **Technical Debt Items**
- [ ] {TECHNICAL_DEBT_ITEM_1}
- [ ] {TECHNICAL_DEBT_ITEM_2}
- [ ] {TECHNICAL_DEBT_ITEM_3}

## 🎯 **Strategic Focus Areas**

### **Current Sprint Focus**
1. **{FOCUS_AREA_1}** - {FOCUS_DESCRIPTION_1}
2. **{FOCUS_AREA_2}** - {FOCUS_DESCRIPTION_2}
3. **{FOCUS_AREA_3}** - {FOCUS_DESCRIPTION_3}
4. **{FOCUS_AREA_4}** - {FOCUS_DESCRIPTION_4}

### **Next Sprint Candidates**
- {NEXT_SPRINT_ITEM_1}
- {NEXT_SPRINT_ITEM_2}
- {NEXT_SPRINT_ITEM_3}
- {NEXT_SPRINT_ITEM_4}

## 🔗 **Quick Navigation**

### **Core Memory Bank Files**
- [[projectbrief]] - Foundation and scope
- [[activeContext]] - Current development focus
- [[progress]] - Achievements and milestones
- [[systemPatterns]] - Architecture and design
- [[techContext]] - Technology stack
- [[productContext]] - User goals and vision
- [[workflow-guide]] - Workflow procedures

### **Related Projects**
- Currently focused on {PROJECT_NAME} development

## 🧠 **Context Switching Guide**

### **For Fresh Memory Reset**
1. **Start Here**: Read this dashboard for current status
2. **Get Context**: Review [[activeContext]] for immediate priorities
3. **Understand Scope**: Check [[projectbrief]] for project boundaries
4. **Check Progress**: Review [[progress]] for recent accomplishments
5. **Deep Dive**: Read relevant technical docs ([[systemPatterns]], [[techContext]])

### **For Specific Workstreams**
- **Backend Work**: [[systemPatterns]] → [[techContext]] → [[activeContext]]
- **Frontend Work**: [[productContext]] → [[systemPatterns]] → [[activeContext]]
- **Integration**: [[systemPatterns]] → [[progress]] → [[activeContext]]
- **Documentation**: [[workflow-guide]] → [[activeContext]] → relevant docs

## 🎨 **Visual Project Map**

### **Interactive Canvas Views** ✅ LIVE
- **[[projects/{PROJECT_NAME}/canvas/system-architecture]]**: Visual representation of system architecture
- **[[projects/{PROJECT_NAME}/canvas/feature-development]]**: Development workflow and process
- **[[projects/{PROJECT_NAME}/canvas/issue-resolution]]**: Systematic debugging and problem-solving

### **Advanced Analytics**
```dataview
TABLE WITHOUT ID
  "📊 " + file.name as "Canvas",
  "🎯 " + choice(contains(file.name, "system"), "Architecture Overview", choice(contains(file.name, "feature"), "Development Workflow", "Problem Solving")) as "Purpose",
  "🔗 [Open Canvas](" + file.path + ")" as "Access"
FROM "projects/{PROJECT_NAME}/canvas"
WHERE file.extension = "canvas"
SORT file.name ASC
```

## 📈 **Success Metrics**

### **Efficiency Gains**
- ⚡ **Context Switch Time**: Target < 30 seconds from dashboard to full context
- 📋 **Task Discovery**: Target < 10 seconds to identify current priorities
- 🔄 **Status Updates**: Target < 2 minutes to update project status

### **Quality Indicators**
- 🔗 **Link Density**: 5+ internal links per memory bank file
- 📊 **Documentation Coverage**: All major features documented
- 🎯 **Template Usage**: Standardized workflows for all development

---

**⚡ Quick Start**: New session? Start with [[activeContext]] then return here for navigation!

*Dashboard powered by Obsidian Dataview - automatically updated from memory bank frontmatter*