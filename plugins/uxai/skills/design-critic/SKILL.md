---
name: design-critic
description: "Review a design and come back with the issues worth fixing, ranked, each with a fix. Use it when a screen, a flow, or a set of screens is ready for a hard look. It runs the right critique method from the UX + AI connector for what you have in front of you: a 30-second first-impression read, the full usability critique, a friction audit on a flow, a consistency check across screens, a structured accessibility pass, or the three objections most likely to block a design review. Outcome: issues ranked by what they cost users, each with a fix. Trigger on 'review this screen', 'critique this design', 'what is wrong with this', 'is this clear', 'why does this feel heavy', 'nobody clicks the button', 'these screens do not match', 'check accessibility', 'is this ready for design review', 'be honest about my design', or any request to review, audit, or pressure-test an interface."
---

# Design Critic

## What this is

Six critique methods behind one door: a first-impression read, the full usability
critique, a cognitive-load audit, a consistency check, an accessibility pass, and a
pre-review objection hunt. The outcome is the same shape every time: issues ranked by
what they cost users, each with a fix.

## When and why to use it

Use it when a design exists and is ready for a hard look: before a design review,
before shipping, or when something feels off and the feeling needs a name. What you
have in front of you decides the method, because a critique run on the wrong scope
produces confident findings about something you did not show.

## This skill runs the methods of the UX + AI MCP

Each critique is a method served by the UX + AI connector. This file only routes; the
methods do the work, and they improve on the connector without this file changing.

## How it works

1. **Check the connector.** The UX + AI MCP must be connected on a subscribed account.
   If it is unavailable, say so and stop.
2. **Look at what they have before choosing.** "Review my checkout" with one screenshot
   is a screen. The same words with five screens and a task is a flow. When the request
   and the material disagree, say which one you are working from.
3. **Fetch by id and follow the text exactly as returned.** These are the six methods
   this skill runs; never rebuild one from memory or from this file.

```
fetch(id: "quick-clarity-check")
fetch(id: "heuristic-critique")
fetch(id: "cognitive-load-audit")
fetch(id: "consistency-audit")
fetch(id: "accessibility-quick-pass")
fetch(id: "devil-s-advocate-review")
```

4. **Match the method to the material:**

   | They have | Run | What comes back |
   |---|---|---|
   | One screen, wants a first impression | `quick-clarity-check` | A 30-second first-time read: what this seems to be, what is unclear, three fixes |
   | One screen, wants the real review | `heuristic-critique` | Usability issues worst-first, each with the heuristic it breaks and a fix |
   | A flow plus the task the user is finishing | `cognitive-load-audit` | Friction points ordered by what they cost, each with a concrete cut |
   | Several screens, components, or specs | `consistency-audit` | Conflicts grouped by type, and the one version to standardise on |
   | Anything that renders | `accessibility-quick-pass` | A structured WCAG 2.2 AA read, honest about what needs a real device |
   | A design about to be presented | `devil-s-advocate-review` | The three objections most likely to block it, and how to preempt each |

   The two single-screen methods answer different questions: the clarity check is a
   stranger with thirty seconds, the heuristic critique is a practitioner with a
   framework. Running both on one screen is reasonable; run the clarity check first,
   because a screen that fails it has a problem no heuristic will name.

5. **Ask for what each method needs, then wait.** Fill nothing in with a guess:

   | Method | Ask for |
   |---|---|
   | `heuristic-critique` | Whether a specific heuristic set is wanted; otherwise it uses Nielsen's ten and says so. |
   | `cognitive-load-audit` | What the user is trying to accomplish. Friction only means something against a goal. |
   | `accessibility-quick-pass` | The platform, and any assistive technology or audience that matters. |
   | `devil-s-advocate-review` | Who would send it back, and what they care about. |

6. **Deliver in the method's own structure.** The ranking is the deliverable. Judge
   only what they showed, say when something the method needs is missing, and make
   every issue name a specific detail of this design. Offer `accessibility-quick-pass`
   alongside whichever method ran; it applies to everything and is the pass most
   often skipped. When a method takes a default, say which one.

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

Run the matching method from the connector instead of stretching these six onto it:

| They ask | Run instead |
|---|---|
| "review my portfolio" | `portfolio-self-critique` |
| "fix the words on this screen" | `microcopy-pass` |
| "give me other versions of this" | `eight-rough-takes` or `variants-of-one-element` |
| "is our AI feature safe" | `ai-control-and-boundaries-review` |
| "walk through a competitor's flow" | `competitive-teardown` |
| "test it with real people" | `usability-test-script` |

Name the method, run it the same way: fetch by id, follow it exactly.

---

Methods by [Ileana Marcut](https://ileanamarcut.substack.com/), UX + AI
