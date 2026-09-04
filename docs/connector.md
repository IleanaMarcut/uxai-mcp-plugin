# The UX+AI connector

The connector is the server behind the commands and skills. It holds the method
library and serves it to your AI over MCP. This page is the reference: what it is,
how to connect, and what your AI can do with it.

## What it is

- **URL**: `https://uxai.ileanamarcut.co/mcp`
- **What it serves**: 101 UX and AI methods, 6 skills, and resources such as the AI
  product principles
- **Who can use it**: paid subscribers of the
  [UX+AI Newsletter](https://ileanamarcut.substack.com/)

## Connecting

Add the URL as a custom connector in your AI app, or install the plugin, which brings
the connector with it.

Sign-in is an email code: enter the email address your subscription is under, and a
6-digit code arrives by email. Access lasts 30 days, then you sign in again the same
way.

- **Claude (web, desktop, mobile)**: Settings, Connectors, add custom connector, paste
  the URL.
- **Claude Code**: comes with the plugin. Run `/mcp`, pick `uxai`, sign in.
- **ChatGPT**: Settings, Connectors, add the URL. Works in normal chats through search
  and fetch; developer mode shows every tool.

## The tools

What your AI can do once connected:

| Tool | What it does |
|---|---|
| `search` | Finds methods and skills from plain words |
| `list_methods` | Lists the whole library: ids, titles, one-line summaries |
| `fetch` | Pulls one method's full text by id |
| `skills` | Lists the installable skills |
| `get_skill` | Returns a download link and install steps for one skill |
| `slash_commands` | Tells an AI how to install the Claude Code plugin |

The methods also appear as named prompts in apps that support them, and the AI product
principles attach as a resource.

Download links from `get_skill` work for 15 minutes and only for the person who asked.
Ask again for a fresh one.

## Method ids

Every method has a stable id, such as `heuristic-critique` or `empathy-map`. Ids are
what `fetch` takes and what the commands use. `list_methods` always has the current
set.

## When something is off

- **The library tools are missing**: the account you signed in with is not on the
  subscriber list. If you subscribe, reconnect with the email address your
  subscription is under.
- **A tool says the connector is unavailable**: reconnect, or in Claude Code run
  `/uxai:connect`, which checks the setup and names the one thing to fix.
- **Anything else**: [ileana@creativegluelab.com](mailto:ileana@creativegluelab.com)

## What never leaves the connector

Method text is licensed to individual subscribers for their own work. It flows to
signed-in subscribers only, and may not be redistributed or republished.
