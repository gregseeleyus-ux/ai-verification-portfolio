---
name: book-recon
description: "Reconstruct a book's useful content from web sources when the book is not in hand and no PDF is available. Produces a triage verdict up front (read, skim, or skip), then harvests transferable tools (frameworks, heuristics, data, arguments) for the user's own work. Trigger whenever the user names a book they want to evaluate without reading it, hears about one and asks whether it is worth their time, asks to run recon or a thread on a book, wants the key ideas or frameworks from a book they do not own, or asks whether to buy or borrow it. Trigger even with no PDF present and even if the user does not say report or analysis. Inherits guardian-context standards and voice (classify down not up, confidence tagging, no emojis or em-dashes); load guardian-context first if available."
---

# Book Recon

## What this is, and what it is not

This skill reconstructs a book from secondary sources (reviews, summaries,
author interviews, excerpts) because the book itself is not in hand. It is not
a fidelity instrument. You cannot promise insight "derivable only from reading
the book," because you are not reading the book. Pretending otherwise produces
a confident report built on other people's flattening and errors.

Treat this as two different jobs, in this order:

1. Triage. Decide whether the book is worth acquiring. Deliver this verdict
   first, before any deep work, so the user can stop early.
2. Harvest. Pull the transferable tools the user can lift into their own work
   now (for example consulting, policy, advocacy, or research), even if they
   never read the book.

A useful side effect: secondary sources are worse than the book at thesis
fidelity but better at one thing the book never does, which is naming its own
weaknesses. Expert reviews surface critical gaps better than the author ever
will. Lean into that.

## Before you search: check what you already have

Do not open with a web search. Two cheap checks first, because the most
expensive failure this skill has is running a full reconstruction on a book
that is already in hand or already reconned.

- In hand or reachable. Confirm the premise. Is the book uploaded to this
  session, sitting in the project files, or plainly available as a legitimate
  full text? If so, this skill is the wrong tool: read the source directly
  instead of reconstructing it from summaries. Say so and stop.
- Already reconned. Check the project's knowledge files for prior recon on
  this book or this author before searching fresh. If a prior harvest exists,
  build on it rather than duplicating it, and spend the search budget only on
  what is missing.

Then read the ask, do not just read the title. How the user asked sets what
the run optimizes for, and it changes which sources to reach for first:

- "Should I buy it / is it worth my time" weights the triage verdict. Get to
  Read/Skim/Skip on the cheap pass and do not over-harvest.
- "Pull the frameworks / what are the models" weights the harvest. Prioritize
  Tier 1 talks and Tier 3 structured summaries where named models surface.
- A bare title with no stated purpose defaults to triage-first, full flow.

Infer this silently from the phrasing. Ask a clarifying question only when the
intent is genuinely ambiguous and the two readings would send you to different
sources. A forced question on every run fights this skill's job, which is a
fast verdict before deep work.

## The flow: triage first, harvest only if warranted

### Stage 1: Triage pass (cheap, 1 to 2 searches)

Run a minimal pass to produce the verdict block at the top of the output:

- One search: title plus author plus "summary." Confirm the book exists, get
  publication facts, and get the one-line thesis.
- One optional search if the thesis is still fuzzy: title plus "review."

Then issue the verdict:

- Read: high transferable value, contested or novel claims worth verifying in
  the source. Proceed to Stage 2 in full.
- Skim: useful skeleton or one or two good frameworks, but most value is
  capturable from summaries. Proceed to Stage 2, lighter.
- Skip: derivative, thin, or outside the user's use. State why in two
  sentences and stop. Do not run the harvest.

Do not proceed past the verdict on a Skip unless the user overrides.

### Stage 2: Harvest pass (bounded, cap at 4 to 6 total searches)

Stage the remaining searches and do not exceed the cap. Snippet-grazing across
ten thin pages is what makes these threads spiral and fail. Fetch full text on
the two or three highest-value pages instead.

- Author's own framing: one search for an author interview, talk, or adapted
  essay. Best source for thesis and arguments in the author's words.
- Critical or expert review: one search targeting a serious outlet or a domain
  expert. Best source for gaps and contested claims.
- Targeted fill: one optional search only to nail a specific framework or a
  disputed claim that the report depends on.

## Route each section to its best source

Do not treat all sources as one bucket. Each section has an optimal source.
Reach for higher tiers first.

Source tiers, most to least reliable:

- Tier 1, author speaking for themselves: long-form podcast interviews about
  the book, talks, adapted essays or op-eds, published excerpts or the free
  first chapter (the intro usually states the thesis outright), and publisher
  jacket copy (use only to confirm, since marketing inflates).
- Tier 2, expert and critical secondary: long reviews in serious outlets,
  reviews by domain experts in the book's field.
- Tier 3, compiled and derivative: Shortform, getAbstract, Blinkist, Four
  Minute Books (good for the skeleton, weak on nuance); Goodreads and Amazon
  (use only for recurring criticism and reception sentiment, not content);
  Wikipedia (good for context and publication facts, weak on argument logic).

