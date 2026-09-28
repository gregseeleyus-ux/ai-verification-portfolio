---
title: "Ground Truth Guardrails Card"
category: "quality"
version: "1.0"
status: "PROTOTYPE"
origin: "December 2025"
---

# Ground Truth Guardrails Card

Card type: master reference card.

Purpose: prevent hallucination, over-inflation, and misclassification in all synthesis work about your own AI systems portfolio (prompts, workflows, schemas, knowledge cards, pipelines, and tools). You fill in the inventory sections with your own systems; the definitions, principle, and usage rules stay fixed.

## System status classifications (canonical definitions)

FULLY BUILT AND USED (BUILT)

- Definition: complete system with documented artifacts, repeatedly used in real workflows, measurably influenced decisions or outcomes.
- Evidence required: specific artifacts (documents, templates, schemas), usage logs or examples, concrete outcomes.
- Count: record the number of systems in this tier.

PARTIALLY BUILT / PROTOTYPED (PROTOTYPE)

- Definition: working components exist (prompts, workflows, schemas), used in practice but not formalized into a stable system, lacks integration or automation.
- Evidence required: actual prompts or templates used, examples of real usage, clear statement of what is missing.
- Count: record the number of systems in this tier.

DESIGNED BUT NOT BUILT (DESIGNED)

- Definition: complete specifications exist (workflows, schemas, logic defined) but no implementation, automation, or repeated usage.
- Evidence required: design documents, specifications, but NO usage examples or working artifacts.
- Count: record the number of systems in this tier.

CONCEPTUAL ONLY / NAME-ONLY (CONCEPT)

- Definition: mentioned in documents, may have a high-level description, but no specifications, workflows, or artifacts created.
- Evidence required: appears in tool lists or discussions only.
- Count: record the number of systems in this tier.

## Card sections to fill in

1. Tier 1: fully built and used systems (the real production systems). List each system with a one-line description, grouped by domain.
2. Critical truths (never misrepresent these). For each system that is often overstated, state what it is NOT and what it IS, which components are prototyped, which are designed but not built, and which are conceptual only.
3. Schema reality check, in three lists: schemas that actually exist (documented and used), schemas drafted but incomplete, schemas aspirational only.
4. Pipeline reality check, in three lists: pipelines actually operating end to end (write each as its stage chain, for example sources, master list, merge, tagging, narrative), pipelines with fragments only (pieces exist, not integrated), pipelines conceptual only.
5. Knowledge base reality check, in two lists: actual persistent knowledge stores (project spaces with uploaded docs, core documents, knowledge cards) and working-memory-only material that is NOT a persistent knowledge base.
6. Systems abandoned or no longer active, in two lists: intentionally retired (including paused, not dead) and only mattered temporarily.
7. Current core systems: what is actually used today.
8. Forbidden interpretations (never say these): the specific overclaims to block, for example "X is a software platform" when X is a set of prompts and workflows, "Y is a unified system" when Y is separate fragments, "Z was built" when Z is name-only.
9. Required interpretations (always say these): the correct framings, for example "the portfolio consists of production systems, working prototypes, and designed architectures; each tier has different evidence requirements."

## Architectural patterns (the real reusable structures)

1. Schema-first architecture: metadata models before tools.
2. Pipeline fragments over monoliths: working segments, not complete platforms.
3. Multi-model orchestration: different models for different tasks.
4. Trust as infrastructure: validation and verification built into the architecture.
5. Simplicity: simplification and clarity as the primary goal.
6. Role-based intelligence routing: information flows to specific roles, not broadcasts.
7. Documentation as system: well-structured docs function as working systems with AI interpretation.

## Synthesis principle

When in doubt, classify DOWN not UP:

- If evidence is ambiguous, use the lower tier classification.
- If usage is unclear, mark as designed not built.
- If artifacts are missing, mark as conceptual not prototyped.
- If integration does not exist, mark as fragments not pipeline.

Ground truth beats narrative.
Evidence beats description.
What you can demonstrate beats what you can describe.

## Usage instructions for new threads

When starting work on new opportunities:

1. Reference this card at the beginning.
2. Use tier classifications as boundaries (do not claim Tier 3 systems are Tier 1).
3. Build NEW systems based on patterns, not by upgrading conceptual systems to built status.
4. When discussing existing systems, verify against this card first.
5. If you find contradictions between this card and other information, FLAG them for resolution.

This card is the canonical source of truth until explicitly updated with new evidence.
