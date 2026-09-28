# VERIFY-TESTSET

Runtime file. A labelled sample of your own deliverables with known
defects, used to measure any verification component (fresh-verify, the
evidence audit in adversarial-pass, the spot-check in research-run) before
a change is promoted. Published benchmark results do not transfer to your
documents on their own; this set is how a change proves itself on your
material.

## Target composition

- 30 to 50 items total.
- At least one third omissions (a critical fact, caveat, qualifier, or
  counter-argument the sources require, missing from the draft).
- The rest split across: altered figure or date, misattributed or
  overstated verb, fabricated or unsupported claim, single-chain
  load-bearing claim, wrong name.
- About one in five items are clean controls with no defect, to measure
  false alarms.

## Item format

- ID: VT-###
- Origin: historical (a real error that happened) or planted (a defect
  introduced into a verified deliverable)
- Assignment: the question the draft answers
- Draft excerpt
- Sources: file names or links
- Defect type: omission / figure / verb / fabrication / single-chain /
  name / control
- Severity: critical / material / minor
- Ground truth: the defect stated exactly, with the source quote that
  proves it (for controls: "none")
- Expected catch: what a correct verifier output names
- Ground-truth status: verified (read in the primary source) or needs
  confirmation

## How to build items

1. Historical: pull real errors you or a reviewer caught, with the draft
   and sources as they stood before correction.
2. Planted: take a deliverable that already passed review, keep the
   original, and make variants that each change one thing. One defect per
   variant.
3. Never take role or status labels for an item (for example "primary
   sponsor", "passed") from an AI summary. Take them from the record
   text, or leave them out.
4. Keep the item file separate from anything the verifier sees. The
   verifier under test sees only the assignment, the draft excerpt, and
   the sources.
5. Add unseen items after any change you tuned on existing items; tuned
   results are not independent evidence.

## Scoring

Per scoring run, log in SKILLS-RECORD: skill and version, items run,
catch rate on wrong content, catch rate on omissions, false-alarm rate on
controls. Keep the three numbers separate; a combined score hides the
omission gap. A clean control scored Pass or Pass pending confirmation is
not a false alarm.
