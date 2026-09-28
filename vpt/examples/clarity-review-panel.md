# Worked Example: A Five-Role Review Panel on Documents About to Be Shared

Method: Virtual Project Team, run as a review panel. Status of the underlying method: PROTOTYPE (see vpt/README.md).

## The input

A set of methodology documents the day before their first outside readers saw them. Real stakes: the author had been too close to the documents for too long to see what a first-time reader would see.

## The method applied

Five reviewer roles were written for the occasion, each defined the way a card in vpt/cards/ is: a lens, what it focuses on, and the standards it holds. A Cold Engineer (technical, allergic to hand-waving; flags every term used before it is defined and every instruction that cannot be executed from the page alone). A Plain Reader (smart, non-technical; flags every sentence that must be read twice). A Fierce Editor (hunts AI-flavored prose: symmetric slogans, confident abstractions, invented terms treated as established). A Domain Practitioner (long experience in the field the documents address; flags anything a working professional would find naive or dispute on sight). A Measurement Skeptic (attacks the design's core assumption about what can be measured and who measures it).

Each role ran in its own fresh AI session, reading only the documents, with no access to the conversations in which they were written. Two rules did most of the work:

1. Every finding had to include the offending sentence rewritten as it should read. A finding without a demonstrated fix was dropped as opinion.
2. Every finding carried one of four classifications: blocks comprehension, undermines credibility, jargon needing definition, or cosmetic.

A chair then reconciled the five reads into one report, with two tiebreakers: comprehension beats elegance, and honesty beats confidence.

## The output

Dozens of findings, each with a proof-of-fix rewrite, a ruling on every invented term (keep and define, replace with ordinary words, or cut), a verdict per file, and a closing list of the three changes that would most improve the set. Nothing needed a rewrite, but almost every file needed sentence-level fixes before sharing. The defects clustered into three classes: claims of measurement with no named measurer (who grades, on what schedule, and how a grade is disputed), pages promising artifacts the folders did not contain, and working vocabulary from the author's own practice leaking into pages for readers who had never seen it. Every fix was applied before the documents were shared.

## What the panel caught that a single review would have missed

The value came from convergence and specialization, and you need several independent readers to get either. A few sentences were flagged independently by four or five of the roles, which is how you learn a first-time reader will certainly trip there rather than possibly. And the two most important single findings each came from exactly one role: only the Measurement Skeptic noticed that a summary claimed more supporting precedents than its own body documented, and only the Domain Practitioner caught that a result from one setting was being applied to a setting where its key assumption did not hold. A single reviewer, however good, reads with one set of instincts; the panel's value was that each role found the failure its lens exists to find, and the chair only had to referee.

## Try it yourself

Pick three to five roles whose blind spots differ, run each in a clean session on the same documents, require a rewrite with every finding, and reconcile with explicit tiebreakers. The roles here were written for this job; the six standing cards in vpt/cards/ work the same way for strategy and planning questions.
