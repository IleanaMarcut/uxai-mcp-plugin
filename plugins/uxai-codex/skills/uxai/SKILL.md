---
name: uxai
description: Run one of Ileana Marcut's 101 UX and AI methods on the user's own work. Use when the user asks for a method by name or id, asks what UX+AI methods exist, or describes a UX, research, ideation, critique, writing, design-system, or AI-design task that one of the methods below covers. Needs the uxai MCP server.
---

# UX+AI methods

The methods live in the `uxai` MCP server, not in this skill. This skill routes a
request to the right method and then follows that method's own text.

## How to run a method

1. Pick the method whose title and summary best match what the user is trying to do.
   Match on intent, not keywords.
2. Call the `uxai` server's `fetch` tool with that method's id.
3. **Follow the returned method text verbatim**, applied to the user's own project and
   whatever context they have already given.
4. If the method asks for a detail the user has not provided (the target user, the
   screen, the design, the goal), ask for it and wait. Never fill in project specifics
   with guesses, and never invent a project detail or pull one from the web.

If two methods fit equally and the choice changes the outcome, name both in one line
each and ask which they want. If the user asks what is available, call `list_methods`
and present the titles and summaries exactly as returned; do not rename, regroup, or
reword them.

For a free-text request that does not obviously match, call `search` with the user's
own words and offer the top matches.

## If the uxai tools are unavailable

Do not improvise or reconstruct a method from its title and summary. Tell the user,
in two lines:

1. The methods come from the UX+AI connector, which needs signing in.
2. Open the plugin's connection settings, sign in with the email address their paid
   UX+AI Newsletter subscription is under, and enter the 6-digit code that arrives by
   email.

Then stop. Do not add troubleshooting they have not asked for.

## The methods

**Design for AI**

- `map-needs-to-ai-capabilities` — Map needs to AI capabilities. Turn user needs into realistic AI opportunities, each with a feasibility score. Grounded in what's buildable today.
- `ai-input-design` — AI input design. Design the input experience for an AI feature: the prompt or chat field, starter prompts, and empty state, so users aren't facing a blank box.
- `recover-a-broken-ai-chat` — Recover a broken AI chat. Design the recovery paths for when an AI chat breaks down: no match, low confidence, misunderstanding, off-script.
- `agentic-scope` — Agentic scope. Define what an agent can do, must ask first, and never do.
- `plan-preview` — Plan preview. Show the agent's plan before it acts, so the user can steer.
- `mid-task-controls` — Mid-task controls. Give users the controls to pause, narrow, correct, or stop a running agent.
- `ai-control-and-boundaries-review` — AI control and boundaries review. Review an AI feature for control, boundaries, and trust: where it should stop, ask, admit, or leave the decision to the user.
- `escalation-triggers` — Escalation triggers. Decide when an agent hands off to a human, and what context goes with it.
- `agent-activity-log` — Agent activity log. Design the agent's activity log: a verifiable, undoable record of what it did.
- `failure-state-finder` — Failure-state finder. List every way an AI flow can break, and how the user recovers.
- `show-why-the-ai-did-that` — Show why the AI did that. Show why the AI produced something, using only signals it can generate, so the explanation builds trust instead of faking it.
- `ai-agent-personality` — AI agent personality. Design your AI agent's personality, voice, and behavior, delivered as a usable system prompt.
- `guardrail-spec` — Guardrail spec. List what to refuse and block, with legal and safety rules flagged for review.
- `red-team-your-ai-feature` — Red-team your AI feature. Adversarial inputs that try to make your AI misbehave, so you find the holes before users or bad actors do.
- `eu-ai-act-review` — EU AI Act review. First-pass triage of where your AI product sits under the EU AI Act. Not legal advice.
- `privacy-and-data-review` — Privacy and data review. A first read on the privacy basics, with what to confirm with a professional.
- `ethics-harm-and-dark-pattern-check` — Ethics, harm, and dark-pattern check. Who could be harmed, and where a pattern works against the user.

**Research**

