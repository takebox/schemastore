# Haijun Ecosystem JSON Schemas

JSON Schemas for the Haijun ecosystem (Haijun Code, Haijun Box, Haijun Voice, Tracks).

Two ways to consume each schema:

| Path                       | URL pattern                                                              | Status                                         |
| -------------------------- | ------------------------------------------------------------------------ | ---------------------------------------------- |
| **Official** (SchemaStore) | `https://json.schemastore.org/<name>.json`                               | active only after the SchemaStore PR is merged |
| **Raw** (immediate)        | `https://raw.githubusercontent.com/takebox/schemastore/main/<name>.json` | live now                                       |
| Source in this repo        | `src/schemas/json/<name>.json` (branch `master`)                         | live now                                       |

> This repository is a mirror of [SchemaStore/schemastore](https://github.com/SchemaStore/schemastore)
> with the Haijun schemas added under `src/schemas/json/` and registered in `src/api/json/catalog.json`.
> The official `https://json.schemastore.org/...` URLs go live once the upstream PR is merged.

## Available Schemas

| Schema                             | Official URL                                                  | Raw URL                                                                                     | Description                                      |
| ---------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| `haijun-code-settings.json`        | https://json.schemastore.org/haijun-code-settings.json        | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-code-settings.json        | Configuration settings for Haijun Code           |
| `haijun-code-marketplace.json`     | https://json.schemastore.org/haijun-code-marketplace.json     | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-code-marketplace.json     | Marketplace plugin manifest for Haijun Code      |
| `haijun-code-plugin-manifest.json` | https://json.schemastore.org/haijun-code-plugin-manifest.json | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-code-plugin-manifest.json | Plugin manifest for Haijun Code                  |
| `haijun-tracks-discovery.json`     | https://json.schemastore.org/haijun-tracks-discovery.json     | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-tracks-discovery.json     | Discovery endpoint for Haijun Tracks             |
| `haijun-box.json`                  | https://json.schemastore.org/haijun-box.json                  | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-box.json                  | Plugin manifest for Haijun Box CLI               |
| `haijun-voice.json`                | https://json.schemastore.org/haijun-voice.json                | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-voice.json                | Extension manifest for Haijun Voice              |
| `tracks.json`                      | https://json.schemastore.org/tracks.json                      | https://raw.githubusercontent.com/takebox/schemastore/main/tracks.json                      | Knowledge base format for AI agents              |
| `haijun-turborepo.json`            | https://json.schemastore.org/haijun-turborepo.json            | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-turborepo.json            | Turborepo configuration for Haijun projects      |
| `haijun-changesets.json`           | https://json.schemastore.org/haijun-changesets.json           | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-changesets.json           | Changesets configuration for Haijun projects     |
| `haijun-release-please.json`       | https://json.schemastore.org/haijun-release-please.json       | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-release-please.json       | Release Please configuration for Haijun projects |

## Install / Use

Add `$schema` to your configuration files for autocomplete and validation. Editors that
support JSON Schema (VS Code, etc.) will pick it up automatically.

Use the **official** URL when it is live, or the **raw** URL in the meantime:

```jsonc
{
  // official (after SchemaStore merge)
  "$schema": "https://json.schemastore.org/haijun-code-settings.json",
  // or raw (works immediately)
  // "$schema": "https://raw.githubusercontent.com/takebox/schemastore/main/haijun-code-settings.json"
}
```

### Haijun Code Settings (`.haijun/settings.json`)

```json
{
  "$schema": "https://json.schemastore.org/haijun-code-settings.json",
  "permissions": {
    "allow": ["Bash(npm *)", "Read"]
  }
}
```

### Haijun Box Plugin

```json
{
  "$schema": "https://json.schemastore.org/haijun-box.json",
  "schema_version": "v1",
  "name_for_human": "My Plugin",
  "name_for_model": "my_plugin",
  "description_for_human": "A plugin for Haijun Box",
  "description_for_model": "This plugin helps users with...",
  "auth": { "type": "none" },
  "api": { "type": "openapi", "url": "https://example.com/openapi.json" }
}
```

### Haijun Voice Extension

```json
{
  "$schema": "https://json.schemastore.org/haijun-voice.json",
  "name": "my-voice-extension",
  "version": "1.0.0",
  "description": "Voice extension for Haijun",
  "platforms": ["windows", "macos", "linux"]
}
```

### Tracks

```json
{
  "$schema": "https://json.schemastore.org/tracks.json",
  "name": "my-track",
  "version": "1.0.0",
  "description": "A knowledge track for AI agents",
  "type": "knowledge",
  "category": "programming"
}
```

### Turborepo

```json
{
  "$schema": "https://json.schemastore.org/haijun-turborepo.json",
  "tasks": {
    "build": {
      "outputs": ["dist/**"],
      "dependsOn": ["^build"]
    }
  }
}
```

### Changesets

```json
{
  "$schema": "https://json.schemastore.org/haijun-changesets.json",
  "changelog": "@changesets/cli/changelog",
  "commit": false,
  "fixed": [],
  "linked": [],
  "access": "public",
  "baseBranch": "main",
  "updateInternalDependencies": "patch",
  "ignore": []
}
```

### Release Please

```json
{
  "$schema": "https://json.schemastore.org/haijun-release-please.json",
  "packages": {
    ".": {
      "release-type": "node",
      "component": "my-project"
    }
  }
}
```

## Registration

To register new schemas at https://json.schemastore.org/:

1. Fork https://github.com/SchemaStore/schemastore
2. Add schema file to `src/schemas/json/`
3. Add schema URL to `src/api/json/catalog.json`
4. Add a positive test under `src/test/<schema>/`
5. Submit PR

## Ecosystem

### Haijun AI Platform

- **Haijun Code**: https://code.haijun.my.id - AI coding assistant (CLI)
- **Haijun Box**: https://box.haijun.my.id - CLI desktop AI assistant
- **Haijun Voice**: https://voice.haijun.my.id - Cross-platform AI voice assistant

### Tracks Platform

- **Tracks**: https://tracks.web.id - Knowledge base for AI agents
- **Agent Tracks**: https://agent.tracks.web.id - Agent-specific tracks

### Organization

- **GitHub**: https://github.com/track-md
- **NPM**: https://npmjs.com/~takebox-ai
- **Foundation**: JuGloW (juglow.my.id)
