# GlacierLens - Deep visibility for your SQL data

A modern, lightweight Electron desktop application for managing SQL Server databases. GlacierLens provides a fast, responsive alternative to traditional tools with a clean interface, powerful query execution, and intelligent data navigation.

## Key Features

- **Fast Connection Management** - Save and organize multiple SQL Server connections with support for SQL Server, Windows, and Microsoft Entra authentication (including MFA)
- **Three-View System** - Dashboard (monitoring), Objects (management), and Query (SQL editing) tabs with unified Navigator
- **Query Editor** - Write and execute SQL with syntax highlighting, autocomplete, find and replace, and keyboard shortcuts
- **Execute Selection** - Highlight text to execute only selected SQL; status bar shows execution scope
- **Virtualized Results Grid** - Handle large result sets (10,000+ rows) with smooth scrolling and FK navigation
- **Foreign Key Navigation** - Click on foreign key values to instantly view related records
- **UPDATE Statement Generation** - Right-click on grid cells to generate T-SQL UPDATE statements
- **Table Management** - Create and delete tables directly from the Objects view with visual column designer
- **Column Management** - Add and edit columns with full data type support, including identity and defaults; click columns to view indexes and constraints
- **Destructive Query Warnings** - Configurable warnings before executing DROP, DELETE, or TRUNCATE statements
- **Database Dashboard** - Monitor database size, backup status, and performance metrics at a glance
- **Objects View** - Manage tables, indexes, constraints, and stored procedures in a dedicated view
- **Navigator** - Context-aware navigation with favorites, search, and smooth scrolling across all views
- **Object Search** - Search schemas, tables, and columns with filter query language (AND/OR operators)
- **Incremental Data Sync** - Checkpoint-based synchronization that only transfers changed data since the last sync
- **Scheduled Auto-Runs** - Cron-based scheduling for Copy and Sync operations with conflict detection, desktop notifications, and execution history
- **Automatic Updates** - Background updates via GitHub releases ensure you always have the latest features and security patches
- **Query History** - Access per-tab query history with one-click copy
- **Data Export** - Export results to CSV, JSON, or Excel with a single click
- **Environment Awareness** - Color-coded environment labels (Dev, Staging, Prod) with optional destructive query warnings
- **Theme System** - Multiple light and dark theme variations (Default, Warm, Cool)
- **Session Persistence** - Your queries and workspace restore exactly where you left off

## Quick Start

### Prerequisites

- Windows 10/11
- Node.js 18+ and npm
- SQL Server instance (local or remote)

### Installation

```bash
# Clone the repository
git clone https://github.com/your-org/glacierlens.git
cd glacierlens

# Install dependencies
npm install

# Start in development mode
npm run dev
```

### First Connection

1. Click the **+** button in the Connections panel
2. Enter your connection details (server, database, authentication)
3. Click **Test Connection** to verify
4. Click **Add Connection** to save

## Authentication Methods

GlacierLens supports four authentication methods:

| Method | Use Case | Configuration |
|--------|----------|---------------|
| **SQL Server** | Username/password authentication | Enter username and password |
| **Windows** | Domain-integrated authentication | No credentials needed |
| **Microsoft Entra (Interactive)** | Azure SQL with MFA support | Works out of the box - no configuration required |
| **Microsoft Entra (Service Principal)** | Automated/CI scenarios | Requires Client ID, Tenant ID, and Client Secret |

> **Note:** Microsoft Entra Interactive authentication uses Azure CLI's public client ID by default, allowing you to connect to Azure SQL Database without any Azure app registration.

## Documentation

| Document | Description |
|----------|-------------|
| [Getting Started](docs/GETTING_STARTED.md) | Installation, setup, and first steps |
| [Usage Guide](docs/USAGE_GUIDE.md) | Complete feature guide with examples |
| [Architecture](docs/ARCHITECTURE.md) | Technical design and project structure |
| [API Reference](docs/API_REFERENCE.md) | Configuration options and API documentation |
| [Deployment](docs/DEPLOYMENT.md) | Building and distributing the application |
| [Troubleshooting](docs/TROUBLESHOOTING.md) | Common issues and solutions |
| [Filter Query Language](docs/filter-query-language.md) | Advanced search syntax for Object Search |
| [Sync Mode Configuration](docs/sync-mode-configuration.md) | Technical documentation for sync feature |

## Technology Stack

| Layer | Technology |
|-------|------------|
| Desktop | Electron 33 |
| Frontend | React 18, TypeScript, Tailwind CSS, shadcn/ui |
| Query Editor | CodeMirror 6 |
| Data Grid | TanStack Table with virtualization |
| State | Zustand |
| Backend | Express (embedded) |
| Database | mssql, msnodesqlv8 |
| Auth | @azure/msal-node |
| Testing | Vitest, Playwright |
| Build | electron-vite, electron-builder |

## Development

```bash
# Start development server
npm run dev

# Run tests
npm run test              # Unit tests
npm run test:e2e          # End-to-end tests

# Code quality
npm run lint              # ESLint
npm run typecheck         # TypeScript checking

# Build for distribution
npm run build             # Build application
npm run package           # Create Windows installer
```

## Keyboard Shortcuts

| Action | Shortcut |
|--------|----------|
| Execute Query / Selection | `F5` or `Ctrl+Enter` |
| New Tab | `Ctrl+T` |
| Close Tab | `Ctrl+W` |
| Save Query | `Ctrl+S` |
| Save as Bookmark | `Ctrl+Shift+S` |
| Copy Selected Cells | `Ctrl+C` |
| Find | `Ctrl+F` |
| Find and Replace | `Ctrl+H` |

> **Tip:** When text is selected in the editor, F5 executes only the selection. When no text is selected, the entire query runs.

## Safety Features

GlacierLens includes built-in safety features to prevent accidental data loss:

- **Destructive Query Warnings** - Optional per-environment warnings before executing DROP, DELETE, TRUNCATE, and other destructive statements; disabling warnings requires explicit confirmation
- **Confirmation Dialogs** - Table deletion requires typing the table name to confirm
- **Environment Color Coding** - Visual indicators help you stay aware of which environment you're working in
- **Customizable Sidebar** - Five sidebar panels (Connections, Copy Data, Schema Drift, Bookmarks, Snippets) with drag-and-drop reordering and persistent layout

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Built with Electron and React. Designed for developers and DBAs who value speed and simplicity.