- `interview-guide-builder` — Interview guide builder. Plan a user interview that draws out real behavior, without leading them.
- `assumption-mapper` — Assumption mapper. Surface the riskiest beliefs under an idea, and the cheapest way to test each. Paste your brief first.
- `survey-question-critic` — Survey question critic. Catch every leading or loaded question before you send the survey.
- `jtbd-extractor` — JTBD extractor. Pull the real jobs out of your raw research data (interviews, tickets, reviews, calls), in users' own words.
- `empathy-map` — Empathy map. Build an empathy map (says, thinks, does, feels) from your real interviews, so the team sees the user the same way.
- `journey-map-to-opportunities` — Journey map to opportunities. Map the journey from real early evidence (your notes plus an online scan) and turn its pain points into opportunities to ideate on.
- `research-synthesis` — Research synthesis. Turn a pile of session notes into themes you can act on. No notes, no themes; it asks for them first.
- `interview-analysis-in-four-tables` — Interview analysis in four tables. Turn interview transcripts into a clean four-table report: participants, patterns, assumption validation, and answers to your questions.
- `card-sort-interpreter` — Card-sort interpreter. Turn card-sort data into a read on users' mental model and concrete structure changes, without over-reading thin signal.
- `set-research-goals` — Set research goals. Turn "we should do research" into answerable, decision-linked questions.
- `choose-ux-metrics` — Choose UX metrics. Pick metrics that map to the goal, with a counter-metric so they can't be gamed.
- `proto-persona` — Proto-persona. A provisional persona built on what you know, with every assumption flagged.
- `synthetic-user-panel` — Synthetic user panel. A diverse cast of believable synthetic users, each with real personality, context, and access needs, to test and compare designs against. A thinking tool, not real data.
- `synthetic-feedback-session` — Synthetic feedback session. Walk a diverse persona panel through your design step by step to surface where it breaks. Hypotheses to verify, never evidence.
- `usability-test-script` — Usability test script. A usability test script built from your real flow: tasks to attempt, with non-leading prompts.
- `emotional-drivers` — Emotional drivers. Find the emotional drivers behind your product, so you design for how it makes people feel, not just what it does.

**Design & build with AI**

- `build-brief-spec-first` — Build brief (spec-first). Turn an idea into a complete, build-ready spec before any code: flow, screens with real content, data, edge cases. It asks before assuming.
- `spec-check-up` — Spec check-up. Review and refine a build spec before you build: catch dead links, vague ranges, underspecified data, and missing states.
- `break-into-bricks` — Break into bricks. Turn the brief into small steps you can build and check one at a time.
- `responsive-check` — Responsive check. Check a generated screen for responsive behavior: how it reflows on mobile and where it breaks.
- `security-and-secrets-first-pass` — Security and secrets first pass. Catch the security basics non-engineers miss, before anyone else touches it.
- `ship-readiness-qa` — Ship-readiness QA. A pre-ship QA pass on a built app: what breaks with real users, code health, and production gaps, ranked by what bites first.
- `diagnose-before-you-fix` — Diagnose before you fix. Find the root cause before patching, including when you're stuck in a fix-one-break-more loop.
- `regression-guard` — Regression guard. Know what could break before a change, and what to re-test after.
- `clean-up-code-without-breaking-it` — Clean up code without breaking it. Tidy up messy code so it's easier to change later, without touching what works.
- `motion-spec` — Motion spec. Turn a rough animation idea into a precise, buildable micro-interaction spec, with purpose, timing, and a reduced-motion fallback.
- `infinite-marquee` — Infinite marquee. A row that scrolls its content in an endless loop with no visible seam (logos, text, or images).
- `horizontal-scroll-gallery` — Horizontal scroll gallery. A section that moves sideways through its items with a modern affordance (drag, peek, controls), no old-school scrollbar.
- `gradient-mesh-background` — Gradient-mesh background. Soft, blurred color that blends into a modern, living backdrop with gentle organic movement.
- `faq-accordion` — FAQ accordion. An accessible FAQ accordion built from your questions and answers.
- `image-to-ascii` — Image to ASCII art. Turn an image into a character grid, still or interactive, with color and density you control.
- `helix-gallery` — Helix gallery. A 3D spiral of your projects you can spin, click an item to bring it forward, with an accessible list fallback.

**Ideation**

- `find-research-backed-problems` — Find research-backed problems. Map validated, recurring, costly market problems from credible recent evidence, scored and ranked, so you pick what to solve based on demand, not hype.
- `problem-statement` — Problem statement. Turn a fuzzy challenge into a complete problem statement: who has it, what it is, when it happens, and why it matters.
- `long-term-goal-statement` — Long-term goal statement. Turn a challenge into a solution-agnostic, measurable one-year goal focused on a real user outcome, with the risks named.
- `divergent-concepts` — Divergent concepts. Ten different concepts, not one idea in ten outfits.
- `eight-rough-takes` — Eight rough takes. Eight different ways to approach one thing (a screen, flow, or concept), each on its own axis.
- `analogous-inspiration` — Analogous inspiration. Borrow a pattern from a far-off industry that solves your problem underneath.
- `constraint-reframe` — Constraint reframe. Break your default thinking by changing the rules of the problem.
- `concept-stress-test` — Concept stress test. Attack your own concept the way the room will, before the room does.
- `variants-of-one-element` — Variants of one element. Real variants of one component, each on a different axis, not reskins.
- `push-past-near-duplicates` — Push past near-duplicates. When the first set converged, force new axes instead of near-duplicates.
- `reframe-needs-into-how-might-we` — Reframe needs into How Might We. Turn user needs into How Might We questions that open the solution space instead of jumping to one answer.

**Productivity**

