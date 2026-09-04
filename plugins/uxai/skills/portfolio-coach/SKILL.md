---
name: portfolio-coach
description: "Build the portfolio case a hiring team will judge you by. Use it when applying for a role or updating your portfolio. It runs three methods from the UX + AI connector: one finds what repeats across your work and turns it into positioning you can say out loud, one structures a case study from a real project with gaps marked instead of invented, and one delivers a tough critique aimed at the role before you send anything. Outcome: positioning, a case study, and a fix list, all built from work you did. Trigger on 'help with my portfolio', 'write my case study', 'review my portfolio', 'I am applying for a role', 'what makes my work different', 'would this get me the job', 'be harsh', or any request to shape, write, or critique work someone presents as their own."
---

# Portfolio Coach

## What this is

Three methods for the work someone presents as their own: positioning built from what
repeats across their projects, a case study structured from a real project, and a tough
critique aimed at a named role. The outcome is a portfolio argument the person can
defend in an interview, because every part of it comes from work they did.

## When and why to use it

Use it when applying for a role, preparing a portfolio review, or updating a portfolio.
It answers "what makes my work different", "how do I structure this case study", and
"would this get me the job". Positioning runs first because it decides what the
portfolio argues; the critique runs last because it judges the whole against the role.

## This skill runs the methods of the UX + AI MCP

Each step is a method served by the UX + AI connector. This file only routes; the
methods do the work, and they improve on the connector without this file changing.

## How it works

1. **Check the connector.** The UX + AI MCP must be connected on a subscribed account.
   If it is unavailable, say so and stop.
2. **Keep every fact the person gave you.** Their material is a record of chosen facts:
   dates, names, companies, roles, numbers, and how many items there were. Keep every
   item and keep the facts exact. Merge two items only after saying which and why.
   Sharpen wording; never trade a specific for a general. When the material is a CV, a
   résumé, or a project list, say so and ask before rewriting it: "tidy up my CV" means
   the wording, never which jobs are in it. The library has no CV method; say that
   plainly, then offer what fits: sharpen wording directly while holding every fact,
   `your-positioning-and-pov` for a summary line, or `the-about-bio` for a written
   piece.
3. **Keep the first reply short.** Ask for the material and the role, then stop.
4. **Fetch by id and follow the text exactly as returned.** These are the three
   methods this skill runs; never rebuild one from memory or from this file.

```
fetch(id: "your-positioning-and-pov")
fetch(id: "case-study-skeleton")
fetch(id: "portfolio-self-critique")
```

5. **Run the steps in this order:**
   - **Positioning** (`your-positioning-and-pov`) when the person starts broad: it
     reads several real projects and returns what repeats, as positioning and a point
     of view. Case studies written without it become a list of things that happened.
   - **Case study** (`case-study-skeleton`), once per project: the structure with gaps
     marked, ready to fill from what happened.
   - **Critique** (`portfolio-self-critique`) last: what would get the portfolio
     rejected, judged against the named role and reader.

   Someone with one project and a deadline gets the case study now, plus one line
   naming what positioning would have decided.

6. **Ask for what each method needs, then wait.** Fill nothing in with a guess:

   | Method | Ask for |
   |---|---|
   | `your-positioning-and-pov` | Several examples of real work. One project shows a project; the pattern across many shows a person. |
   | `case-study-skeleton` | Their part, the constraints, and what happened, including what did not work. |
   | `portfolio-self-critique` | The role it targets and who will read it. |

7. **Deliver in the method's own structure, in the person's voice.** Mark what is
   missing; never fill it. Say plainly when material is thin: a project with no
   outcome is a weak anchor, and hearing that now beats hearing it after an interview.

One method at a time. Offer the next when the first is answered.

## When the request is a different job

Run the matching method from the connector instead of stretching these three onto it:

| They ask | Run instead |
|---|---|
| "which projects should I show" | `portfolio-project-selection` |
| "here are my messy project notes" | `case-study-from-messy-notes` |
| "write my bio" | `the-about-bio` |
| "review my portfolio site's design" | `heuristic-critique` |

Name the method, run it the same way: fetch by id, follow it exactly.

---

Methods by [Ileana Marcut](https://ileanamarcut.substack.com/), UX + AI