Fall-through rule. Reach for the best source class for a section first. If it
does not exist or does not surface within the search cap, drop to the next
class down, tag the section at the lower confidence that source earns, and move
on. Do not burn extra searches hunting for a Tier 1 source that is not there,
and do not leave a section empty and call it a gap when a Tier 2 or Tier 3
source would fill it at lower confidence. A section filled from a weaker source
with an honest confidence tag beats both an empty section and a spiral of
searches. The one exception is quotes: never drop a tier to manufacture one,
because the fallback there is fabrication, not lower confidence.

Section to source mapping:

- Central thesis: Tier 1 interviews plus the free intro plus jacket copy.
  Triangulate all three.
- Main arguments and structure: Tier 3 structured summaries plus Tier 1
  interviews.
- Frameworks and mental models: Tier 1 talks plus Tier 3 summaries. Highest
  yield from the web, because named frameworks are built to be portable.
- Key evidence: reviews and summaries, but flag that evidence quality cannot be
  verified without the text. This is where web sourcing is most dangerous.
- Counterarguments the author acknowledged: Tier 1 only. Reviews will not give
  you this.
- Critical gaps: Tier 2 expert reviews. Single best source, better than the
  book itself.
- Quotes: only verified direct quotes from excerpts or from reviews that quote
  the book directly. Never reconstruct a quote from a paraphrase.

## Confidence tagging

Tag every substantive claim, since none of it is checked against the text.
Classify down, not up. Use:

- Confirmed: multiple independent source types agree (for example author plus
  two reviews).
- Single-source: only one source asserts it.
- Inferred: synthesized or reconstructed, not directly stated anywhere.
- Disputed: sources disagree. Name the disagreement.

Weight by substance, not just count. A source's depth governs how much it can
carry. A forty-minute author interview or a long expert review is a load-bearing
source. A two-line blurb, a stub summary, or a listicle entry is not, and two of
them agreeing is not a Confirmed claim. Three thin sources echoing the same
marketing line are one source, not corroboration. Before a source counts toward
a confidence tier, ask whether it has enough substance to be wrong in an
interesting way. If it does not, it is reception signal at most, not evidence of
content.

## Output format

Always open with the verdict block and the confidence ceiling, so the
deeper-dive decision is the first thing the user sees.

```
# Book Recon: [Title]

VERDICT: Read | Skim | Skip
One to three sentences on why, written for the user's use, not a neutral
blurb. One line on what would flip the verdict, for example: Skim flips to
Read if the central framework turns out to be original rather than
repackaged, which only the text settles.

Confidence ceiling: [how much of this report is confirmed versus
reconstructed, in one line, so the user knows how far to trust it before
acting]

Title: [title]
Author: [author]
Genre: [genre and subgenre]
Year: [year if determinable]
Core purpose: [one sentence on what the book exists to do]
```

If the verdict is Skip, stop here. Otherwise continue with the harvest, using
the framework that matches the genre. Non-fiction is the default below; for
other genres swap section labels per the note at the end.

### Non-fiction harvest (default)

Tag each claim with a confidence marker. Write analytical sections as prose.
Use lists only where they aid comprehension (arguments, evidence, tools,
quotes).

- Transferable tools: the harvest, and the point of the whole exercise. The
  specific frameworks, heuristics, phrasings, or data points the user can lift
  into their own work (for example consulting, policy, advocacy, or research).
  Be concrete about how each could be used.
- Central thesis: the single core claim, stated precisely, not "the author
  argues mindset matters."
- Main arguments: the three to six logical moves that build the thesis, not
  chapter summaries.
- Key evidence: the strongest data, studies, or cases cited, with an explicit
  flag that quality is unverified from secondary sources.
- Frameworks and mental models: each named model, what it explains, and where
  it breaks down.
- Critical gaps: what reviewers and experts say the book overstates, overlooks,
  or gets wrong. Pull hard from Tier 2 here.
- Contested claims: where sources disagree about what the book says or whether
  it holds up. Useful for debate and policy work.
- Best quotes: three to five verified short quotes, attributed, each kept brief.
- Primary source pointers: where to go to verify or go deeper. Name the
  specific podcast episode, the free intro link, the one review worth reading.
  This makes the report a map back to sources.

### Fiction, history, biography, memoir

Same triage-first flow and same source tiering. Swap the harvest sections:
for fiction use themes, plot architecture, character, narrative technique,
symbolism, worldview, tone; for history or biography use central
narrative or argument, the arc, key figures, causes and consequences, author
bias, lessons, standout revelations. Keep transferable tools, critical gaps,
confidence ceiling, and primary source pointers in every genre, since those
serve the triage and harvest purpose regardless of form.

## Quality standards

- Every sentence carries information specific to this book. Generic
  observations that fit any book in the genre are waste.
- Separate clearly what the author claims, what sources confirm, and your own
  judgment.
- Never fabricate or paraphrase-as-quote. If you cannot find a verified quote,
  describe the passage instead.
- Keep quotes short and use no more than one per source.
- No emojis, no em-dashes, no icons, in keeping with the guardian-context
  house style.
- If sources are thin or conflicting, say so plainly and lower the confidence
  ceiling rather than padding the report.
- On request, write the transferable tools into the project's knowledge
  files per the memory-hygiene convention in guardian-context Section 8:
  one tool per entry, dated, tagged with its confidence level and the
  book as source. Offer this in one closing line; do not do it unasked.
