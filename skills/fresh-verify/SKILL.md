---
name: "fresh-verify"
description: "Runs a fresh-context verification pass on a finished deliverable before it ships: checks every claim, quote, figure, citation, and attribution verb against the provided sources, runs a separate omission pass for facts and caveats the sources require but the draft leaves out, and returns a pass or fail verdict with failures listed by item. Use when the user asks to verify, fact-check, source-check, check for omissions or what is missing, run a verification pass, run fresh-verify, or clear a document for review, especially in a clean conversation containing only the deliverable and its sources. Covers research reports, policy plans, comparison documents, briefs, and any product with sourced claims. Distinct from adversarial-pass, which attacks strategy and framing; this skill verifies factual fidelity and completeness only. Load guardian-context first if available."
---

# Fresh Verify

An independent verifier for finished deliverables. The drafter should not
be the sole grader of its own work; this skill is the second grader,
designed to run in a conversation that contains only the deliverable and
the sources it cites, with none of the drafting history. If drafting
history is present in the conversation, say so in the output and label the
result a first pass, not a clearance.

## Role and scope

Verify factual fidelity and required completeness. Two error classes are
in scope: content that is wrong (added, altered, misattributed) and
content the sources require that is absent (a fact, qualifier, caveat, or
counter-evidence a faithful product on this assignment must carry). Flag
only failures that affect correctness or the deliverable's stated
requirements. Do not propose stylistic improvements, strategic changes, or
discretionary additions; a verifier that reports taste findings buries the
correctness findings. Strategy and framing attacks belong to
adversarial-pass. Do not fix failures in place; report them by item so the
drafting context makes the corrections and the verifier stays independent.

These are two different checks because model verifiers detect wrong
content well and missing content at close to chance. Asking a reviewer
"is anything missing?" does not work; the omission pass below replaces
that question with closed per-item checks.

## Framing the verifier

Apply the guardian-context Neutral Verification Prompts rule. The
deliverable is presented as a third party's submission, never as the
verifier's own earlier work. The request states what to check, not what
the drafter believes or hopes the answer is. Never tell the verifier the
material has been reviewed or is trustworthy.

## Fire threshold

Run on deliverables headed to an external audience or a decision: client
delivery, leadership or reviewer handoff, publication, or a financial or
legal choice. Internal scratch work does not need a pass. The omission
pass runs in full when the deliverable carries load-bearing claims; for a
short external item with no load-bearing claims, run the faithfulness
checklist only and say so in the pass line. A repeat pass after
corrections rechecks only the failed items plus any item the corrections
touched.

## Inputs required

The deliverable, the sources it cites, and the assignment it answers (the
brief, request, or question). If a cited source is not provided and not
reachable, the claims resting on it are marked unverifiable, not assumed
good. If the deliverable type has a house checklist (below), apply it;
otherwise apply the general checklist.

Source access: when a load-bearing source can only be read through a
summarizing fetch and the reading is uncertain, mark the claims resting
on it needs-confirmation and name the exact fact for the user to look up.
Do not score them pass or fail on an uncertain read. Uncertain means a
format whose meaning a summarized read can lose: roll calls that mark
votes with an X in columns are misread by summarizing tools, and the same
holds for scanned tables and struck-and-underlined bill text. Roll calls
that print a vote letter beside each name read reliably: score the claim
on such a roll call, matching the member by initials when two members
share a surname, and fail a draft the text contradicts. When other text
that reads reliably decides the claim on its own (totals, dates, roll
call numbers), score it on that text; the needs-confirmation mark applies
only when the uncertain read is the deciding evidence.
A direct text capture of the source is reserved for critical research;
for everything else, a lookup request is the default.

## Faithfulness checklist, per claim

1. Quote fidelity: verbatim quotes match the source exactly, including
   names, numbers, dates, and punctuation that changes meaning.
2. Paraphrase support: the stated claim is supported by the cited passage
   itself, not by surrounding context the reader will not see. Quote the
   supporting span. A claim the cited source addresses but does not
   support fails. A claim the cited source does not address at all is
   unverifiable, not a failure: list it with the record that would settle
   it.
3. Figure fidelity: numbers, units, dates, and dollar figures match the
   source; derived figures show a reproducible calculation.
4. Attribution verbs: the verb is defensible. Use precise verbs (voted
   for, voted against, sponsored, co-sponsored, introduced, supported,
   opposed, said, wrote, signed); stronger verbs (authored, secured,
   delivered, championed, led, spearheaded) need a source that says so.
   Downgrade any verb the source does not explicitly support.
5. Citation resolution: the link works, the date is right, and the source
   is what the citation says it is. A resolving, on-topic link is necessary
   but proves nothing about the claim; items 2 and 3 carry the weight.
6. Label fidelity: confidence tags and source tiers are correct per the
   guardian-context claim-level definitions; nothing Extrapolated,
   single-source, or supported only by model agreement is presented as
   Verified.
