# Haijun Ecosystem Schemas

Schema files for Haijun ecosystem, registered at https://json.schemastore.org/

## Available Schemas

| Schema | URL | Description | Based On |
|--------|-----|-------------|----------|
| `haijun-code-settings.json` | https://json.schemastore.org/haijun-code-settings.json | Configuration settings for Haijun Code | Haijun Code Settings |
| `haijun-code-marketplace.json` | https://json.schemastore.org/haijun-code-marketplace.json | Marketplace plugin manifest for Haijun Code | Haijun Code Marketplace |
| `haijun-code-plugin-manifest.json` | https://json.schemastore.org/haijun-code-plugin-manifest.json | Plugin manifest for Haijun Code | OpenAI Plugin Manifest |
| `haijun-tracks-discovery.json` | https://json.schemastore.org/haijun-tracks-discovery.json | Discovery endpoint for Haijun Tracks | Juglow Tracks Discovery |
| `haijun-box.json` | https://json.schemastore.org/haijun-box.json | Plugin manifest for Haijun Box CLI | OpenAI Plugin Manifest |
| `haijun-voice.json` | https://json.schemastore.org/haijun-voice.json | Extension manifest for Haijun Voice | Gemini CLI Extensions |
| `tracks.json` | https://json.schemastore.org/tracks.json | Knowledge base format for AI agents | Tracks JSON |
| `haijun-turborepo.json` | https://json.schemastore.org/haijun-turborepo.json | Turborepo configuration for Haijun projects | turbo.build/schema.json |
| `haijun-changesets.json` | https://json.schemastore.org/haijun-changesets.json | Changesets configuration for Haijun projects | @changesets/config |
| `haijun-release-please.json` | https://json.schemastore.org/haijun-release-please.json | Release Please configuration for Haijun projects | googleapis/release-please |

## Usage

Add `$schema` to your configuration files for autocomplete and validation:

### Haijun Code Settings
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
4. Submit PR

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