- `improve-a-prompt` — Improve a prompt. Improve any prompt you use: clearer, more specific, and more reliable, with the weak spots named.
- `set-up-a-new-project` — Set up a new project. Set up a clean project for working with AI: structure, naming conventions, and a filled-in rules or context file. It asks for your conventions.
- `interview-me-to-sharpen-an-idea` — Interview me to sharpen an idea. Let the AI interview you, one question at a time, until a fuzzy idea is sharp.
- `interview-me-to-set-something-up` — Interview me to set something up. Answer questions one at a time and end up with a finished brief or spec.
- `uncover-what-i-m-missing` — Uncover what I'm missing. A sharp thinking partner that probes for your blind spots, not your praise.
- `prioritize-what-to-build` — Prioritize what to build. Rank your list on an impact/effort matrix, grounded in real data, not invented scores.
- `design-documentation` — Design documentation. Document a piece of work so your team or future you can pick it up: what it is, the key decisions and why, and how it works.
- `turn-your-patterns-into-skills` — Turn your patterns into skills. Mine your own AI chats and work sessions for what you keep doing, and turn it into reusable skills, prompts, and frameworks.
- `turn-it-into-a-game` — Turn it into a game. Stuck, or getting same-y answers? Turn the task into a game with rules and a way to win, and play to win instead of playing it safe.
- `map-your-process-before-adding-ai` — Map your process before adding AI. Observe how you already think and work, write it down, then place AI where it supports your process without taking it over.

**Critique and review**

- `heuristic-critique` — Heuristic critique. For reviewing, testing, or finalising a design: the usability issues that cost users most, ranked, each with a fix.
- `consistency-audit` — Consistency audit. Catch where your design contradicts itself across screens, the vibe-coding wall.
- `accessibility-quick-pass` — Accessibility quick pass. A structured first accessibility read against WCAG 2.2 AA, honest about what still needs a real device.
- `cognitive-load-audit` — Cognitive load audit. Find every place your flow makes people think too hard.
- `devil-s-advocate-review` — Devil's advocate review. The three things most likely to get your design sent back, and how to preempt them.
- `competitive-teardown` — Competitive teardown. Walk a competitor's flow from what you paste and understand what works, what's clumsy, and why.
- `quick-clarity-check` — Quick clarity check. A 30-second first-time-user read: is it clear what this is, what stands out, and what to do next?
- `reality-check` — Reality check. A pre-mortem: imagine it failed, and surface the risks and blind spots before they bite.
- `future-proof-your-product` — Future-proof your product. Stress-test your product against realistic future shifts specific to it, and find how to stay ahead.

**Flows and information architecture**

- `full-flow-mapper` — Full flow mapper. Map the happy path and every messy edge of a task flow.
- `navigation-critique` — Navigation critique. Find the ambiguous, buried, and overlapping labels in your navigation, and a cleaner structure.
- `first-run-experience` — First-run experience. Get a brand-new user to their first real win fast.
- `state-inventory` — State inventory. List every state a screen can be in and how each should behave, so none get forgotten and each is handled well.
- `journey-map` — Journey map. Map the user's journey phase by phase: actions, thoughts, feelings, touchpoints, and pain points, built from your real research.
- `ecosystem-map` — Ecosystem map. Map every actor, system, and touchpoint around your product, and how value and information flow between them.
- `as-is-scenario` — As-is scenario. Map how the user gets the job done today, step by step with the pain, before you design anything new.

**Personal development**

- `your-positioning-and-pov` — Your positioning and point of view. Uncover what makes your work yours, from several angles, and turn it into honest positioning and a point of view.
- `portfolio-project-selection` — Portfolio project selection. Pick the right projects to anchor your portfolio for a specific role.
- `case-study-skeleton` — Case study skeleton. Structure a case study from your real work, no invented project.
- `case-study-from-messy-notes` — Case study from messy notes. Draft a case study from raw notes, without smoothing in fiction.
- `the-about-bio` — The about / bio. A bio in your voice, specific and un-inflated.
- `portfolio-self-critique` — Portfolio self-critique. A tough, role-targeted critique of your portfolio before you send it.

**UX writing**

- `microcopy-pass` — Microcopy pass. Make your interface text clearer and warmer without losing precision.
- `error-message-rewrite` — Error message rewrite. Turn cryptic errors into what happened, why, and what to do next.
- `empty-state-copy` — Empty state copy. Fill an empty screen with a headline, a line, and one clear next step.
- `cta-namer` — CTA namer. Five button labels that say exactly what happens on click.
- `tone-calibrator` — Tone calibrator. Hear your message in three tones and pick the one that fits.

**Design systems**

- `design-system-as-the-rulebook` — Design system rules for AI. Create the rules that keep AI building with your tokens and components, so the system does not drift and stays maintainable as it grows.
- `build-a-design-system-starter` — Design system starter kit. A robust design-system starter from your brand or a simple design: full color scales and roles, type, core components, all tokenized and accessible.
- `audit-your-design-system` — Audit your design system. Audit the design system in your codebase for drift: off-scale values, duplicates, naming, gaps, and contrast.
- `token-and-naming-conventions` — Token and naming conventions. Set a modern layered token system (primitive, semantic, component) and naming convention, so the system scales and AI builds with it.
