---
name: design-thinking
description: Run the Empathise-Define-Ideate-Prototype-Test method for a product discovery challenge, keeping evidence, interpretation, and assumptions separate and gating every product decision on human approval. Use when the group is investigating a challenge, building a persona or journey map, framing a POV/HMW, generating and selecting ideas, planning or building a prototype, or recording and iterating on a usability test.
---

# Design Thinking

This Skill runs the Design Thinking method taught in this repository's modules
01-04. It structures artifacts and enforces process discipline. It does not
supply evidence, choose the challenge, or make product decisions — those stay
with the human group (the "AI Project Manager").

## Non-negotiable rules

These apply at every stage, not just where restated:

1. **Never turn an assumption or interpretation into evidence.** Every claim in
   an artifact must be tagged as one of: `[EVIDENCE]`, `[INTERPRETATION]`,
   `[ASSUMPTION]`, or `[AI-DRAFT — unverified]`. Direct evidence keeps the
   original wording and context. Interpretation is a labeled synthesis, never
   presented as a quote or fact. An assumption is flagged and must be tested
   before it is treated as a requirement.
2. **Tag every evidence item's provenance** as `real`, `simulated`, or
   `missing`. If evidence is missing, record it as an open question — never
   fabricate an answer to fill the gap.
3. **AI-generated personas, simulated participants, and subagent findings are
   not user research.** Label any AI-simulated participant or reaction as
   `[SIMULATED]` and keep it out of the real evidence log.
4. **No sensitive personal data.** Do not enter names or identifying details
   into any artifact; confirm they've been removed from source notes first.
5. **Stop and ask for approval at each gate below** before proceeding. Show
   the plan, options, or proposed change — do not create the Skill's output
   files or edit the prototype past a gate without explicit approval.
   - Before creating or restructuring any of the deliverable files.
   - Before moving from Ideate to a selected direction (present the criteria
     table first).
   - Before building or editing the prototype (present learning question,
     files, and interaction flow first).
   - Before implementing any change proposed from test observations.
6. **The five stages (Empathise, Define, Ideate, Prototype, Test) are a
   default order, not a lockstep gate.** New evidence at any stage can send
   the work back to Empathise. Say so explicitly when it happens.

## Stage 1 — Empathise: build the evidence log, persona, journey map

Reference: `02-empathise-with-evidence.md`.

**Evidence log.** For every item collected, record it in `discovery.md` under
an Evidence Log section with these categories:

| Type | Handling rule |
|---|---|
| Direct evidence | Record the exact wording and context. |
| Behavioural evidence | Look for frequency and patterns, not single instances. |
| Interpretation | Mark it as a synthesis, not a quote. |
| Assumption | Flag it; it must be tested before being treated as a requirement. |

Tag each entry's provenance (`real` / `simulated` / `missing`).

**Persona.** Include only: a clearly described user group and context; a goal
and the situation that creates it; relevant behaviours and constraints;
evidence-backed needs or pain points; open questions where evidence is weak.
Avoid: unsupported demographic details, stereotypes, invented quotes, false
precision. Label any AI-drafted field `[AI-DRAFT — unverified]` until the
group checks it against evidence.

**Journey map.** Choose the scope deliberately — a **long-shot map** (whole
service experience) or a **close-up map** (one uncertain interaction) —
based on the question being answered. Cover, in order: the actor; the
scenario; the goal; 4-6 journey phases; for each phase one action, one
thought, one emotion, and one piece of evidence or an explicit
`[ASSUMPTION]`; pain points and moments of uncertainty; opportunities for
improvement; and close with questions to test.

Do not conflate a journey map with a user flow (path through one specific
interaction) or a user story map (activities/stories in release order) —
those are separate artifacts used later.

## Stage 2 — Define: problem statement, POV, HMW

Reference: `03-define-and-ideate.md`.

Work through, in order: cluster related observations; name the user need or
tension behind each cluster; separate evidence from interpretation; identify
the user group and context that matter most; write the problem statement.

The problem statement must be: user-centred (not solution-centred); specific
enough to investigate; grounded in observed needs or behaviours; open to more
than one response; bounded by relevant constraints.

