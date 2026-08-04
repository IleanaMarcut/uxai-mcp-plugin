---
description: "Design system rules for AI. Create the rules that keep AI building with your tokens and components, so the system does not drift and stays maintainable as it grows. (UX+AI, Design systems)"
---

The user wants the UX+AI method "Design system rules for AI" (Design systems) applied to their own work. Their context, if any:

$ARGUMENTS

Call the connector's `fetch` tool with id `design-system-as-the-rulebook`, then follow the returned method text verbatim, applied to the user's own project and the context they have given. If the method needs a detail the user has not provided (the target user, the screen, the design, the goal), ask for it and wait; never fill project specifics with guesses.

If the `fetch` tool from the UX+AI connector is not available in this session, do not improvise or reconstruct the method. Tell the user, in two lines:
1. The methods come from the UX+AI connector, which needs signing in.
2. Run `/mcp`, pick `uxai`, and sign in with the email address their paid UX+AI Newsletter subscription is under. A 6-digit code arrives by email.
Then stop. Do not add troubleshooting, and do not pitch the subscription: someone running a method wants to know what is missing, and `/uxai:connect` is where anyone without access is sent.
