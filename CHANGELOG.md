# Changelog

This file documents all notable changes to the [n8n-helm-chart](https://github.com/maximilianoPizarro/n8n-helm-chart/). The release numbering uses [semantic versioning](http://semver.org).

Also see GitHub Releases: https://github.com/maximilianoPizarro/n8n-helm-chart/releases

## [1.17.0] — 2026-08-01

### Highlights

- Upgrade n8n from **1.123.28** to **2.32.7** (latest stable)
- Rebuild UBI image: `quay.io/maximilianopizarro/n8n:2.32.7`
- Fix OpenShift `EACCES: permission denied, mkdir '/.n8n'`
- Keep chart **1.16.0** in the Helm repository for existing catalog RC installs

### Fixed

- Always inject `HOME` and `N8N_USER_FOLDER` in the main Deployment (and import initContainer) from `main.persistence.mountPath`, so random UIDs with `HOME=/` no longer crash n8n

### Changed

- `container/Containerfile` targets n8n 2.32.7 and locates `sqlite3` dynamically under pnpm
- Documentation: Sandbox install via [`values-sandbox.yaml`](values-sandbox.yaml), EACCES notes, 1.x → 2.x upgrade guide
- Artifact Hub changelog clarified: workflow auto-import uses Deployment **initContainers** (not a Helm post-install Job)

### Upgrade notes (1.16.0 → 1.17.0)

1. Backup the n8n database before upgrading (2.x migrations).
2. Keep `NODE_FUNCTION_ALLOW_BUILTIN: "*"` for MCP Code nodes on n8n 2.x.
3. Prefer `main.persistence.mountPath: "/data"` on OpenShift; do not duplicate `HOME` / `N8N_USER_FOLDER` in `extraEnvVars`.
4. First start may take longer; wait for Ready if a single liveness restart occurs during migrations.

```shell
helm repo update
helm upgrade n8n n8n-openshift/n8n --version 1.17.0 -f values-sandbox.yaml
```

To stay on n8n 1.123.28:

```shell
helm upgrade n8n n8n-openshift/n8n --version 1.16.0
```

## [1.16.0] — 2026-04-06

### Added

- 7 OpenShift MCP Server workflows (Streamable HTTP + session handling) with AI Format & Explain (LiteLLM/Granite) and Mailpit HTML reports
- Workflow auto-import via Deployment initContainers
- Optional Mailpit SMTP test service with OpenShift Route
- `enableServiceLinks` and `route.sccRoleDisabled` for Developer Sandbox
- Red Hat UBI image at `quay.io/maximilianopizarro/n8n` (CI build)
- `image.variant` (`official` / `ubi`) to select `wget` vs `curl` for workflow downloads
- Configurable `main.persistence.mountPath`
- Chart Verifier GitHub Actions workflow

### Changed

- n8n app version **1.123.28**
- GitHub Pages documentation redesign (MCP pipeline, lightbox, Mermaid)

### Fixed

- `ClusterIP_` typo in service template
- Hardcoded names in `role.yaml` replaced with chart naming helpers
