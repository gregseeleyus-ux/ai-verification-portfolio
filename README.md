# AI Verification Portfolio

Greg Seeley | Guardian Consulting Group | Albuquerque, New Mexico

I build AI workflows that professionals can trust with work that carries consequences: policy research, legislative analysis, public-sector proposals, and decision briefs. The focus is verification. AI drafts fast and makes confident mistakes; the tools here are built to catch those mistakes, measure how well they catch them, and say plainly what has and has not been proven.

Background: retired Air Force Technical Sergeant, former congressional military legislative aide, Senate military liaison, city government, public infrastructure sales, and statewide campaign work. Heavy AI user since late 2022 across ChatGPT, Claude, Gemini, and NotebookLM.

## Start here

- **[CASE-STUDY.md](CASE-STUDY.md)**: how I measured an AI verifier against a labelled test set, what it caught, where it failed, and how I kept myself honest about tuning.
- **[skills/](skills/)**: eight packaged Claude skills. The verification core is [guardian-context](skills/guardian-context/), [fresh-verify](skills/fresh-verify/), [research-run](skills/research-run/), and [adversarial-pass](skills/adversarial-pass/).
- **[CATALOG.md](CATALOG.md)**: the wider catalog of methods and systems built since 2024, many of them before I moved my work to Claude.

## How I label my own work

Every skill and method carries one of four labels, set by recorded use, not by how finished it looks:

- **BUILT**: fully built and in regular use.
- **PROTOTYPE**: working in limited scope; limited real use so far.
- **DESIGNED**: the design exists and can be tried, but there is no record of real use yet.
- **CONCEPT**: named or discussed, nothing created.

A component moves to BUILT only after two logged wins on distinct real tasks. When the evidence is thin, the label goes down, not up. A skill that is fully written but has no recorded use is labelled DESIGNED, so several items here are PROTOTYPE or DESIGNED on purpose.

## Skills

| Skill | Status | What it does |
|---|---|---|
| [guardian-context](skills/guardian-context/) | BUILT | Shared standards every other skill loads first: evidence tiers, claim-level verification, a feasibility filter for decisions that depend on people, an adversarial pre-mortem, and rules for building new skills. |
| [adversarial-pass](skills/adversarial-pass/) | BUILT | A structured red-team pass on a draft, including drafts from other AI models: classifies findings, marks each claim verified, inferred, extrapolated, or unsourced, and ends with an actionable audit. |
| [fresh-verify](skills/fresh-verify/) | PROTOTYPE | An independent verifier for finished deliverables, with a two-stage omission pass. Scored on a labelled test set; see the case study. |
| [research-run](skills/research-run/) | PROTOTYPE | Builds and judges deep research runs: one gating question, a clause that lets the run disconfirm your framing, two independent evidence chains, and a ship, correct, rerun, or cut verdict. |
| [skill-forge](skills/skill-forge/) | BUILT | Builds, tests, refactors, and retires skills, and keeps the promotion-gate record. |
| [decision-brief](skills/decision-brief/) | DESIGNED | Turns a real decision into a one-page brief with priced options and a mandatory verdict. |
| [book-recon](skills/book-recon/) | PROTOTYPE | Reconstructs a book's useful content from public sources when you do not have the book. |
| [guardian-intake](skills/guardian-intake/) | DESIGNED | Triage for raw, ambiguous input: restates the real ask, names the decisions inside it, and routes it. |

## Principles

- Model agreement is not verification. Models from different vendors share errors, so the verification skills require independent sources plus at least one check no model controls.
- "Verified" applies to a single claim, never to a whole document.
- A verifier that has never been scored is an opinion. Measure it against items with known answers, including clean items it should pass.

## Also here

- **vpt/**: the Virtual Project Team, six role cards for running a multi-perspective review, with a worked example.
- **cards/**: eight method knowledge cards.
- **methods/**: short write-ups of methods that live as prompt patterns.
- **templates/**: blank versions of the runtime files the skills expect: a skill test record, a verification test set, an evidence register, and others.
- **docs/INSTALL.md**: how to install the skills in Claude or Claude Code.

## Use

Adapt freely. The skills name no people, clients, or projects. Run each one on a real task and log the result before you rely on it.
