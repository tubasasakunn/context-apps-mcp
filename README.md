# Context Apps MCP

**AI-powered productivity suite** connecting Todo, Idea, Journal, and Timer apps with Claude via Model Context Protocol.

[![Remote MCP](https://img.shields.io/badge/MCP-Remote_Server-blue)](https://modelcontextprotocol.io/)
[![Production](https://img.shields.io/badge/Status-Production-green)](https://mcp-server.basaapp.com/mcp)
[![Users](https://img.shields.io/badge/Users-10k+-orange)](https://mcp-app.basaapp.com/)

🌐 **Server URL**: `https://mcp-server.basaapp.com/mcp`  
📱 **Learn More**: [mcp-app.basaapp.com](https://mcp-app.basaapp.com/)

## Quick Start (30 seconds)

### Claude Desktop
1. Open Settings → **Manage connectors**
2. Click **Add custom connector** 
3. Enter URL: `https://mcp-server.basaapp.com/mcp`
4. Click **Connect** → Sign in with Apple ID
5. ✅ Ready to use!

### Other MCP Clients
```json
{
  "mcpServers": {
    "context-apps": {
      "url": "https://mcp-server.basaapp.com/mcp"
    }
  }
}
```

## Available Apps

Download all apps from App Store to unlock full functionality:

| App | Purpose | Download |
|-----|---------|----------|
| 🎯 Context Todo | AI task management & scheduling | [App Store](https://apps.apple.com/jp/app/context-todo-mcp%E5%AF%BE%E5%BF%9Ctodo%E3%82%A2%E3%83%97%E3%83%AA/id6747934261) |
| 💡 Context Idea | AI idea development & organization | [App Store](https://apps.apple.com/jp/app/context-idea-mcp%E5%AF%BE%E5%BF%9C%E3%82%A2%E3%82%A4%E3%83%87%E3%82%A2%E3%83%8E%E3%83%BC%E3%83%88/id6747934378) |
| 📔 Context Journal | AI journal analysis & insights | [App Store](https://apps.apple.com/jp/app/context-journal-mcp%E5%AF%BE%E5%BF%9C%E6%97%A5%E8%A8%98%E3%82%A2%E3%83%97%E3%83%AA/id6747934304) |
| ⏰ Context Timer | AI productivity & time tracking | [App Store](https://apps.apple.com/jp/app/context-timer-mcp%E5%AF%BE%E5%BF%9C%E3%82%BF%E3%82%A4%E3%83%9E%E3%83%BC/id6747934337) |

## What You Get

### 🎯 Smart Task Management
* AI task breakdown and prioritization
* Intelligent time estimation
* Context-aware scheduling
* Progress tracking and insights

### 💡 Idea Development
* AI-powered brainstorming assistance
* Concept expansion and refinement
* Knowledge linking and organization
* Creative synthesis and insights

### 📔 Journal Intelligence
* Emotional pattern recognition
* Personal growth tracking
* AI-guided reflection prompts
* Behavioral insight analysis

### ⏰ Productivity Optimization
* Focus session management
* Work pattern analysis and optimization
* Habit formation guidance
* Performance metrics and recommendations

## Authentication & Security

* **Authentication**: Apple ID OAuth 2.0
* **Requirements**: Context apps installed on iOS device
* **Permissions**: Read/write access to your productivity data
* **Privacy**: End-to-end encrypted communication
* **Data Control**: You own your data, export anytime

## Available MCP Tools

* **Task Management**: `todo_search`, `todo_insert`, `todo_update`, `todo_delete`, `todo_status_list`
* **Idea Development**: `idea_search`, `idea_insert`, `idea_update`, `idea_delete`
* **Journal Analysis**: `journal_search`, `journal_insert`, `journal_update`, `journal_delete`, `journal_tag_list`
* **Time Management**: `timer_search`, `timer_insert`, `timer_update`, `timer_delete`

→ [View detailed tool documentation](docs/tools.md)

## Example Interactions

👤 "Help me organize my day with 5 tasks and 3 meetings"  
🤖 *Analyzes tasks via Context Todo, estimates times, creates optimized schedule*

👤 "Expand my idea about sustainable urban transportation"  
🤖 *Uses Context Idea to develop concepts, suggest research areas, structure thinking*

👤 "How has my productivity changed this month compared to last?"  
🤖 *Analyzes patterns using Context Timer and Journal data, provides insights*

👤 "Create a reflection prompt based on my recent journal entries"  
🤖 *Reviews Context Journal data, generates personalized reflection questions*

## Supported Platforms

| Platform | Status | Setup Guide |
|----------|--------|-------------|
| 🖥 Claude Desktop | ✅ Full Support | [Quick Start](#quick-start-30-seconds) |
| 📝 Cursor IDE | ✅ Compatible | Standard MCP config |
| 🛠 Cline (VS Code) | ✅ Compatible | Standard MCP config |
| 🌐 Other MCP Clients | ✅ Standard MCP | JSON config above |

## System Requirements

* **MCP Client**: Any MCP-compatible application
* **Authentication**: Apple ID required
* **iOS Apps**: Context apps installed on iOS device
* **Internet**: Stable connection required

## Troubleshooting

**Connection Issues:**
* Verify URL: `https://mcp-server.basaapp.com/mcp`
* Check internet connectivity
* Ensure MCP client supports remote servers

**Authentication Problems:**
* Confirm Apple ID credentials
* Verify Context apps are installed on iOS device
* Check app permissions in iOS Settings

**Tool Errors:**
* Ensure specific Context app is installed for tool category
* Check app is signed in with same Apple ID
* Verify app permissions are granted

## Support & Community

* 🌐 **Website**: [mcp-app.basaapp.com](https://mcp-app.basaapp.com/)
* 📧 **Support**: support@basaapp.com
* 🐛 **Issues**: [GitHub Issues](https://github.com/basaapp/context-apps-mcp/issues)
* 💬 **Community**: Join our Discord server

## Service Information

* **Status**: Production (launched November 2024)
* **Users**: 10,000+ active users
* **Uptime**: 99.9% SLA
* **Updates**: Automatic server updates
* **Regions**: Global availability

---

## Legal

This is a hosted remote MCP server. Usage is governed by:
* **Terms of Service**: [basaapp.com/terms](https://basaapp.com/terms)
* **Privacy Policy**: [basaapp.com/privacy](https://basaapp.com/privacy)

Context Apps mobile applications are available under their respective App Store licenses.

Copyright © 2024 Basaapp. All rights reserved.