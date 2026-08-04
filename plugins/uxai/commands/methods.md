---
description: "Browse all 101 UX+AI methods by Ileana Marcut, or route a task to the right one."
---

The user wants to browse the UX+AI method library, or find the right method for a task. Their request:

$ARGUMENTS

If they described a task, call the connector's `search` tool with it and offer the top matches by title and summary; then on their pick, call the connector's `fetch` tool with the chosen id, then follow the returned method text verbatim, applied to the user's own project and the context they have given. If the method needs a detail the user has not provided (the target user, the screen, the design, the goal), ask for it and wait; never fill project specifics with guesses.

If they did not describe a task, call `list_methods` and present the methods grouped by category, titles and summaries exactly as returned. Do not invent, rename, or rephrase any of them. Mention that every method is also its own command, `/uxai:` followed by the method id, for example `/uxai:interview-guide-builder`.

If the `fetch` tool from the UX+AI connector is not available in this session, do not improvise or reconstruct the method. Tell the user, in two lines:
1. The methods come from the UX+AI connector, which needs signing in.
2. Run `/mcp`, pick `uxai`, and sign in with the email address their paid UX+AI Newsletter subscription is under. A 6-digit code arrives by email.
Then stop. Do not add troubleshooting, and do not pitch the subscription: someone running a method wants to know what is missing, and `/uxai:connect` is where anyone without access is sent.
