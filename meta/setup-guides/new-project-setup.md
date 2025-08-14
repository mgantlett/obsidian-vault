---
tags: [setup, guide, automation, new-project]
type: setup-guide
status: active
priority: critical
created: 2025-08-13
last-updated: 2025-08-13
managed-by: obsidian-mcp
---

# 🚀 New Project Setup Guide

*Complete automated setup process for new projects using the enhanced Obsidian workflow*

## 🎯 **Overview**

This guide enables **complete project setup in < 5 minutes** through Cline automation. Follow these steps to create a fully functional project with:
- ✅ Complete 7-file memory bank system
- ✅ Live dashboard with Dataview queries
- ✅ Visual Canvas project maps
- ✅ Cross-linked documentation
- ✅ Professional workflow structure

## 📋 **Prerequisites**

### **Obsidian Vault Setup**
- ✅ **Obsidian installed** with Dataview plugin enabled
- ✅ **Vault structure exists** with current template system
- ✅ **MCP server running** and connected to vault
- ✅ **Templates available** in `templates/memory-bank/`

### **Development Environment**
- ✅ **New project workspace created** (e.g., `/home/user/new-project-name/`)
- ✅ **Cline access** to both workspace and Obsidian vault
- ✅ **Project requirements defined** (technology stack, goals, scope)

## 🚀 **Automated Setup Process**

### **Step 1: Copy Custom Instructions (30 seconds)**
1. **Navigate to**: `meta/setup-guides/custom-instructions-template.md`
2. **Copy entire content** to new file: `{new-project-path}/.clinerules/custom-instructions.md`
3. **Customize placeholders**:
   - Replace `{PROJECT_NAME}` with actual project name (e.g., `task-manager`)
   - Replace `{PROJECT_TITLE}` with human-readable name (e.g., `Task Manager App`)
   - Replace `{PROJECT_TYPE}` with type (e.g., `web-app`, `mobile-app`, `data-science`)
   - Replace `{PRIMARY_TECH_STACK}` (e.g., `React+Node.js`, `Python+FastAPI`)
   - Replace `{PRIMARY_LANGUAGE}` (e.g., `JavaScript`, `Python`, `Dart`)

### **Step 2: Initiate Cline Setup (30 seconds)**
Provide Cline with this exact instruction:

```
Follow custom instructions
```

*Note: Smart workflow detection automatically determines this is a new project and follows initialization protocol*

### **Step 3: Automatic Cline Execution (3-4 minutes)**
Cline will automatically execute the following process:

## 🤖 **Cline Automation Steps**

### **Phase 1: Setup Guide Reading**
1. **Read this guide**: `read_note: meta/setup-guides/new-project-setup`
2. **Load project variables** from custom-instructions
3. **Understand project requirements** and customization needs

### **Phase 2: Project Structure Creation**
```
projects/{PROJECT_NAME}/
├── memory-bank/
│   ├── dashboard.md
│   ├── activeContext.md
│   ├── progress.md
│   ├── projectbrief.md
│   ├── systemPatterns.md
│   ├── techContext.md
│   ├── productContext.md
│   └── workflow-guide.md
└── canvas/
    ├── system-architecture.canvas
    ├── feature-development.canvas
    └── issue-resolution.canvas
```

### **Phase 3: Template Customization**
For each memory bank file:
1. **Copy template** from `templates/memory-bank/{filename}.md`
2. **Replace placeholders**:
   - `{PROJECT_NAME}` → actual project name
   - `{PROJECT_TITLE}` → human-readable project title
   - `{PROJECT_TYPE}` → project type
   - `{DATE}` → current date
   - `{PRIMARY_LANGUAGE}` → primary programming language
   - **+ 50+ other contextual placeholders**

### **Phase 4: Canvas Setup**
1. **Create Canvas files** for visual project management
2. **Customize layouts** for project-specific workflows
3. **Establish visual project maps** for system understanding

### **Phase 5: Dashboard Initialization**
1. **Setup Dataview queries** pointing to correct project path
2. **Initialize live status tracking** via frontmatter
3. **Establish cross-linking** between all memory bank files
4. **Validate dashboard functionality**

## 🔧 **Project Type Customizations**

### **Web Application Projects**
**Tech Stack**: React/Vue + Node.js/Python/PHP
**Customizations**:
- Frontend/backend separation in systemPatterns
- API design patterns and REST/GraphQL considerations
- Database integration and ORM patterns
- Deployment pipeline and CI/CD specifics
- User authentication and session management

### **Mobile App Projects**
**Tech Stack**: React Native/Flutter/Native
**Customizations**:
- Platform-specific considerations (iOS/Android)
- App store deployment processes
- Device testing workflows and emulator setup
- Performance optimization for mobile
- Native module integration patterns

### **Data Science Projects**
**Tech Stack**: Python + Jupyter + ML Libraries
**Customizations**:
- Data pipeline architecture and ETL processes
- Model development and experimentation workflow
- Experiment tracking and versioning (MLflow/Weights & Biases)
- Model deployment and serving infrastructure
- Data visualization and reporting systems

