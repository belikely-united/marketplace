# Be Likely United marketplace

## What it is

This repo is the official Claude Code plugin marketplace for Be Likely United.

Install it, then install plugins from it:

```shell
/plugin marketplace add Belikely-United/marketplace
/plugin install <plugin-name>@belikely-united
```

The catalog is `.claude-plugin/marketplace.json`. It currently lists one plugin:

- **lerret** — author and export Lerret design assets from Claude Code.

This catalog is MIT. Plugin code is licensed per-plugin.

## Current plan

There are no open GitHub issues and no growth notes in this repo, so there is
nothing tracked here beyond keeping the catalog correct.

Standing work:

- Keep `.claude-plugin/marketplace.json` accurate — it is the single source of
  truth for which plugins Be Likely United publishes.
- Register any new Be Likely United plugin here when it is created, either as a
  `github` source (plugin in its own repo) or a relative path under `plugins/`.
- Run `claude plugin validate .` before pushing to `main`; users pick up changes
  with `/plugin marketplace update`.

The `marketing/` directory exists as a placeholder. Nothing is written there yet.
