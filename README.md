# UX+AI Commands

101 UX and AI methods by [Ileana Marcut](https://uxai.ileanamarcut.co), in Claude Code and
in ChatGPT or Codex.

An extension of the UX+AI MCP. The methods live in the connector, and this plugin
makes them easy to find and run.

```
/uxai:heuristic-critique   our checkout screen
/uxai:cta-namer            the button that saves a draft
/uxai:methods              browse all 101
```

## Install

### 1. Open Plugins

Click the **+** next to the message box, then **Plugins**. You can also reach it from
**Settings, Plugins**.

### 2. Add the marketplace

Top right, click **Add**, then **Add from a repository**.

In the **URL** field, paste:

```
IleanaMarcut/uxai-mcp-plugin
```

Click **Sync**.

### 3. Install UX+AI Commands

Find **UX+AI Commands** in the plugin list and install it.

### 4. Restart Claude Code

Quit and reopen it.

### 5. Use it

Type `/uxai` to see all 101 methods and pick one, or run one directly with what you are
working on:

```
/uxai:heuristic-critique   our checkout screen
```

If a command says the connector is missing, run `/uxai:connect`. It names the one thing to
fix.

---

Steps 1 to 3, as commands instead:

```
/plugin marketplace add IleanaMarcut/uxai-mcp-plugin
/plugin install uxai@uxai-mcp-plugin
```

## ChatGPT and Codex

A second plugin in this repo, `plugins/uxai-codex/`, carries the same methods for ChatGPT
and Codex. It uses one routing skill rather than 101 commands, because those surfaces pick
skills by `@` or by description rather than by typed command.

```
codex plugin marketplace add IleanaMarcut/uxai-mcp-plugin
```

Then install **UX+AI Methods** from that source in the Plugins Directory and restart. Ask
for a method by name, or describe what you are working on and it picks one:

```
Run a heuristic critique on this screen
Use the UX+AI assumption mapper on this brief
Show me the UX+AI research methods
```

Same connector, same sign-in, same methods.

## How it works

Each command points at the connector. `/uxai:empathy-map` asks for the `empathy-map`
method and follows it, which gives you three things:

- **Methods that stay current.** A method gets edited, and your next run uses the new
  version. Nothing to re-download.
- **A repository you can read.** It holds the ids, titles, and one-line summaries that are
  already public on the site. The method text stays in the connector.
- **Straight answers.** Without a connector, a command tells you what is missing and how
  to fix it.

## Updating

```
/plugin update uxai@uxai-mcp-plugin
```

Method text always comes from the connector, so edits reach you straight away.

Run an update when new methods are added and you want them as their own commands. New
methods work through `/uxai:methods` from the day they ship, with or without an update.

## Uninstall

```
/plugin uninstall uxai@uxai-mcp-plugin
```

## Not connected to the UX+AI MCP yet?

The methods come from the UX+AI MCP, which comes with a paid UX+AI Newsletter
subscription.

The plugin brings the connector with it, so once you have a subscription you only need to
sign in: type `/mcp`, pick `uxai` from the list, and enter the email address your
subscription is under. You will receive a 6-digit code by email.

More details on the MCP: [uxai.ileanamarcut.co](https://uxai.ileanamarcut.co)

## Support

Happy to help: [ileana@creativegluelab.com](mailto:ileana@creativegluelab.com)

## Licence

Copyright © 2026 Ileana Marcut, UX+AI. All rights reserved.

This repository contains only the command definitions and configuration for the plugin. It
carries no method content.

The methods themselves are served by the UX+AI MCP and are licensed to individual UX+AI
Newsletter subscribers for use in their own work. Method text retrieved through the
connector may not be redistributed or republished.
