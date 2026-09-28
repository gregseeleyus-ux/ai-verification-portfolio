---
title: "Notes Synthesis Sprint (Lean)"
category: "processing"
version: "1.0"
status: "DESIGNED"
origin: "September 2025"
---

# Notes Synthesis Sprint (Lean)

## Purpose

Rapidly combine a batch of meeting outline notes (Markdown) into one file, then use ChatGPT to surface themes, common tasks, recurring needs, and role insights, working from condensed notes only.

## Inputs

- 20 to 60 outline notes in Markdown (a mix of recurring standups and customer meetings).
- Optional: a simple header line above each map:

```
### Meeting: <Title> | Date: YYYY-MM-DD | Type: Standup/Customer | Client/Topic: <X>
```

## Sampling (fast and representative)

Pick about one third standups, one third customer calls, and one third "other" (internal planning, vendors, and so on). Spread the sample across months (early, mid, recent) so you catch drift over time.

## Prep (keep tokens tiny)

1. Put all chosen notes files in one folder.
2. Create one combined file by copy and paste (or in a terminal: `cat *.md > notes_combined.md`).
3. Aim for 60 maps or fewer in the first pass. If the set is bigger, split it into chunks of about 20.

## Sprint flow (3 short passes)

### Pass 1: Theme Harvest (per chunk of about 20)

Prompt (paste before the chunk):

> SYNTHESIS, PASS 1 (notes only)
>
> From the notes below, output:
>
> 1. Theme List (10 to 20 items) with counts; merge synonyms (for example "invoices / billing / payment terms" becomes Billing).
> 2. Common Tasks (verb-first, 10 to 25 items) with counts.
> 3. Recurring Needs/Gaps (8 to 15).
> 4. Meeting Types to Typical Outcomes (Standup vs Customer).
>
> Keep bullets terse, no quotes, no inference beyond the notes. Return a Running Tally JSON first, then the readable lists.

Running Tally JSON (return first each pass):

```json
{
  "themes": {"Billing": 0, "Onboarding": 0, "Budget/Funding": 0},
  "tasks": {"Schedule customer follow-up": 0, "Draft scope": 0, "Send recap": 0},
  "needs": {"Clarify ownership": 0, "Timeline certainty": 0, "Data access": 0},
  "types": {"Standup": {"typical_outcomes": []}, "Customer": {"typical_outcomes": []}}
}
```

Counts are filled by the model; it merges obvious duplicates.

### Pass 2: Merge the Tallies (once, after all chunks)

Prompt:

> SYNTHESIS, PASS 2 (Merge Tallies)
>
> Here are the Running Tally JSON blocks from Pass 1 (paste them).
>
> - Merge them, de-duplicate keys, and normalize synonyms.
> - Return a Final Tally JSON (themes, tasks, and needs sorted by count, descending) and a Top-line Summary (150 words or fewer).

### Pass 3: Role and Playbook Insights (from the Final Tally)

Prompt:

> SYNTHESIS, PASS 3 (Role and Playbooks)
>
> Using the Final Tally JSON, produce:
>
> 1. Role Essence (evidence-based): 3 to 5 sentences describing what the role actually is in practice.
> 2. Top 10 Repeatable Tasks, each with a one-line "definition of done."
> 3. 3 Micro-Playbooks (checklists) for the highest-frequency patterns (for example Customer Debrief, Scope Draft, Comms Sprint).
> 4. Big-3 Gaps to Fix, each with a first action.
> 5. 7-Day Plan (3 outcomes, with guidance for 1 Deep Block and 1 Comms Sprint per day).

## Micro-Playbook template (use in Pass 3)

Playbook: <Name> (7 checks or fewer)

1. Trigger / when to use
2. Inputs needed
3. Steps (verb-first, 3 to 5)
4. Deliverable(s) (one sentence)
5. Timebox (for example 45 min)
6. Escalation rule (if blocked)
7. Hand-off note (who gets what)

## Outputs to save

- Final Tally JSON (themes, tasks, needs with counts)
- Role Essence paragraph
- Top 10 Repeatable Tasks (with definition of done)
- 3 Micro-Playbooks (checklists)
- 7-Day Plan (immediately actionable)

## QA checklist (2 minutes)

- Does the Top 10 Tasks list reflect what actually repeats in standups and customer calls?
- Are themes merged sanely (no duplicate wording for the same idea)?
- Does each playbook fit in 7 checks or fewer?
- Does the 7-Day Plan map to calendar reality (one Deep Block and one Comms Sprint daily)?

## Timebox

- Prep and combine: 20 to 30 min
- Pass 1 (3 chunks): 30 to 40 min
- Pass 2 merge: 10 to 15 min
- Pass 3 insights: 20 to 25 min
- Total: about 90 minutes for a high-signal review.