### **API Service Projects**
**Tech Stack**: FastAPI/Express/Spring Boot
**Customizations**:
- API design patterns and documentation
- Microservices architecture considerations
- Database design and optimization
- Authentication and authorization patterns
- Monitoring and observability setup

### **Desktop Application Projects**
**Tech Stack**: Electron/Tauri/Qt/Tkinter
**Customizations**:
- Cross-platform considerations
- Native OS integration patterns
- Application packaging and distribution
- Update mechanisms and auto-updaters
- Performance optimization for desktop

### **CLI Tool Projects**
**Tech Stack**: Python/Go/Rust/Node.js
**Customizations**:
- Command-line interface design patterns
- Configuration file management
- Package distribution and installation
- Documentation and help system
- Testing strategies for CLI applications

## ✅ **Validation Checklist**

### **After Setup Complete**
- [ ] **Dashboard renders correctly** with working Dataview queries showing project data
- [ ] **All 8 memory bank files created** with project-specific content (no template placeholders)
- [ ] **Canvas files open properly** with project-relevant visual maps
- [ ] **Internal links work** between all memory bank files
- [ ] **Frontmatter metadata consistent** across all files with correct project name
- [ ] **Project structure created** in Obsidian vault under `projects/{PROJECT_NAME}/`
- [ ] **Workflow guide functional** with project-specific development processes

### **Functionality Tests**
- [ ] **Context switching works**: Read dashboard → get full project understanding in < 30 seconds
- [ ] **Task discovery functional**: Dashboard shows current priorities and status
- [ ] **Visual navigation works**: Canvas files display relevant project workflows
- [ ] **Cross-references functional**: Links between memory bank files navigate correctly
- [ ] **Live queries work**: Dataview queries show project-specific data

### **Content Quality**
- [ ] **No template placeholders remain**: All `{PLACEHOLDER}` text replaced with actual content
- [ ] **Project-specific content**: Descriptions and examples match actual project domain
- [ ] **Consistent naming**: Project name used consistently across all files
- [ ] **Relevant technology**: Tech stack and patterns match project requirements

## 🔄 **Troubleshooting**

### **Common Issues**

#### **Dashboard Dataview Queries Not Working**
- **Cause**: Incorrect project path in queries
- **Solution**: Verify `projects/{PROJECT_NAME}/memory-bank` path is correct
- **Fix**: Update FROM clauses in dashboard Dataview queries

#### **Template Placeholders Not Replaced**
- **Cause**: Incomplete customization during setup
- **Solution**: Search for remaining `{PLACEHOLDER}` text and replace manually
- **Prevention**: Ensure all variables defined in custom-instructions

#### **Canvas Files Not Opening**
- **Cause**: Canvas plugin not enabled or files corrupted
- **Solution**: Enable Canvas core plugin in Obsidian settings
- **Alternative**: Recreate Canvas files from templates

#### **Internal Links Broken**
- **Cause**: Case sensitivity or incorrect file paths
- **Solution**: Use exact filenames and verify file exists
- **Fix**: Update links to match actual file structure

### **Reset and Retry**
If setup fails:
1. **Delete project folder**: Remove `projects/{PROJECT_NAME}/`
2. **Fix custom-instructions**: Correct any variable issues
3. **Retry setup**: Run Cline automation again
4. **Manual verification**: Check each step completed correctly

## 🚀 **Success Metrics**

### **Setup Efficiency**
- ⚡ **Total Setup Time**: < 5 minutes from start to functional system
- 🤖 **Automation Level**: 90% of process automated through Cline
- 📋 **Template Coverage**: 100% of 8 memory bank files created and customized
- 🎯 **Success Rate**: > 95% successful setups without manual intervention

### **Workflow Quality**
- ⚡ **Context Switch Speed**: < 30 seconds from dashboard to full project understanding
- 📊 **Information Discovery**: < 10 seconds to find current priorities
- 🎨 **Visual Understanding**: Instant system comprehension through Canvas
- 🔗 **Knowledge Navigation**: Seamless cross-references between documentation

## 🔮 **Phase 3 Future Enhancements**

*Track in [[meta/vault-projects/obsidian-workflow-enhancement]]*

### **Planned Improvements**
- **Smart Template Detection**: Auto-detect project type and customize templates
- **Simplified Memory Bank**: Reduce from 7 files to 3-4 native Obsidian approach
- **Dynamic Canvas**: Self-updating visual maps based on project changes
- **Advanced Automation**: One-command setup with zero manual customization
- **Template Library**: Domain-specific templates (e.g., fintech, healthcare, e-commerce)

## 🔗 **Related Resources**

- **[[meta/vault-overview]]** - Multi-project command center
- **[[meta/project-index]]** - All projects directory
- **[[meta/setup-guides/custom-instructions-template]]** - Template for local configuration
- **[[meta/setup-guides/obsidian-requirements]]** - Obsidian plugin setup
- **[[templates/memory-bank/dashboard]]** - Example of generated dashboard

---

**🚀 PROJECT SETUP**: Complete professional workflow system deployment in under 5 minutes!

*Powered by Cline automation and Obsidian native features for maximum efficiency*