# Belikely United — Claude Code Marketplace

The official [Claude Code](https://code.claude.com/docs/en/plugins) plugin marketplace for **Belikely United**.

One place to discover and install every Belikely United plugin — knowledge graphs, deep research, and more.

## Install the marketplace

```shell
/plugin marketplace add Belikely-United/marketplace
```

Then browse and install plugins:

```shell
/plugin install <plugin-name>@belikely-united
```

> This repo is private during setup. Make it public before sharing the install command widely, or `/plugin marketplace add` will fail for others.

## What's inside

The catalog lives in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json). It currently lists:

- **[lerret](plugins/lerret/)** — author and export [Lerret](https://lerret.io) design assets from inside Claude Code; your own Claude is the brain, no AI keys. `/plugin install lerret@belikely-united`
- **[easyversioning](https://github.com/Belikely-United/EasyVersioning)** — saves, syncs and shares work for teams, in plain words, with no Git knowledge needed. `/plugin install easyversioning@belikely-united`

## Add a new plugin (the workflow)

Whenever a new Belikely United plugin is created, **register it here** — this marketplace is the single source of truth. Two patterns:

### A) Plugin lives in its own repo (recommended for anything substantial)

Add an entry pointing at the plugin's repo by its HTTPS address:

```json
{
  "name": "example-plugin",
  "source": { "source": "url", "url": "https://github.com/Belikely-United/example-plugin.git" },
  "description": "What the plugin does, in one line.",
  "version": "1.0.0",
  "author": { "name": "Belikely United LLP" },
  "homepage": "https://github.com/Belikely-United/example-plugin",
  "license": "MIT",
  "keywords": ["claude-code", "plugin"]
}
```

Use the HTTPS address, not `"source": "github"`. With `"github"`, `/plugin update` downloads over SSH and fails on any computer without a GitHub SSH key. A first install falls back to HTTPS, so the problem only shows up at the first update.

Only list plugins **Belikely United owns**. Don't catalog third-party tools you merely use.

### B) Plugin lives in this repo (fine for small ones)

Drop it under [`plugins/`](plugins/) and reference it by relative path:

```json
{
  "name": "my-plugin",
  "source": "./plugins/my-plugin",
  "description": "What it does."
}
```

A plugin directory needs at least `.claude-plugin/plugin.json` plus its `skills/`, `commands/`, `agents/`, or `hooks/`. See the [plugin guide](https://code.claude.com/docs/en/plugins).

## Validate before pushing

```shell
claude plugin validate .
```

Push to `main` and users pick up changes with `/plugin marketplace update`.

## License

Plugin code is licensed per-plugin (see each entry). This catalog is MIT.
