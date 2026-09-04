---
name: agent-designer
description: "Design an AI agent or bot before it meets users. Use it at design time, when the agent's behaviour is still on paper. It runs three methods from the UX + AI connector: one defines what the agent may do, must ask about first, and never does; one decides when it hands off to a human and what context travels with the handoff; one delivers its personality, voice, and behaviour as a usable system prompt. Outcome: an enforceable scope, a handoff plan, and a system prompt that holds the voice. Trigger on 'we are building an agent', 'our bot needs a personality', 'what should it sound like', 'it should do this automatically', 'how much should it be allowed to do', 'when should it ask permission', 'when does a human take over', 'give it a voice', or any request to scope, voice, or design the behaviour of something that acts on its own."
---

# Agent Designer

## What this is

Three methods for designing an AI agent or bot: the scope of what it may do, the
handoff to a human when it cannot finish, and its personality delivered as a usable
system prompt. The outcome is an agent whose behaviour is decided on paper before it
acts in front of anyone.

## When and why to use it

Use it at design time, while the agent's behaviour can still change cheaply. An agent
acts while nobody is watching, so what it is allowed to do, when it hands off, and how
it sounds have to be decisions, and this order makes each one before the next needs it.

## This skill runs the methods of the UX + AI MCP

Each step is a method served by the UX + AI connector. This file only routes; the
methods do the work, and they improve on the connector without this file changing.

## How it works

1. **Check the connector.** The UX + AI MCP must be connected on a subscribed account.
   If it is unavailable, say so and stop.
2. **Establish what the agent does.** Keep the first reply short: ask what it acts on
   and for whom, then stop.
3. **Fetch by id and follow the text exactly as returned.** These are the three
   methods this skill runs; never rebuild one from memory or from this file.

```
fetch(id: "agentic-scope")
fetch(id: "escalation-triggers")
fetch(id: "ai-agent-personality")
```

4. **Run the steps in this order:**
   - **Scope** (`agentic-scope`): what the agent can do, must ask about first, and
     never does. Every later decision needs this answer.
   - **Escalation** (`escalation-triggers`): when it hands off to a human and what
     context goes with it, so the handoff can be picked up cold.
   - **Personality** (`ai-agent-personality`) last: character, voice, and behaviour as
     a usable system prompt. It runs last because it dresses behaviour that already
     exists; written first, it becomes a voice that decides its own limits.

   Someone asking only "give it a personality" gets exactly that, plus one line naming
   the skipped steps and what each would have decided.

5. **Ask for what each method needs, then wait.** Fill nothing in with a guess:

   | Method | Ask for |
   |---|---|
   | `agentic-scope` | What the agent touches: money, other people's data, anything sent outside, anything hard to undo. The boundary is drawn around consequences. |
   | `escalation-triggers` | Who receives the handoff and what they need to act on it. |
   | `ai-agent-personality` | The brand voice, and where the agent must drop it. A bot staying playful through a failure reads as not understanding what happened. |

6. **Deliver in the method's own structure.** Design only for confirmed capability:
   never assume a permission, an integration, or a rollback. Every answer names a
   specific action this agent takes. When a method takes a default, say which one.

One method at a time. Offer the next when the first is answered.

## Presenting results

- One markdown document holds the results. When the client can create or save a
  document, put everything there; otherwise deliver it as one structured message.
  Never scatter a deliverable across replies.
- Open the document with one line: which method ran, on what material.
- Deliver everything the method's Deliver section names, complete and uncompressed:
  every item, every ranked entry, full tables, as produced.
- Keep the method's own headings, tables, and order. Add nothing decorative.
- Close with a conclusion in short bullets: the decisions or next steps the results
  point to.
- In multi-step runs, each step's output stays intact in the same document; carry
  forward what the next step needs, and never hand a summary of a deliverable to the
  next method.

## When the request is a different job

Run the matching method from the connector instead of stretching these three onto it:

| They ask | Run instead |
|---|---|
| "show the user its plan before it acts" | `plan-preview` |
| "how do they stop it mid-run" | `mid-task-controls` |
| "what record does it leave" | `agent-activity-log` |
| "is this agent safe" | `ai-control-and-boundaries-review`, then `red-team-your-ai-feature` |
| "should this even be AI" | `map-needs-to-ai-capabilities` |

Name the method, run it the same way: fetch by id, follow it exactly.

---

Methods by [Ileana Marcut](https://ileanamarcut.substack.com/), UX + AI
