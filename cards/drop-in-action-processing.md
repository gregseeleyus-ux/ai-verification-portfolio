---
title: "Default Drop-In Notes Processing (Outline-First Action Hub)"
category: "processing"
version: "2025-09-29"
status: "DESIGNED"
origin: "September 2025"
---

# Default Drop-In Notes Processing (Outline-First Action Hub)

This card merges two source cards that describe the same flow: a default processing run for meeting notes pasted with no prompt, and a lean notes-to-outline transform that serves as that run's optional first step.

## Purpose

Ensure a consistent, fast, useful output when a meeting summary and/or detailed meeting notes are pasted without any prompt. The assistant auto-runs the standard processing flow: no extras, no tools.

## Trigger

- The user pastes a meeting summary and/or detailed notes with no explicit instructions.
- The assistant proceeds immediately (no clarifying questions) using the rules below.

## Auto-response header (always show)

> Auto-run: No special prompt detected. Processed using the Notes to Action Hub (with Calendar Estimates) default flow.

## Inputs (detect and normalize)

- Summary: treat as primary if present.
- Detailed notes: if present, mine for section references and details.
- File name or link (optional): if provided, echo the file name in outputs.
- If only a link and no text: return a one-line ask to paste the text; otherwise proceed.

## Default processing steps (in order)

1. (Optional) Outline First: if a rough outline in Markdown is included, first convert it into a single-page outline with the headings Agenda, Outcomes, Decisions, Risks, Next 7 Days (see the Outline Transform section below). Use that outline as the spine for extraction.
2. Extract Actions: verb-first tasks; one owner; one outcome.
3. Add Estimates and Calendar Blocks: for user-owned items, compute effort_min and create a one-line calendar suggestion plus a paste-ready description.
4. Decisions / Risks / Reference Nuggets: keep terse; include section references when available.
5. Meeting Summary: 150 to 250 words, focused on "what changed" and "what happens next."
6. Micro-Plan: Today / Tomorrow / This Week.
7. Quality Checks.

## Defaults and heuristics

- Owner: if unclear, assign to the user and add a short clarifying subtask.
- Dates:
  - External or mentioned deadline: use it.
  - If not stated: internal work item due in 5 business days; external deliverable due in 2 business days; otherwise due_date: null and review_on in 3 to 5 days.
- Priorities: P0 (date-certain, legal, finance), P1 (unblocks others), P2 (nice-to-have).
- Source references: note the section or line of the source notes each item came from.
- Batching: 3 or more small comms become a Comms Sprint (30 to 45 min). 2 or more related reviews become a Review Sprint (60 to 90 min).
- Effort baselines (before buffer):
  - Comms nudges (1 to 2 messages): 15 to 20 min
  - Light review plus 1 to 2 deliverables: 30 to 45 min
  - Deep review or drafting: 60 to 90 min
  - Scheduling or admin (2 to 4 meetings): 25 to 40 min
  - Research or number pull: 30 to 60 min
  - Add about 20% buffer for ambiguity; round calendar durations to 15-minute increments.
- If multiple meetings are in one paste: process the most recent first; list the others under "Backlog to Process."

## Output order (exact)

1. Action Items (JSON): a single code fence; schema below.
2. Action Items (Readable List): append `Time: X min | Calendar: "<event title>" (<schedule hint>)` to each user-owned item.
3. Decisions
4. Risks/Issues
5. Reference Nuggets (with section references where possible)
6. Meeting Summary (150 to 250 words)
7. Calendar Block Plan: one line per user-owned item (plus batched sprints) with copy-ready event descriptions.
8. Micro-Plan: Today / Tomorrow / This Week
9. Quality Checks

## JSON schema (use exactly)

