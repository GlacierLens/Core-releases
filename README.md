# Kattalog

**Curious about data.**

A Windows desktop SQL Server management tool by GlacierLens. Kattalog combines database health monitoring, object management, query development, and AI-assisted diagnostics in a focused Electron application.

## Key Features

- **Three focused views** — Dashboard for database health and backup metrics, Objects for tables, indexes, constraints, diagrams, and Index Health, and Query for SQL editing and results.
- **AI Assistant** — Turn natural language into SQL, Explain with AI, run agentic diagnostics, and use Fix-with-AI. Connect an API-key provider or use Claude Code or Codex without an API key.
- **SQL editor and execution** — CodeMirror 6 editing with syntax highlighting, autocomplete, find/replace, SQL formatting, selection execution, query history, and keyboard shortcuts.
- **Session-per-tab execution** — Each query tab has an independent database session, with an open-transaction badge and Commit/Rollback prompts.
- **Structured SQL errors** — Surface actionable SQL Server error details with links that jump directly to the relevant query line.
- **Graphical execution plans** — Inspect Actual and Estimated plans, operator details, warnings, and missing-index suggestions.
- **Virtualized, editable results** — Work smoothly with large result sets; make inline edits, stage inserts and deletes, and commit changes transactionally.
- **Foreign key navigation** — Click through FK popovers, perform reverse FK lookups, and explore relationships in the FK Dependency Diagram.
- **Database and object management** — Create and modify tables and columns, inspect indexes and constraints, and monitor fragmentation in the Index Health panel.
- **Schema tools** — Compare schemas, generate synchronization scripts, and detect schema drift.
- **Copy and incremental sync** — Transfer data in batches or synchronize changes from checkpoints, with scheduling, conflict handling, progress, and run history.
- **Data export** — Export query results to CSV, JSON, or Excel.
- **Connection and safety controls** — Use SQL Server, Windows, or Microsoft Entra authentication; label environments and require confirmation for destructive operations.
- **Resilient workspace** — Restore tabs and queries between launches and automatically reconnect database sessions.
- **Windows delivery** — Install with an EV-signed installer and receive full automatic application updates.

## Quick Start

### Prerequisites

- Windows 10 or 11
- Node.js 18+ and npm
- A local or remote SQL Server instance

### Development Setup

```bash
git clone https://github.com/GlacierLens/Core.git
cd Core
npm install
npm run dev
```

To add your first connection, select **+** in the Connections panel, enter the server and authentication details, test the connection, and save it.

## Authentication

| Method | Typical use |
| --- | --- |
| SQL Server | Username and password authentication |
| Windows | Domain-integrated authentication |
| Microsoft Entra Interactive | Azure SQL with MFA |
| Microsoft Entra Service Principal | Non-interactive connections using client, tenant, and secret credentials |

## Documentation

| Document | Description |
| --- | --- |
| [Getting Started](docs/app/GETTING_STARTED.md) | Installation, setup, and first steps |
| [Usage Guide](docs/app/USAGE_GUIDE.md) | Product features and workflows |
| [Architecture](docs/app/ARCHITECTURE.md) | Technical design and project structure |
| [API Reference](docs/app/API_REFERENCE.md) | Embedded API reference |
| [Deployment](docs/app/DEPLOYMENT.md) | Building and distributing the application |
| [Troubleshooting](docs/app/TROUBLESHOOTING.md) | Common issues and solutions |
| [Filter Query Language](docs/app/filter-query-language.md) | Object Search filter syntax |
| [Sync Mode Configuration](docs/app/sync-mode-configuration.md) | Incremental sync configuration |

## Technology Stack

| Area | Technology |
| --- | --- |
| Desktop | Electron |
| Frontend | React, TypeScript, Vite |
| UI | Tailwind CSS, Radix UI |
| Query editor | CodeMirror 6 |
| Data grid | TanStack Table, TanStack Virtual |
| State | Zustand |
| Database | mssql, msnodesqlv8 |
| Testing | Vitest, Playwright |
| Packaging and updates | electron-builder, electron-updater |

## Development Commands

```bash
npm run dev              # Start the application in development mode
npm run test             # Run unit and component tests
npm run test:e2e         # Run Playwright end-to-end tests
npm run lint             # Run ESLint
npm run typecheck        # Run TypeScript type checking
npm run build            # Build the application
npm run package          # Create the Windows installer
```

## Keyboard Shortcuts

| Action | Shortcut |
| --- | --- |
| Execute query or selection | `F5` or `Ctrl+Enter` |
| New / close query tab | `Ctrl+T` / `Ctrl+W` |
| Save as bookmark | `Ctrl+S` or `Ctrl+Shift+S` |
| Find / replace | `Ctrl+F` / `Ctrl+H` |
| Toggle estimated execution plan | `Ctrl+L` |

## License

© GLACIERLENS LLC. All rights reserved.

Kattalog is proprietary commercial software. It is not open source, and no rights are granted to use, copy, modify, or distribute it except under an applicable commercial agreement.
