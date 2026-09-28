# Case Study: Measuring an AI Verifier

## The problem

I use AI to draft research on public legislative records: who sponsored a bill, how a member voted, what happened to it. The drafts read well and are sometimes wrong. The common failure is not an invented fact but a small one stated with confidence: a co-sponsor described as the sponsor, a vote read from the wrong line, a bill described as passed when it died in committee, or the one fact that changes the reader's conclusion left out.

A correction log from one research project traced nine errors to a single cause: a status asserted from a database grid or an AI summary without anyone reading the official roll call.

I had a verification skill (fresh-verify). I had never measured it. A verifier that has never been scored is an opinion.

## What I built

**A labelled test set.** Twenty items drawn from my own real research drafts, each with a known answer written down before any scoring. One was retired before scoring, leaving nineteen: eleven used while tuning the verifier and eight held back as unseen items.

- Wrong content: a claim that contradicts its source.
- Omissions: a draft that leaves out something the source makes essential.
- Clean controls: accurate drafts the verifier should pass. Without these, a verifier that flags everything would score perfectly.

Each item records its origin, the source, the defect type, the severity, the ground truth with a quote from the source, and what a correct catch looks like.

**An omission pass the verifier did not have.** Most verification checks what a draft says. It cannot see what the draft leaves out. I added a two-stage pass: one AI context sees only the sources and lists what a faithful draft must contain; a separate context checks the draft against that list. The verdict has three values: Pass, Pass pending confirmation, and Fail.

## Results

| Run | Wrong content caught | Omissions caught | Clean controls passed |
|---|---|---|---|
| v2.1, 10 items | 5 of 5 | 3 of 3 | 0 of 2 |
| v2.2, same items plus one | 5 of 5 | 4 of 4 | 2 of 2 |
| v2.2, 8 unseen items | 3 of 4, plus 1 partial | 2 of 2 | 1 of 1 (a second control was invalid; see below) |

**v2.1 failed.** It caught every defect and also failed both clean controls. It was over-flagging: its must-contain lists padded out to formatting details and treated every partial match as a failure. A verifier that fails good work gets ignored, which is worse than no verifier. I logged it as a loss.

**v2.2 fixed the over-flagging,** but I wrote those fixes after seeing v2.1 fail on the same items, so that clean result could be fitting to the test. I logged the caveat and built eight new items the verifier had never seen.

**On unseen items v2.2 held up,** with one partial catch: it held a vote as "pending confirmation" when the roll call format was one that reads reliably. That became a narrow rule change in v2.3, which then caught the item fully on a targeted rerun. The rule was written on that item, so that catch is not independent evidence either.

## What the testing surfaced beyond the scores

- **One of my own clean controls was invalid.** Its "correct" label had come from an AI summary rather than the source page. The test set had inherited the exact error it was built to catch. I excluded it, rebuilt it from the source text, and noted that the rebuilt item's pass came after a rule written on it, so it is not independent evidence.
- **The tooling misreads some sources.** A summarizing fetch tool read a confirmed No vote as Yes on one roll call format. The verifier now routes uncertain reads to a human as a named lookup instead of scoring on a misread.
- **A research check caught a retracted study.** Judging a briefing on AI verification practices, a quote-level spot check found that one cited study had been retracted by its own authors. A link-and-topic check would have passed it. The finding it supported still held on two independent studies.

## Why it matters

The rule I took from this: model agreement is not verification. Models from different vendors share errors, so a second model agreeing is a weak signal. Verification needs independent sources and at least one check no model controls: a primary record read directly, a checklist built from the sources alone, or a human lookup.

## Honest status

fresh-verify is PROTOTYPE: it works in limited scope and has been scored on items built from real research drafts, but not yet run on a live deliverable before it shipped. A live task is the next test. The test items stay private because they contain unpublished research; the design, the scoring rules, and a blank template are in [templates/VERIFY-TESTSET.template.md](templates/VERIFY-TESTSET.template.md).