```json
{
  "actions": [
    {
      "task_id": "A-001",
      "title": "Verb-first action title",
      "owner": "User",
      "due_date": "YYYY-MM-DD or null",
      "priority": "P0|P1|P2",
      "status": "Backlog|Next|In-Progress|Blocked|Done",
      "context": "1-2 sentence rationale",
      "source_link": "https://...",
      "source_refs": ["notes section 2", "notes section 5"],
      "tags": ["Client: ...", "Project: ...", "Topic: ..."],
      "effort_min": 45,
      "batch_tag": "Comms Sprint A",
      "calendar_block": {
        "title": "Short imperative event title",
        "duration_min": 45,
        "schedule_hint": "ASAP (within 48h, morning focus)",
        "description": "Goal: <one sentence outcome>\nInputs: <files/links or file name>\nDeliverables: <bulleted outputs>\nNotes: <section references or constraints>"
      }
    }
  ],
  "decisions": [
    {"who": "...", "what": "...", "when": "...", "rationale": "...", "source_refs": ["..."]}
  ],
  "risks": [
    {"description": "...", "owner": "...", "next_review": "YYYY-MM-DD", "mitigation": "...", "source_refs": ["..."]}
  ],
  "references": [
    {"fact": "...", "reference": "...", "note": "..."}
  ]
}
```

## Quality checks (always include)

- Owners and due dates on Do Next items?
- Ambiguities flagged with a clarifying subtask?
- Duplicates merged? At least 3 reference nuggets?
- Effort and calendar present for all user-owned actions?
- Batching applied (if 3 or more small comms)?
- Micro-Plan matches the Calendar Block Plan?

## Style

- Crisp; bias toward fewer, better tasks (cap Do Next (48h) at 7 or fewer).
- No verbatim dumps of the source notes; focus on what to do and why.
- If a link to the source file is included, also echo the file name.

## Outline Transform (step 1 detail)

### When to use

- You have a rough outline in Markdown (even if the fuller notes or summary are messy).
- You want a one-page snapshot: Agenda, Outcomes, Decisions, Risks, Next 7 Days.
- If no rough outline is available, skip this step and run the normal flow above.

### Procedure (3 steps, about 2 to 3 minutes)

1. Paste the rough outline at the top of the ChatGPT run.
2. Run the Outline Prompt (A).
3. Immediately run the Action Hub prompt (B), telling it to use the Outline as the primary structure.

### A) Outline Prompt

> Rough Notes to Outline (Lean)
>
> Convert the following rough outline (Markdown) into a single-page outline with these exact top-level headings: Agenda, Outcomes, Decisions, Risks, Next 7 Days.
>
> - Keep bullets terse, unique, and non-duplicative.
> - If an item is unclear, add a short bracketed note [clarify: ...].
> - Do not invent owners or dates; just reflect what is present.
>
> Rough outline (MD):
> [paste rough outline here]

### B) Action Hub Using the Outline

> Run: Quick/Deep Mode + Calendar (Outline-First)
>
> Use the Outline above as the spine for extraction. If the fuller notes or summary conflict with the Outline, flag and reconcile briefly. Produce the standard bundle (Actions JSON first; then readable actions; Decisions; Risks; Reference Nuggets; Meeting Summary; Calendar Block Plan; Micro-Plan; Quality Checks).
>
> - For each user-owned action, include effort_min and a calendar_block (title, duration in 15-minute increments, schedule_hint, description with Goal/Inputs/Deliverables/Notes).
> - Keep Do Next (48h) at 7 or fewer.
> - Attach section references where available.

### What good looks like (outline rubric)

- Agenda: 3 to 7 bullets, reflects planned topics.
- Outcomes: clear end-state statements (what changed, was decided, or was learned).
- Decisions: who, what, when; one line each.
- Risks: concrete; owner and next review are added later during the action pass.
- Next 7 Days: only near-term items; the long tail belongs in Actions or Backlog.

### Tips

- If the outline is large, paste it in sections and run the Outline Prompt twice; the second pass should dedupe and compress.
- Keep the Outline visible above the Action output so you (and future you) can skim it in seconds.

## Dependencies

None beyond the pasted notes (summary, detailed notes, optional rough outline).
