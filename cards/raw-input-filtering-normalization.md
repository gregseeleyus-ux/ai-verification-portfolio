---
title: "Raw Input Filtering and Normalization"
category: "processing"
version: "1.0"
status: "PROTOTYPE"
origin: "December 2025"
---

# Raw Input Filtering and Normalization

Scope: a ChatGPT project space used for work intake.

## Purpose

This card defines how raw, messy, or high-volume inputs are handled in the project space before they are used for analysis, drafting, or transfer into other systems.

It exists to:

- Prevent garbage-in, garbage-out
- Reduce noise from raw, unedited notes
- Separate capture from interpretation
- Normalize information into usable forms

It applies broadly across use cases, including but not limited to:

- Weekly updates
- Brain dumps
- Meeting notes
- Email or calendar exports
- AI-generated summaries
- Mixed or unsorted materials

## What counts as raw input

Raw input is any material that is:

- Unstructured or loosely structured
- Over-detailed or repetitive
- Mixed across topics, projects, or timeframes
- Written as raw notes rather than for decision-making
- Not yet shaped for a specific output

Examples:

- Full raw notes or logs
- Bulk summaries
- Long task lists
- Combined notes
- Unfiltered AI outputs

## Role of ChatGPT in this step

ChatGPT functions as:

- A filter
- A normalizer
- A sanity check

ChatGPT does not function as:

- A judge of importance
- A priority engine
- A decision-maker
- A replacement for human judgment

## Core processing passes

Apply these passes in order, regardless of use case.

### Pass 1: Noise reduction

Remove or ignore:

- Speculation, hypotheticals, or AI "suggestions"
- Brainstorming not tied to action or state
- Repeated details that add no new information
- Personal reminders unrelated to the work in scope
- Commentary without factual grounding

### Pass 2: Fact extraction

Identify factual elements related to:

- Actions taken
- Information received or produced
- Decisions made or deferred
- Commitments or dependencies
- Constraints or conditions
- State changes

Do not interpret significance. Extract facts only.

### Pass 3: Normalization

Rewrite extracted facts into clear, neutral, declarative language.

Examples of normalized phrasing:

- "Prepared..."
- "Received..."
- "Awaiting..."
- "Confirmed..."
- "Next step depends on..."

Normalization is about clarity, not polish.

### Pass 4: Sorting by destination

Group normalized information by where it will be used next, such as:

- Weekly updates
- Project tracking
- Follow-up drafting
- NotebookLM ingestion
- Reference notes

If the destination is unclear, leave it unsorted.

## What this card does not do

This process does not:

- Decide what matters most
- Rank priorities
- Evaluate performance
- Collapse uncertainty
- Rewrite into final outputs
- Force conclusions

It prepares information so human judgment can be applied cleanly.

## Success criteria

This card is working when:

- Messy inputs feel manageable
- Important facts are easy to see
- Downstream systems receive cleaner material
- Less re-reading and second-guessing is required

If this step feels like drafting or analysis, it is being overused.

## Position in the overall workflow

Raw inputs then ChatGPT (filtering and normalization) then downstream use (NotebookLM, drafting, tracking sheets, analysis)

This card is foundational and reusable across workflows.
