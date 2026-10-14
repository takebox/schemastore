# Haijun Ecosystem Schemas

JSON Schema files for the Haijun ecosystem.

These schemas are published through **two paths**:

| Path | Base URL | Status | Notes |
|------|----------|--------|-------|
| **Raw (GitHub)** | `https://raw.githubusercontent.com/takebox/schemastore/main/` | ✅ Live now | Instant, no review. Use this today. |
| **SchemaStore (official)** | `https://json.schemastore.org/` | ⏳ Pending merge | Canonical URL, matches each schema `$id`. Live once the PR to `SchemaStore/schemastore` is merged. |

Both serve the exact same schema content; only the host differs.

## Available Schemas

| Schema | Raw (live now) | Official (after merge) |
|--------|----------------|------------------------|
| `haijun-code-settings.json` | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-code-settings.json | https://json.schemastore.org/haijun-code-settings.json |
| `haijun-code-marketplace.json` | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-code-marketplace.json | https://json.schemastore.org/haijun-code-marketplace.json |
| `haijun-code-plugin-manifest.json` | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-code-plugin-manifest.json | https://json.schemastore.org/haijun-code-plugin-manifest.json |
| `haijun-tracks-discovery.json` | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-tracks-discovery.json | https://json.schemastore.org/haijun-tracks-discovery.json |
| `haijun-box.json` | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-box.json | https://json.schemastore.org/haijun-box.json |
| `haijun-voice.json` | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-voice.json | https://json.schemastore.org/haijun-voice.json |
| `tracks.json` | https://raw.githubusercontent.com/takebox/schemastore/main/tracks.json | https://json.schemastore.org/tracks.json |
| `haijun-turborepo.json` | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-turborepo.json | https://json.schemastore.org/haijun-turborepo.json |
| `haijun-changesets.json` | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-changesets.json | https://json.schemastore.org/haijun-changesets.json |
| `haijun-release-please.json` | https://raw.githubusercontent.com/takebox/schemastore/main/haijun-release-please.json | https://json.schemastore.org/haijun-release-please.json |

## Usage

Add `$schema` to your configuration files for autocomplete and validation.

Use the **raw URL today** (works immediately), and switch to the **official URL**
once the SchemaStore PR is merged (or keep raw — both are valid).

### Option A — Raw (live now)

```json
{
  "$schema": "https://raw.githubusercontent.com/takebox/schemastore/main/haijun-code-settings.json",
  "permissions": {
    "allow": ["Bash(npm *)", "Read"]
  }
}
```

### Option B — Official (after SchemaStore merge)

```json
{
  "$schema": "https://json.schemastore.org/haijun-code-settings.json",
  "permissions": {
    "allow": ["Bash(npm *)", "Read"]
  }
}
```

### More examples

```json
{ "$schema": "https://raw.githubusercontent.com/takebox/schemastore/main/haijun-box.json", "schema_version": "v1" }
{ "$schema": "https://raw.githubusercontent.com/takebox/schemastore/main/haijun-voice.json", "name": "my-voice-extension" }
{ "$schema": "https://raw.githubusercontent.com/takebox/schemastore/main/tracks.json", "name": "my-track", "version": "1.0.0" }
{ "$schema": "https://raw.githubusercontent.com/takebox/schemastore/main/haijun-turborepo.json", "tasks": { "build": { "outputs": ["dist/**"], "dependsOn": ["^build"] } } }
{ "$schema": "https://raw.githubusercontent.com/takebox/schemastore/main/haijun-changesets.json", "access": "public", "baseBranch": "main" }
{ "$schema": "https://raw.githubusercontent.com/takebox/schemastore/main/haijun-release-please.json", "packages": { ".": { "release-type": "node" } } }
```

## Which path should I use?

- **Use raw** if you want it working *right now* — zero delay, no dependency on review.
- **Use the official URL** if you want the canonical, editor-auto-discovered URL that matches each schema `$id`.
- **Best of both:** use raw now and the official URL later; they are interchangeable.

## Registration (official)

To make these live at `https://json.schemastore.org/`:

1. Fork https://github.com/SchemaStore/schemastore
2. Add schema file to `src/schemas/json/`
3. Add the schema entry to `src/api/json/catalog.json`
4. Submit a PR and wait for review/merge

Until then, the raw path above is the live option.

## Ecosystem

### Haijun AI Platform
- **Haijun Code**: https://code.haijun.my.id — AI coding assistant (CLI)
- **Haijun Box**: https://box.haijun.my.id — CLI desktop AI assistant
- **Haijun Voice**: https://voice.haijun.my.id — Cross-platform AI voice assistant

### Tracks Platform
- **Tracks**: https://tracks.web.id — Knowledge base for AI agents
- **Agent Tracks**: https://agent.tracks.web.id — Agent-specific tracks

### Organization
- **GitHub**: https://github.com/takebox
- **NPM**: https://npmjs.com/~takebox-ai
- **Foundation**: JuGloW (juglow.my.id)
