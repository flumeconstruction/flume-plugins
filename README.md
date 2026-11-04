# Flume plugins

Flume's plugin for Claude. Flume helps US real estate developers, general contractors and
subcontractors source tile, flooring and stone for their projects, with instant quotes to
their ZIP code.

| Folder | What it holds |
|---|---|
| [`claude/`](claude/) | The Flume plugin for Claude on the web, desktop and mobile, Cowork and Claude Code: the `flume-search` skill and Flume's connector. Its [README](claude/README.md) says what it does, how to use it and what it sends. |

## Install

- **Claude and Cowork:** add Flume from Claude's plugin directory, then open the plugin's
  **Connectors** tab, connect Flume and sign in with your Flume account.
- **Claude Code:**

  ```text
  /plugin marketplace add flumeconstruction/flume-plugins
  /plugin install flume@flume-plugins
  ```

## About this repository

Flume publishes this repository from its own source on each release, so pull requests are
not merged here. For help, or to report a problem, write to support@tryflume.ai.

See [LICENSE](LICENSE) for the terms of use.
