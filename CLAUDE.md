# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository purpose

This is not a software project. It is a Markdown-based learning path that teaches Design
Thinking as a product discovery method, then teaches participants to configure Claude Code
(via a project Skill and subagents) to run that method as a repeatable workflow. There is no
build, lint, or test tooling — the repository's "product" is the lesson content in the
numbered `.md` files plus, once a workshop group starts Phase 3+ of `06-session-handout.md`,
a set of workshop deliverables created inside the repo (see below).

## Learning path structure

Files `01`–`06` in the repo root form an ordered curriculum; each module builds on the
previous one:

1. `01-design-processes-and-design-thinking.md` — Design Thinking vs. Double Diamond vs.
   design sprints.
2. `02-empathise-with-evidence.md` — evidence-gathering, personas, journey maps.
3. `03-define-and-ideate.md` — problem framing, POV statements, How Might We questions.
4. `04-prototype-test-and-iterate.md` — prototype fidelity, usability testing, iteration.
5. `05-claude-code-skills-and-subagents.md` — turns the method (modules 01–04) into a
   reusable Claude Code Skill plus two review subagents.
6. `06-session-handout.md` — the practical workshop: a 9-phase sequence plus optional
   extensions where a group directs Claude Code through a full Design Thinking cycle.

`assets/` holds attributed diagrams referenced by the lesson files (Double Diamond, journey
map examples, official Anthropic Skill/subagent doc screenshots). Treat these as
already-licensed reference material, not something to regenerate.

When asked to edit lesson content, preserve the module's position in the sequence (each file
assumes the reader completed the previous ones) and keep terminology consistent with the
"AI Project Manager" framing used throughout: Claude Code produces artifacts and prototypes;
the human group supplies evidence and makes product decisions.

## The workshop workflow this repo teaches

`05-claude-code-skills-and-subagents.md` and `06-session-handout.md` describe a specific
Claude Code configuration that a workshop group builds *inside this repo* (or a copy of it).
If asked to do this work, follow the same structure the lessons describe rather than
inventing a different one:

- `.claude/skills/design-thinking/SKILL.md` — a Skill derived from modules 01–04 that
  encodes the Design Thinking method, evidence rules, and approval gates. It must not encode
  a specific product solution, and must require human approval before committing to a concept
  or editing a prototype.
- `.claude/agents/evidence-auditor.md` — a **read-only** subagent that audits discovery
  artifacts for unsupported claims, mixed certainty levels, and missing evidence.
- `.claude/agents/prototype-reviewer.md` — a **read-only** subagent that reviews the
  prototype against the approved learning question for unclear flows, accessibility issues,
  and test risks.

Workshop deliverables produced alongside these live in the repo root:

- `discovery.md` — evidence, persona, journey map, POV, HMW question.
- `decision-log.md` — ideas generated, selection criteria, chosen direction, rejected options.
- a prototype (static HTML/CSS/JS is the suggested default, but not mandatory).
- `test-notes.md` — usability test observations and the approved iteration.
- `ai-collaboration-log.md` — a table of requests/delegated tasks with accepted/edited/
  rejected status and the evidence or reason.

## Non-negotiable guardrails

These rules recur across `05` and `06` and should govern any work in this repo, not just
content edits:

- **Evidence vs. interpretation vs. assumption must stay visibly separate** in any artifact
  Claude produces. Never let a generated interpretation or assumption get written as if it
  were observed evidence.
- **AI-generated personas, simulated reactions, or subagent findings are not user research.**
  They may inform review but must never be presented as evidence from real people.
  Never fabricate an answer to fill a missing-evidence gap — leave it as an open question.
- **No sensitive personal data.** Names and identifying details must be removed from research
  notes before they are entered into Claude Code.
- **Approval gates are mandatory**, not optional politeness: show a plan before creating the
  Skill, subagents, or prototype; propose selection criteria before choosing a direction;
  propose changes from test observations before implementing them. Do not skip ahead and
  build/edit without the group's approval at each gate.
- **Review subagents stay read-only** and critique rather than silently rewrite — their
  output is findings for the human group to accept, edit, or reject, never a final decision.
