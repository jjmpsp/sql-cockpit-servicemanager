# SQL Cockpit Service Manager

[![GitHub release](https://img.shields.io/github/v/release/sql-cockpit/sql-cockpit-servicemanager?label=version&logo=github)](https://github.com/sql-cockpit/sql-cockpit-servicemanager/releases)
[![Build & Publish](https://github.com/sql-cockpit/sql-cockpit-servicemanager/actions/workflows/release-electron.yml/badge.svg)](https://github.com/sql-cockpit/sql-cockpit-servicemanager/actions/workflows/release-electron.yml)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows-lightgrey?logo=windows)](https://github.com/sql-cockpit/sql-cockpit-servicemanager)

> **Part of the [SQL Cockpit](https://github.com/sql-cockpit/sql-cockpit) suite** Ã¢â‚¬â€œ Your modern database management companion

---

## Ã°Å¸â€œâ€“ Overview

The **SQL Cockpit Service Manager** is a Windows tray companion application that provides seamless control and monitoring for the SQL Cockpit Windows Service. Built with Electron, this component ensures smooth integration between the SQL Cockpit Desktop app and the underlying Windows service infrastructure.

### Ã°Å¸Å½Â¯ Purpose

This repository contains:
- **Service Control Tray App**: A system tray application for managing the SQL Cockpit Windows Service lifecycle
- **Windows Service Host**: The .NET-based Windows service that powers SQL Cockpit backend operations
- **Suite Installer Scripts**: PowerShell scripts for unified installation, repair, and maintenance of the complete SQL Cockpit suite

Together with the main [SQL Cockpit Desktop app](https://github.com/sql-cockpit/sql-cockpit), this forms a complete database management solution for Windows users.

---

## Ã°Å¸Ââ€”Ã¯Â¸Â Architecture

```
Ã¢â€Å’Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€Â
Ã¢â€â€š                    SQL Cockpit Suite                        Ã¢â€â€š
Ã¢â€Å“Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€Â¤
Ã¢â€â€š  Ã¢â€Å’Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€Â    Ã¢â€Å’Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€Â Ã¢â€â€š
Ã¢â€â€š  Ã¢â€â€š  Desktop App    Ã¢â€â€šÃ¢â€”â€žÃ¢â€â‚¬Ã¢â€â‚¬Ã¢â€“ÂºÃ¢â€â€š  Service Control (Tray App)     Ã¢â€â€š Ã¢â€â€š
Ã¢â€â€š  Ã¢â€â€š  (Electron)     Ã¢â€â€š    Ã¢â€â€š  (Electron + electron-updater)  Ã¢â€â€š Ã¢â€â€š
Ã¢â€â€š  Ã¢â€â€Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€Ëœ    Ã¢â€â€Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€Ëœ Ã¢â€â€š
Ã¢â€â€š                              Ã¢â€â€š                               Ã¢â€â€š
Ã¢â€â€š                              Ã¢â€“Â¼                               Ã¢â€â€š
Ã¢â€â€š                   Ã¢â€Å’Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€Â                   Ã¢â€â€š
Ã¢â€â€š                   Ã¢â€â€š  Windows Service    Ã¢â€â€š                   Ã¢â€â€š
Ã¢â€â€š                   Ã¢â€â€š  (.NET ServiceHost) Ã¢â€â€š                   Ã¢â€â€š
Ã¢â€â€š                   Ã¢â€â€Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€Ëœ                   Ã¢â€â€š
Ã¢â€â€Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€â‚¬Ã¢â€Ëœ
```

### Component Breakdown

| Component | Location | Technology | Purpose |
|-----------|----------|------------|---------|
| **Service Control UI** | `windows/SqlCockpit.ServiceControl.Electron` | Electron | System tray interface for service management |
| **Windows Service** | `windows/SqlCockpit.ServiceHost.Windows` | .NET | Background service for SQL Cockpit operations |
| **Installation Scripts** | `windows/*.ps1` | PowerShell | Suite installation, repair, and maintenance |
| **Icons & Assets** | `icons/` | Various | Cross-platform application icons |

---

## Ã°Å¸Å¡â‚¬ Quick Start

### For End Users

Download the latest installer from the [Releases page](https://github.com/sql-cockpit/sql-cockpit-servicemanager/releases):

- **`SQL Cockpit Service Control Setup *.exe`** Ã¢â‚¬â€œ Run this single installer to provision the complete suite

The suite installer automatically provisions:
- Ã¢Å“â€¦ SQL Cockpit Desktop app
- Ã¢Å“â€¦ SQLCockpitServiceHost Windows service
- Ã¢Å“â€¦ SQL Cockpit Service Control tray app with auto-startup

> **Note:** Do not distribute separate installers to end users for normal setup. Use the suite installer only.

### For Developers

```powershell
# Clone the repository
git clone https://github.com/sql-cockpit/sql-cockpit-servicemanager.git
cd sql-cockpit-servicemanager

# Prepare the desktop bundle
powershell -ExecutionPolicy Bypass -File .\windows\Prepare-SqlCockpitSuiteDesktopBundle.ps1

# Build the Service Control Electron app
powershell -ExecutionPolicy Bypass -File .\windows\Publish-SqlCockpitServiceControlElectron.ps1
```

---

## Ã°Å¸â€ºÂ Ã¯Â¸Â Development

### Prerequisites

- **Node.js 20+** ([Download](https://nodejs.org/))
- **PowerShell 5.1+** (Windows)
- **.NET SDK** (for Windows Service Host)
- **Git**

### Project Structure

```
sql-cockpit-servicemanager/
Ã¢â€Å“Ã¢â€â‚¬Ã¢â€â‚¬ .github/workflows/       # CI/CD pipelines
Ã¢â€Å“Ã¢â€â‚¬Ã¢â€â‚¬ icons/                   # Application icons (Windows, macOS, Linux)
Ã¢â€Å“Ã¢â€â‚¬Ã¢â€â‚¬ publish/                 # Build output directory
Ã¢â€Å“Ã¢â€â‚¬Ã¢â€â‚¬ windows/
Ã¢â€â€š   Ã¢â€Å“Ã¢â€â‚¬Ã¢â€â‚¬ SqlCockpit.ServiceControl.Electron/
Ã¢â€â€š   Ã¢â€â€š   Ã¢â€Å“Ã¢â€â‚¬Ã¢â€â‚¬ build/           # Electron build configuration
Ã¢â€â€š   Ã¢â€â€š   Ã¢â€Å“Ã¢â€â‚¬Ã¢â€â‚¬ main.js          # Electron main process
Ã¢â€â€š   Ã¢â€â€š   Ã¢â€Å“Ã¢â€â‚¬Ã¢â€â‚¬ preload.js       # Preload script
Ã¢â€â€š   Ã¢â€â€š   Ã¢â€â€Ã¢â€â‚¬Ã¢â€â‚¬ renderer/        # Renderer process UI
Ã¢â€â€š   Ã¢â€Å“Ã¢â€â‚¬Ã¢â€â‚¬ SqlCockpit.ServiceHost.Windows/
Ã¢â€â€š   Ã¢â€â€š   Ã¢â€â€Ã¢â€â‚¬Ã¢â€â‚¬ ...              # .NET Windows Service source
Ã¢â€â€š   Ã¢â€Å“Ã¢â€â‚¬Ã¢â€â‚¬ *.ps1                # PowerShell installation/maintenance scripts
Ã¢â€â€š   Ã¢â€â€Ã¢â€â‚¬Ã¢â€â‚¬ *.settings.json      # Service configuration templates
Ã¢â€â€Ã¢â€â‚¬Ã¢â€â‚¬ README.md
```

### Running in Development Mode

```powershell
cd windows/SqlCockpit.ServiceControl.Electron

# Install dependencies
npm ci

# Run in development mode
npm run dev

# Or with file watching
npm run dev:watch
```

### Building Distribution Packages

```powershell
cd windows/SqlCockpit.ServiceControl.Electron

# NSIS installer (production)
npm run dist

# Portable build (testing)
npm run dist:portable
```

---

## Ã°Å¸â€œÂ¦ Release Publishing

This repository publishes installer artifacts through GitHub Releases using automated workflows.

### Release Workflow

- **Workflow File:** `.github/workflows/release-electron.yml`
- **Trigger:** Git tag push matching `v*.*.*` (e.g., `v1.0.1`)
- **Platform:** `windows-latest` runner

### Release Steps

1. **Update version** in `windows/SqlCockpit.ServiceControl.Electron/package.json`

2. **Commit and push** to `main`:
   ```bash
   git add .
   git commit -m "Bump version to 1.0.1"
   git push origin main
   ```

3. **Tag and push** the release:
   ```bash
   git tag v1.0.1
   git push origin v1.0.1
   ```

The workflow will automatically:
- Checkout the repository
- Setup Node.js 20 with npm caching
- Install dependencies via `npm ci`
- Build distribution packages via `npm run dist`
- Publish release assets using `electron-builder` + `electron-updater`

### Desktop App Release Flow

For the main SQL Cockpit desktop app (separate repository), use the `desktop-vX.Y.Z` tag format:

```bash
git tag desktop-v1.0.0
git push origin desktop-v1.0.0
```

This triggers the `.github/workflows/release-desktop-app.yml` workflow in the parent repository.

> **Important:** Auto-updates require installed/packaged builds from the NSIS installer path. Portable builds are for dev/test convenience only.

---

## Ã°Å¸â€Â§ Maintenance

### Common Maintenance Tasks

#### Reset Development Environment
```powershell
powershell -ExecutionPolicy Bypass -File .\windows\Reset-SqlCockpitServiceControlDevEnvironment.ps1
```

#### Test Windows Service Host
```powershell
powershell -ExecutionPolicy Bypass -File .\windows\Test-SqlCockpitWindowsServiceHost.ps1
```

#### Repair Suite Installation
```powershell
powershell -ExecutionPolicy Bypass -File .\windows\Repair-SqlCockpitSuite.ps1
```

### Configuration Files

| File | Purpose |
|------|---------|
| `sql-cockpit-service.settings.json` | Default service configuration |
| `sql-cockpit-service.dev.settings.json` | Development environment settings |
| `sql-cockpit-service.prod.settings.json` | Production environment settings |

---

## Ã°Å¸Â¤Â Contributing

We welcome contributions! Here's how you can help:

### How to Contribute

1. **Fork the repository** on GitHub
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Make your changes** following our coding standards
4. **Test thoroughly** using the provided PowerShell scripts
5. **Submit a Pull Request** with a clear description of changes

### Contribution Guidelines

- Follow existing code style and conventions
- Write meaningful commit messages
- Include tests for new features where applicable
- Update documentation for significant changes
- Ensure PowerShell scripts are compatible with PowerShell 5.1+

### Reporting Issues

Found a bug or have a feature request? Please open an issue on GitHub with:
- Clear description of the problem or feature
- Steps to reproduce (for bugs)
- Expected vs actual behavior
- Environment details (OS version, Node.js version, etc.)

### Code of Conduct

Please be respectful and constructive in all interactions. We're building a community around SQL Cockpit!

---

## Ã°Å¸â€œÅ¾ Support

Community support is always free via GitHub Issues and Discussions.

Commercial support is available for enterprise teams needing training, one-time migrations, and managed sync operations.
Typical pricing (GBP): training from **GBP 1,200**, one-time migration from **GBP 4,000**, managed sync from **GBP 1,500/month**.

## Ã°Å¸â€œâ€ž License

This project is licensed under the **Apache License 2.0** - see [LICENSE](LICENSE) for details.

---

## Ã°Å¸â€â€” Links

- **Main Repository:** [https://github.com/sql-cockpit/sql-cockpit](https://github.com/sql-cockpit/sql-cockpit)
- **Releases:** [https://github.com/sql-cockpit/sql-cockpit-servicemanager/releases](https://github.com/sql-cockpit/sql-cockpit-servicemanager/releases)
- **Issues:** [https://github.com/sql-cockpit/sql-cockpit-servicemanager/issues](https://github.com/sql-cockpit/sql-cockpit-servicemanager/issues)
- **Actions:** [https://github.com/sql-cockpit/sql-cockpit-servicemanager/actions](https://github.com/sql-cockpit/sql-cockpit-servicemanager/actions)

---

<div align="center">

**Made with Ã¢ÂÂ¤Ã¯Â¸Â by the SQL Cockpit Team**

[Ã¢Â­Â Star this repo](https://github.com/sql-cockpit/sql-cockpit-servicemanager) | [Ã°Å¸Ââ€º Report an issue](https://github.com/sql-cockpit/sql-cockpit-servicemanager/issues) | [Ã°Å¸â€œâ€“ View main project](https://github.com/sql-cockpit/sql-cockpit)

</div>
