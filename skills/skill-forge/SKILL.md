---
name: skill-forge
description: "Designs, tests, refactors, and retires skills in the user's skill suite, and maintains the promotion-gate test record. Use whenever the work is about the skill catalog itself rather than a domain task: creating a new skill, rewriting or auditing an existing one, deciding whether a proposed skill should exist, promoting or demoting a skill on the four-tier maturity scale (BUILT, PROTOTYPE, DESIGNED, CONCEPT), logging a win or loss from a real task, or running a hygiene pass on the record file. Trigger on requests to build a skill, update skill status in a systems index, check what is BUILT versus designed, or close the design-to-deployment gap. This skill depends on guardian-context Section 8 for construction standards; load guardian-context first if not already loaded."
---

# Skill Forge

Governs the skill catalog. Three jobs: decide whether a skill should exist,
build or refactor it to standard, and hold every skill accountable to a
performance record. The catalog's standing failure is supply outrunning
deployment; this skill exists to make the record, not the design, the unit
of progress.

## Dependencies and authority

Load guardian-context first. Section 8 (standards over steps, runtime state
separation, memory hygiene, cost of rigor) and the Section 1 Promotion Gate
are the governing standards; this skill implements them and does not restate
them. Where this skill and Section 8 ever conflict, Section 8 wins and this
skill gets corrected.

Maturity classifications use the four-tier scale defined in guardian-context
Section 1: BUILT (fully built and used), PROTOTYPE (partially built or
prototyped), DESIGNED (designed but not built), and CONCEPT (conceptual
only). Movement up the scale is governed by the Promotion Gate.

The test record lives in a runtime file, SKILLS-RECORD.md, in the working
project, per the runtime state separation rule. Create it from the repo
template, templates/SKILLS-RECORD.template.md. This skill defines the
format (the template) but never carries the state.

If you keep your own systems index (SYSTEMS.md, created from
templates/SYSTEMS-INDEX.template.md), skill status there is a runtime file
like the record: read it at execution time, and update a skill's status
there only when the record supports the change.

## Fire threshold

This skill fires on catalog work only. A domain task that happens to use a
skill does not convene skill-forge; the only touch is the one-line record
entry after the task, which any skill run can write. Do not audit or
refactor a skill mid-task. Log the failure and route the refactor to a
separate session.

## Job 1: Decide whether a skill should exist

A proposed skill must clear all four gates before any drafting:

1. Recurrence. The task has happened at least twice and will happen again.
   One-time work gets done, not systematized.
2. Non-redundancy. No existing skill covers it or could cover it with a
   section added. Prefer extending an existing skill over creating a new
   one; every additional skill costs triggering accuracy across the suite.
3. First test named, eval-first. A real, currently live task exists that
   will serve as the skill's first logged test. Before drafting, run or
   describe the task without the skill to establish the baseline gap the
   skill must close; if Claude already does the task well bare, decline.
   No live first test, no build.
4. Standards content. The skill would encode standards, formats, or durable
   logic. A checklist or a preference statement is not a skill; it is a
   line in guardian-context or a runtime file.

Deliver the existence decision as a verdict: build, extend an existing
skill (name it), or decline (state why). Per the Verdict Rule, name what
would flip the decision.

## Job 2: Build or refactor to standard

Construction requirements, applied to every new skill and every refactor:

- Platform constraints, per Anthropic's authoring docs. Frontmatter carries
  only allowed keys (name, description, license, allowed-tools, metadata);
  unexpected keys are rejected. Name: 64 characters maximum, lowercase
  letters, numbers, and hyphens only, no reserved words. Description:
  1024 characters maximum, third person, stating what the skill does and
  when to use it. Body under 500 lines. Reference files one level deep
  from SKILL.md, with a table of contents on any reference over 100 lines.
  Forward-slash paths only. No time-sensitive information in the body.
