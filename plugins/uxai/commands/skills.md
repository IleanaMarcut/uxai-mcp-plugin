---
description: "List the UX+AI skills: the workflow skills installed with this plugin and the installable skills that come with the subscription."
---

The user wants to see the UX+AI skills. Their request:

$ARGUMENTS

Call the connector's `skills` tool and present what it returns, titles and summaries exactly as given. Do not invent, rename, or rephrase any of them.

Present them in two groups:

1. **Installed with this plugin** (they are already available in this session): Project Health Check, Portfolio Coach, Agent Designer. Each handles a whole situation and runs the right methods in order; the user starts one by describing their situation or naming it.
2. **Installable packages**: the rest of what the `skills` tool returned, such as Idea Studio, AI UX Risk audit, and 3D Studio. To get one, the user asks for it, for example: "install the 3D Studio skill", and the connector's `get_skill` tool returns the download link and steps. Only call `get_skill` when the user asks for a skill in this conversation.

If the `skills` tool from the UX+AI connector is not available in this session, do not improvise. Tell the user, in two lines:
1. The skills come with the UX+AI connector, which needs signing in.
2. Run `/mcp`, pick `uxai`, and sign in with the email address their paid UX+AI Newsletter subscription is under. A 6-digit code arrives by email.
Then stop. `/uxai:connect` is where anyone without access is sent.
