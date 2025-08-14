---
tags: [setup, requirements, obsidian, plugins]
type: setup-guide
version: 2.0
created: 2025-08-13
---

# 🔧 Obsidian Setup Requirements

*Complete setup guide for the enhanced Cline workflow system*

## 📋 **Required Community Plugins**

### **Essential Plugins (Must Install)**

#### **1. Dataview** ⭐ CRITICAL
- **Purpose**: Powers all dynamic dashboards and live queries
- **Installation**: Community Plugins → Search "Dataview" → Install & Enable
- **Settings Required**:
  - ✅ Enable "Enable JavaScript Queries"
  - ✅ Enable "Enable Inline Queries"
  - ✅ Enable "Enable DataviewJS"

#### **2. Canvas** ✨ BUILT-IN
- **Purpose**: Visual project mapping and workflow diagrams
- **Status**: Built into Obsidian (no installation needed)
- **Usage**: Creates interactive visual project maps

### **Recommended Plugins (Optional but Helpful)**

#### **3. Templater**
- **Purpose**: Advanced template functionality with dynamic content
- **Benefits**: Auto-populate dates, project names, dynamic links
- **Installation**: Community Plugins → Search "Templater"

#### **4. Advanced Tables**
- **Purpose**: Enhanced table editing and formatting
- **Benefits**: Better table manipulation in Dataview results
- **Installation**: Community Plugins → Search "Advanced Tables"

#### **5. Tag Wrangler**
- **Purpose**: Advanced tag management and organization
- **Benefits**: Rename tags across vault, tag hierarchy
- **Installation**: Community Plugins → Search "Tag Wrangler"

## ⚙️ **Obsidian Settings Configuration**

### **Core Settings**
```yaml
Files & Links:
  - New link format: "Shortest path when possible"
  - Use [[Wikilinks]]: Enabled
  - Automatically update internal links: Enabled

Editor:
  - Default editing mode: "Live Preview"
  - Show frontmatter: Enabled
  - Fold headings: Enabled

Appearance:
  - Theme: Any (Dark themes recommended)
  - CSS snippets: Optional custom styling
```

### **Dataview Plugin Settings**
```yaml
Dataview Settings:
  ✅ Enable JavaScript Queries
  ✅ Enable Inline Queries  
  ✅ Enable DataviewJS
  📅 Date Format: "YYYY-MM-DD"
  🔢 Task Completion Tracking: Enabled
  📝 Automatic View Refresh: Enabled
```

## 📁 **Vault Structure Setup**

### **Required Folder Structure**
```
Your-Vault/
├── cline-memory-banks/          # Core memory bank storage
│   └── {project-name}/          # Project-specific memory bank
│       ├── dashboard.md         # Central command center
│       ├── activeContext.md     # Current priorities
│       ├── progress.md          # Achievement tracking
│       ├── projectbrief.md      # Foundation document
│       ├── systemPatterns.md    # Architecture patterns
│       ├── techContext.md       # Technology stack
│       └── productContext.md    # User goals
├── projects/                    # Project tracking files
├── templates/                   # Workflow templates
│   ├── feature-development.md   # Feature planning template
│   └── bug-investigation.md     # Bug resolution template
├── canvas/                      # Visual project maps
│   ├── system-architecture.canvas
│   ├── strategy-development.canvas
│   └── issue-resolution.canvas
└── setup/                       # Setup documentation
    └── obsidian-requirements.md # This file
```

## 🚀 **Quick Setup Checklist**

### **Phase 1: Obsidian Preparation**
- [ ] Install Obsidian (latest version)
- [ ] Create new vault or use existing
- [ ] Install Dataview plugin
- [ ] Enable JavaScript queries in Dataview settings
- [ ] Configure core Obsidian settings

### **Phase 2: Vault Structure**
- [ ] Create folder structure (as shown above)
- [ ] Copy memory bank files to appropriate locations
- [ ] Copy template files to templates folder
- [ ] Copy Canvas files to canvas folder

### **Phase 3: MCP Integration**
- [ ] Ensure Obsidian MCP server is running
- [ ] Test MCP connection with Cline
- [ ] Verify read/write permissions
- [ ] Test Dataview query rendering

### **Phase 4: Workflow Validation**
- [ ] Open dashboard.md and verify Dataview tables render
- [ ] Open Canvas files and verify visual layouts
- [ ] Test template usage for new features/bugs
- [ ] Verify cross-linking between memory bank files

## 🔍 **Troubleshooting**

### **Dataview Queries Not Rendering**
**Problem**: Seeing raw code blocks instead of tables/lists

**Solutions**:
1. **Install Dataview**: Community Plugins → Dataview → Install & Enable
2. **Enable JavaScript**: Dataview Settings → Enable JavaScript Queries
3. **Restart Obsidian**: Close and reopen Obsidian
4. **Check Syntax**: Ensure query syntax is correct

### **Canvas Files Not Opening**
**Problem**: Canvas files show as text instead of visual layout

**Solutions**:
1. **Check File Extension**: Must be `.canvas` not `.md`
2. **Update Obsidian**: Canvas requires recent Obsidian version
3. **File Permissions**: Ensure vault has read/write access

### **MCP Connection Issues**
**Problem**: Cline cannot read/write Obsidian files

**Solutions**:
1. **Check MCP Server**: Ensure Obsidian MCP server is running
2. **Vault Path**: Verify correct vault path in MCP configuration
3. **File Permissions**: Check folder and file permissions
4. **Restart Services**: Restart both Cline and Obsidian

## 📊 **Success Validation**

### **Dashboard Test**
Open `cline-memory-banks/{project}/dashboard.md` and verify:
- ✅ Status overview table renders with project data
- ✅ Active tasks lists show current priorities
- ✅ Recent activity table displays file updates
- ✅ Workstream status sections populate correctly

### **Canvas Test**
Open each Canvas file and verify:
- ✅ System architecture shows connected components
- ✅ Strategy development displays workflow steps
- ✅ Issue resolution shows problem-solving process
- ✅ All nodes and connections render properly

### **Template Test**
Create new note from template and verify:
- ✅ Feature development template structures correctly
- ✅ Bug investigation template includes all sections
- ✅ Cross-links to memory bank files work
- ✅ Frontmatter populates with metadata

## 🔗 **Related Documentation**

- [[cline-memory-banks/{project}/dashboard]] - Main project dashboard
- [[cline-memory-banks/{project}/workflow-guide]] - Detailed workflow procedures
- [[templates/feature-development]] - Feature planning template
- [[templates/bug-investigation]] - Bug resolution template

---

**Setup complete? Test the system by opening the dashboard and verifying all Dataview queries render correctly!**

*Enhanced workflow powered by Obsidian community plugins and native features*