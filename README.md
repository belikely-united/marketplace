# Be Likely United — Claude Code Marketplace

The official [Claude Code](https://code.claude.com/docs/en/plugins) plugin marketplace for **Be Likely United**.

One place to discover and install every Be Likely United plugin — knowledge graphs, deep research, and more.

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

_(no plugins yet — the first one ships soon)_

## Add a new plugin (the workflow)

Whenever a new Be Likely United plugin is created, **register it here** — this marketplace is the single source of truth. Two patterns:

### A) Plugin lives in its own repo (recommended for anything substantial)

Add an entry pointing at the plugin's repo:

```json
{
  "name": "graphify",
  "source": { "source": "github", "repo": "Belikely-United/graphify" },
  "description": "Turn any folder of code, docs, or media into a navigable knowledge graph.",
  "version": "1.0.0",
  "author": { "name": "Be Likely United" },
  "homepage": "https://github.com/Belikely-United/graphify",
  "license": "MIT",
  "keywords": ["knowledge-graph", "codebase", "graphrag"]
}
```

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