7. Internal consistency: no figure, date, or name contradicts another
   instance of itself elsewhere in the deliverable.
8. Corroboration: each load-bearing claim rests on two independent evidence
   chains. A load-bearing claim resting on one document that states the
   conclusion directly is flagged single-chain, even when that document
   looks authoritative.

## Omission pass

Stage 1, list: a context that sees only the sources and the assignment,
never the deliverable, lists the must-appear items: each fact, qualifier,
caveat, or piece of counter-evidence in the sources that a faithful product
on this assignment must carry. List what the assignment requires, not
everything the source contains; three to six items is typical, and a
padded list turns every draft into a Fail. Each item gets a severity and
the source quote that establishes it:
- Critical: its absence would change what the reader concludes or
  decides about the assignment's question.
- Material: its absence would mislead a reader on a secondary point.
- Minor: detail. Record-keeping details (time stamps, excused counts,
  certification lines, roll call housekeeping) are minor unless the
  assignment asks for them.

Stage 2, check: a separate context holding the deliverable and the
Stage 1 list answers present, partial, or absent for each item, one closed
question per item, quoting the deliverable span for present or partial.
A restatement elsewhere in the deliverable counts as present only if it
carries the same fact, not a vaguer version of it. A draft that states
the item in the source's own operative words (for example "postponed
indefinitely" where the list says the bill died by indefinite
postponement) has it present; do not mark it partial for omitting a
gloss the source itself does not require.

Where subagents are available, run each stage as its own agent. Where they
are not, complete the Stage 1 list before opening the deliverable and
label the omission result a first pass. Flag on any critical item that
is absent, or partial where the missing part is itself critical; do not
average item results into a coverage score, which hides the signal.
Material and minor gaps are reported as notes and do not fail the pass.
For load-bearing products, the user reviews the Stage 1 list before
Stage 2 runs, because this method still misses most omissions and a human
check of the list is the cheapest improvement.

## Product-specific checklists

Research products (research files, public-record and legislative record
reviews): apply escalated verification to claims of absence, enforcement,
sponsorship, status and vote, and version. At minimum check:
- Sponsorship position: the draft states the subject's role on a bill or
  measure (sponsor, cosponsor, or neither) exactly as the official record
  shows it.
- Vote attribution: every vote claim is checked against the official roll
  call, not a secondary summary.
- Verb discipline: attribution and vote characterization verbs pass
  checklist item 4; downgrade any verb the record does not support.
- Loaded-term flag: flag loaded terms, including politically loaded bill
  titles, that the draft repeats as neutral description.

Consolidations of multiple drafts into one version (if you have a domain
consolidation skill, apply its source pass): check that retained language
traces to a source draft and that any preservation rules set for the
consolidation are honored.

Comparison documents and stat-bearing public materials: apply the general
checklist plus the rule that unverifiable figures are dropped, not
softened.

## Returning results to an agent

When the drafter is the user or a session the user supervises, report
failures by item as below. When the drafter is an autonomous agent working
unattended, return a generic fail with item locations only, and keep this
checklist and the Stage 1 list out of the agent's context. This is a
precaution: early evidence (one preprint, in which the detailed-feedback
condition also carried attempt history) links detailed reviewer feedback
to higher agent evasion, but the effect of the reasons alone is not
established.

## Output contract

Open with one of three verdicts:
- Pass: no failures and no critical absences.
- Pass pending confirmation: no failures or critical absences, but one or
  more load-bearing claims are unverifiable or need-confirmation; name
  each fact to confirm.
- Fail, with the failure count: any failure, or any critical absence.

Then:

- Failures, listed by item: location in the deliverable, the checklist
  item failed, and the source span that shows the correct content, in one
  to three lines each. Name the defect; do not score it.
- Omissions: each critical item marked absent or partial, with its
  source quote. Material gaps follow as a short notes list; minor gaps
  are not reported.
- Single-chain flags: load-bearing claims resting on one document.
- Unverifiable and needs-confirmation items: claims the provided sources
  do not address, or could not be read reliably, listed separately from
  failures, each with the record or lookup that would settle it.
- Pass line: the pass date, whether the context was clean or carried
  drafting history, and whether the omission pass ran in full, first-pass
  mode, or was skipped under the fire threshold.

A deliverable with any failure on a claim bound for external use repeats
the pass after correction. Do not soften a Fail to be polite, and do not
pad a Pass with taste findings to appear thorough.

## Measuring this skill

If you maintain a verification test set (create VERIFY-TESTSET.md from
templates/VERIFY-TESTSET.template.md), changes to this skill are scored
against its labelled items before promotion, logging the catch rate for
wrong content, the catch rate for omissions, and the false-alarm rate on
clean controls as separate numbers. A clean control scored Pass or Pass
pending confirmation is not a false alarm. Log each scoring run in
SKILLS-RECORD.md (create it from templates/SKILLS-RECORD.template.md).
