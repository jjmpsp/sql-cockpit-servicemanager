# sql-cockpit-servicemanager

The SQL Cockpit Service Control Electron application (Windows tray companion).

## Release Publishing

This repository publishes installer artifacts through GitHub Releases using:

- workflow: `.github/workflows/release-electron.yml`
- trigger: git tag push matching `v*.*.*` (for example `v1.0.1`)

### Release steps

1. Update version in `windows/SqlCockpit.ServiceControl.Electron/package.json`.
2. Commit and push to `main`.
3. Tag and push:

```powershell
git tag v1.0.1
git push origin main
git push origin v1.0.1
```

The workflow will run on `windows-latest`, execute `npm ci`, then `npm run dist`, and publish release assets via `electron-builder` + `electron-updater`.