**POV**, exact template:
> `[User] needs [need] because [insight from evidence].`

**HMW**, exact template:
> `How might we help [user] [desired progress] when [relevant context]?`

Reject any HMW draft that already contains the solution (e.g. "How might we
build a notification feature?") — regenerate it before continuing.

## Stage 3 — Ideate: diverge, then converge deliberately

Reference: `03-define-and-ideate.md`.

Diverge first: generate ideas with deferred judgement, using techniques such
as rapid brainstorming, mind mapping around the user need, SCAMPER
(Substitute, Combine, Adapt, Modify, Put to another use, Eliminate, Reverse),
"What if..." prompts that change a constraint, or borrowing patterns from
another domain. Generate ideas that are materially different from each other,
not variations in wording, colour, or layout. Do not stop at the first
plausible answer.

**Gate:** present a selection-criteria table before narrowing:

| Criterion | Question |
|---|---|
| User value | Would this meaningfully address the observed need? |
| Learning value | Could a prototype test an important assumption? |
| Feasibility | Can the team make a convincing first version quickly? |
| Risk | What could mislead, exclude, or harm users? |

The group may edit these criteria. Prefer an idea with moderate certainty but
high learning value over one that looks polished but tests nothing important.
Record alternatives, criteria, the decision, and rejected options in
`decision-log.md`.

Optionally translate the selected idea into a user story for backlog
handoff: `As a [user], I want to [action/goal], so that [benefit/reason].`
A user story is a planning artefact, not proof the interface is right — keep
it attached to its evidence and learning question.

## Stage 4 — Prototype: match fidelity to the learning question

Reference: `04-prototype-test-and-iterate.md`.

State one learning question before building anything. Choose the lowest
fidelity that can answer it:

| Learning question | Suitable prototype |
|---|---|
| Does the overall journey make sense? | Storyboard or paper flow |
| Can users find the next action? | Low-fidelity wireframe |
| Does the interaction sequence work? | Clickable prototype |
| Can a technical assumption work at all? | Small technical spike |

Do not add detail merely because it looks professional — polish can make
people react to visual finish instead of the assumption being tested. Static
HTML/CSS/JS is a reasonable default for a digital journey but not mandatory.

**Gate:** show the proposed files, interaction flow, and test task before
building or editing the prototype.

## Stage 5 — Test and iterate

Reference: `04-prototype-test-and-iterate.md`.

**Test plan** must state: the learning question; the participant or proxy and
why they're relevant; a realistic task that does not explain the intended
solution; what will be observed; follow-up questions; what evidence would
change the design.

Task script, exact template:
> `Imagine you are [person in a realistic context]. Show me how you would
> [complete the goal] using this prototype.`

Prefer observing behaviour over asking whether someone likes the idea — a
person can say a prototype looks good and still fail the task. Never name the
intended control or explain the solution during a test; ask "What would you
do next?"

**Recording.** For every finding in `test-notes.md`, use three columns —
Observation | Interpretation | Decision — and note the sample size, context,
and confidence level. Never generalize a single reaction into a universal
requirement.

**Iteration.** A test result may change the prototype, the HMW question, the
persona, the journey map, or the decision to continue — it is not limited to
the prototype. Propose changes and the observation motivating each one, wait
for approval, then implement only what was approved. Close each cycle by
stating what was learned, what changed, and what is deliberately deferred for
now.

## Deliverable files this Skill maintains

- `discovery.md` — evidence log, persona, journey map, POV, HMW question.
- `decision-log.md` — ideas generated, selection criteria, chosen direction,
  rejected options.
- the prototype, in whatever format matches the learning question.
- `test-notes.md` — test plan, observations, interpretations, decisions,
  approved iteration.
- `ai-collaboration-log.md` — a table of requests/delegated tasks with
  accepted/edited/rejected status and the evidence or reason, updated as work
  is accepted, edited, or rejected.

## When invoked mid-project

Read whichever deliverable files already exist before writing anything new,
so new work is consistent with prior evidence, labels, and decisions rather
than overwriting them.
