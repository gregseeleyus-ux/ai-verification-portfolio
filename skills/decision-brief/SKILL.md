---
name: decision-brief
description: "Structures a real decision into a one-page brief that ends in a mandatory verdict: frames what is being decided and by when, prices the options including doing nothing, and delivers a recommendation with confidence and the evidence that would flip it. Use when the user is weighing a choice, asks what they should do, asks for a decision brief, is comparing paths on timing, money, career, or business questions, or is circling a decision across multiple messages without landing it. Handles business, consulting, career, and personal-professional decisions in a single pass rather than convening a multi-seat panel. Load guardian-context first if available."
---

# Decision Brief

Turns an open decision into a closed one or names exactly what is blocking
closure. The failure this skill exists to counter is verdict avoidance:
analysis that circles, options held open past their value, and "it depends"
with no named dependency. Every run ends in a verdict per the
guardian-context Verdict Rule. This is a decision instrument, not
counseling; it prices options, it does not process feelings.

## Fire threshold

Fire on decisions with real stakes and a genuine fork: money, timing,
career, business commitments, resource allocation. Do not fire on trivial
choices, on questions with a single defensible answer (answer directly),
or on decisions that belong to someone else (brief the input, not the
verdict). If the same decision has surfaced across multiple conversations
without closing, that is a signal to fire, and the brief should say the
decision is aging.

## Structure of a run

Hold the whole brief to roughly one page. Gather before judging; judge
before recommending.

Frame. State the decision in one sentence, the real deadline (and whether
it is external and hard or self-imposed and soft), what is reversible
about each path and what is not, and who else the outcome binds.

Options. Two to four live paths, always including the do-nothing default,
priced like the others: doing nothing is a choice with costs and is where
verdict avoidance hides. For each option: what it wins, what it costs,
what it forecloses, and the probability-weighted read where numbers exist
(use real figures from the runtime files or from the user; do not invent
financial inputs). Kill options that are not genuinely live rather than
carrying them for balance.

Evidence check. Tag the load-bearing facts per the evidence standard.
If the verdict would change based on an unverified fact, the brief says
so and names the check.

Verdict. The recommended path, its confidence tag, the strongest argument
against it, the single piece of evidence that would flip it, and the
first concrete action with a date. If the verdict genuinely cannot be
given, that is the finding: name the one blocking unknown, who or what
resolves it, and the date by which waiting stops being information
gathering and becomes the do-nothing option in disguise.

## Standing rules

- Deadlines are load-bearing. A decision without a date is a preference,
  not a decision; if no external deadline exists, the brief proposes one
  and says it is proposed.
- State the decision's history if it has one: what was previously decided
  or deferred, per the runtime record, so the brief does not relitigate
  settled ground.
- Sunk costs are named as sunk and excluded from the pricing.
- Where the decision touches a domain that has its own skill (a domain
  skill, if you have one, such as a research, finance, or policy skill),
  pull its standards rather than duplicating the analysis; this skill
  owns the closure, not the domain expertise.
- One brief, one decision. Compound decisions get split, sequenced, and
  the brief says which one is actually first.

## Output contract

The one-page brief in the structure above, verdict last and mandatory.
Close with the first action and its date. If the user overrides the
verdict, that is their call to make; record the decision taken and the
reason in the project's runtime file per memory hygiene, so the next brief
on adjacent ground starts from what was actually decided.
