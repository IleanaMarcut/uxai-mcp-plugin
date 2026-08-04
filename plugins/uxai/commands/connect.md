---
description: "Connect the UX+AI methods, or find out what is missing. Checks the connector and your subscription, and names the one next step."
---

Diagnose the user's UX+AI setup and tell them exactly what to do next. They may have
arrived here from either direction: plugin first, or connector first. Do not assume which.

Run the checks in order and stop at the first one that fails. Report the result in plain
language, name the single next action, and do not list the other steps they do not need.

## Check 1 — is the connector present at all?

Look for a connected MCP server offering the tools `search`, `list_methods` and `fetch`
(commonly under a server named `uxai`). Do not call anything yet, just look at what tools
this session has.

- **Not present** → The connector is not connected in this session. Two possible causes,
  and you should say both because they need different fixes:
  1. The plugin bundles the connector, but a bundled server only appears once Claude Code
     has picked the plugin up. Tell them to **restart Claude Code**, then run
     `/uxai:connect` again. Do not tell them to run `/reload-plugins`: it does not exist
     in every setup, and a restart works everywhere.
  2. If it still does not appear after a restart, they can add it by hand:
     `claude mcp add --transport http uxai https://uxai.ileanamarcut.co/mcp`
  Stop here.

## Check 2 — is the session signed in?

Call `list_methods`. Judge only by what comes back.

- **An authentication or authorization error, or a prompt to sign in** → They are connected
  but not signed in. Tell them: run `/mcp`, pick the `uxai` server, and authenticate. They
  will enter the email address their UX+AI Newsletter paid subscription is under, and they
  will receive a 6-digit code by email. Note that access is not instant for a brand new
  subscriber: tell them to give it 10 to 15 minutes before they add their email and
  request the code. Stop here.

- **It returns methods** → They are signed in. Continue.

## Check 3 — is the subscription active?

- **`list_methods` returned methods** → Everything works. Report the number of methods it
  returned and tell them they can now use any `/uxai:` command, for example
  `/uxai:heuristic-critique` on a screen they are working on, or `/uxai:methods` to browse
  everything. Suggest one command that fits whatever they are currently working on, if you
  can tell from the conversation.

- **Only a `subscribe` tool is available, or the catalog tools are missing while signed in**
  → The address they signed in with is not on the paid list. Tell them: the methods come
  with a paid UX+AI Newsletter subscription. If they just subscribed or upgraded, access is not
  instant: give it 10 to 15 minutes before adding the email and requesting the code. If they have more than one email address,
  the one to use is the one the subscription is under. Subscribe or check at
  https://uxai.ileanamarcut.co

## Rules

- Report what you actually observed. Never guess at a state you did not verify, and never
  claim a check passed that you did not run.
- One next action, not a checklist. The point of this command is to remove the confusion
  about which thing to set up first.
- If a check is inconclusive, say so plainly and say what would settle it.
- Never suggest editing config files by hand beyond the single `claude mcp add` line above.