- Description field is the trigger. Write it for retrieval: name the task
  types, the trigger phrases the user actually uses, what the skill is
  distinct from, and its load-order dependency. Front-load the core
  triggers in the first two hundred characters, since listing budgets
  truncate long descriptions and drop trailing keywords first. Err pushy;
  skills under-trigger far more often than they over-trigger. Weak
  descriptions are the leading cause of skills that exist but never fire.
- Standards over steps. State the output contract and boundaries as hard
  constraints. Include a numbered procedure only where a logged failure
  justifies each step, and say so in the step or its history.
- Fire threshold. Every skill states when it does not fire and what
  lightweight mode looks like. The fire threshold in decision-brief is a
  working model.
- Runtime state separation. No statuses, dates, rosters, or open items in
  the skill body. The skill instructs Claude to read the named runtime
  files at execution time.
- Verdict discipline. If the skill produces decision-facing output, its
  output contract ends in a verdict per guardian-context Section 4.
- Verification hook. If the skill's products ship to an external audience,
  the skill names its fresh-context verification step.
- Inheritance, not restatement. Standards that live in guardian-context are
  referenced, never copied. Copied standards fork and go stale.
- House voice. No emojis, no em-dashes, no icons, concise, BLUF.

Refactors follow the same requirements plus one rule: read the full skill
and its references before editing anything, and check the record file for
logged failures the refactor should address. A refactor that does not
address a logged loss needs a stated reason to exist.

## Job 3: The record

Every skill in active use has an entry in SKILLS-RECORD.md, formatted per
templates/SKILLS-RECORD.template.md. The record is the promotion-gate
evidence: maturity classifications cite it, and a skill with no record
cannot climb.

Record discipline:

- One line per test: date, task, win or loss, one-sentence cause if a loss.
- A win means the skill produced the intended result without manual rescue.
  Partial rescue is a loss with a cause, which is more useful than a soft
  win.
- Two losses with the same cause trigger a refactor flag in the entry.
  Three losses with the same cause and no refactor demotes the skill one
  maturity tier.
- Triggering failures are recordable losses. If a skill should have fired
  and did not, log it with cause "did not trigger"; two such losses route
  the refactor at the description, tested against a small set of
  should-trigger and should-not-trigger phrasings.
- Skills do not sync across surfaces (claude.ai, API, Claude Code are
  separate), and the claude.ai upload path may enforce a shorter
  description limit than the spec. Treat the packaged folder as the
  source of truth and note deployed surfaces in the record entry.
- Record entries follow memory hygiene: dated, one finding per line,
  superseded status changes marked, and a periodic hygiene pass that
  archives retired skills rather than deleting their history.

## Job 4: The capability meta-audit

Quarterly, or whenever a painful gap discovery suggests the last audit
missed something, score the capability landscape: every recurring way the
user uses AI, whether or not a skill exists for it. Per area, score usage
frequency one to five, value per use one to five, and existing skill
coverage zero to five; leverage is frequency times value times the coverage
shortfall (five minus coverage). Rank by leverage and return the top two or
three uncovered areas as build or study candidates, each routed through the
Job 1 existence gates before anything is drafted. Log the audit date and
its top findings in SKILLS-RECORD.md. The audit exists because a
high-frequency, high-value capability can sit unexamined for months while
smaller capabilities get systematized; frequency times value is where to
look first, not novelty.

## Retirement

A skill retires when its record shows no use across a quarter, when its
domain has closed, or when an extension of another skill has absorbed it.
Retirement is an entry in the record with a one-line reason, and the skill
file moves to an archive folder. Retired is a status, not a deletion;
the design work stays recoverable.

## Output contract

Catalog work ends in one of four deliverables: an existence verdict
(Job 1), a built or refactored skill package plus its record entry
initialized with the named first test (Job 2), an updated record with
promotions, demotions, and refactor flags stated (Job 3), or a ranked
meta-audit naming the next build or study candidates (Job 4). Every
deliverable ends with the next action: the first test to run, the refactor
to schedule, or nothing further, said plainly.
