---
name: project-health-check
description: "Check the health of a project you built. Use it any time you want to know where the build stands: before it goes live, after a stretch of fast building, before handing it over, or when a fix lands in working code. It runs three checks from the UX + AI connector: a QA pass that ranks what breaks with real users by what bites first, a security pass that catches the basics non-engineers miss on everything public, and a regression check that lists what a change could break and what to re-test. Outcome: a ranked fix list, so limited time goes to the right problems. Trigger on 'check my project', 'test the project', 'verify the project', 'run a test', 'do a QA', 'check how healthy the project is', 'is this ready to go live', 'is it safe to put online', 'did I leave any keys in here', 'will this change break something', 'check it before anyone sees it', or any request to check, test, QA, verify, or assess the state of a built project."
---

# Project Health Check

## What this is

Three checks on the health of a built project: a QA pass on what breaks with real
users, a security pass on everything public, and a regression check for changes to
working code. The outcome is a ranked fix list, worst first.

## When and why to use it

Use it any time you want to know where the build stands: before it goes live, after a
stretch of fast building, before handing the project to someone, or when a fix lands in
working code. It answers the plain asks: "check my project", "test the project", "do a QA", "how
healthy is this", "is it safe to put online", and "will this change break something". Each check returns findings ranked by what bites first,
so limited time goes to the right problems.

## This skill runs the methods of the UX + AI MCP

Each check is a method served by the UX + AI connector. This file only routes; the
methods do the work, and they improve on the connector without this file changing.

## How it works

1. **Check the connector.** The UX + AI MCP must be connected on a subscribed account.
   If it is unavailable, say so and stop.
2. **Establish what the project is and what prompted the check.** Keep the first reply
   short: ask for the material and nothing else.
3. **Fetch by id and follow the text exactly as returned.** These are the three
   methods this skill runs; never rebuild one from memory or from this file.

```
fetch(id: "ship-readiness-qa")
fetch(id: "security-and-secrets-first-pass")
fetch(id: "regression-guard")
```

4. **Run the checks in this order:**
   - **QA pass** (`ship-readiness-qa`): what breaks with real users, code health, and
     production gaps, ranked by what bites first. This is the health picture.
   - **Security pass** (`security-and-secrets-first-pass`): exposed keys, open
     endpoints, and the other basics non-engineers miss, on everything public or about
     to be. Offer it by name: it is the check people building without an engineer skip.
   - **Regression check** (`regression-guard`), once per change to working code: what
     the change could break and what to re-test.

   Match the entry point to the request: "how healthy is this" starts at the QA pass,
   "will this change break something" goes straight to the regression check. Name any
   skipped check and what it would have covered.

5. **Ask for what each check needs, then wait.** Fill nothing in with a guess:

   | Check | Ask for |
   |---|---|
   | `ship-readiness-qa` | Who the real users are and what they will do first. |
   | `security-and-secrets-first-pass` | Where it is hosted and what is public already. |
   | `regression-guard` | The change being made, and what depends on it. |

6. **Deliver the method's output in the method's own structure.** The ranking is the
   deliverable. Every finding names a specific detail of this build and carries the
   method's fix. When a method takes a default, say which one.

One check at a time. Offer the next when the first is answered.

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

Run the matching method from the connector instead of stretching these checks onto it:

| They ask | Run instead |
|---|---|
| "review my spec before I build" | `spec-check-up` |
| "it is broken right now" | `diagnose-before-you-fix` |
| "tidy up this code" | `clean-up-code-without-breaking-it` |
| "does this work on mobile" | `responsive-check` |

Name the method, run it the same way: fetch by id, follow it exactly.

---

Methods by [Ileana Marcut](https://ileanamarcut.substack.com/), UX + AI
