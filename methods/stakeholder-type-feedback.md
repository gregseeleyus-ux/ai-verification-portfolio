# Stakeholder-Type Feedback Simulation

Status: DESIGNED (rebuilt from an earlier prototype; this anonymized-type version has not been run)

## What it is

A way to test a draft before real readers see it by running it through the voices of the kinds of people whose judgment decides its fate: for a book or proposal, the creator who wants specific questions answered, a first-time reader, and the gatekeeper who says yes or no (an acquisitions editor type). Each voice is a stakeholder type, a composite built from public material, never a simulation of a real, named person. It is a domain variant of the Virtual Project Team (vpt/README.md): the roles are the draft's stakeholders rather than a consulting team.

## When to use it

- A draft is about to go to a gatekeeper (an editor, a funder, a buyer, a review board) and you want a realistic accept or reject read first.
- You want to know which questions real readers should be asked before handing the draft to them.
- You have been too close to the draft to see how a first-time reader will meet it.

## Consent rule

No exceptions: stakeholder types are composites built from public material (published submission guidelines, interviews and talks, craft and industry writing), generalized and anonymized. Name the type by role ("an acquisitions editor type at a genre imprint"), never by a real person's name. Never simulate a specific person you actually work with. If a type cannot honestly carry the provenance note in the card template, do not build it.

## How to run it

1. **Pick the types.** Choose two to four stakeholder types whose reactions matter for this draft. Example types for a book or proposal:
   - **Creator type:** the author or owner of the work. Generates the questions they most want beta readers to answer.
   - **Gatekeeper type:** for example an acquisitions editor type. Reads the draft as a submission and gives a market-realistic accept or reject verdict with reasons.
   - **First-time reader type:** a lay reader with no background. Leaves chapter-by-chapter (or section-by-section) notes: questions, reactions, and flags where something pulled them out of the piece.
2. **Build each type as a card.** Use vpt/templates/card-template.md: the lens, what the type focuses on, the standards it holds, what its output looks like, and the provenance note stating the public sources and that the card is a generalized composite.
3. **Run the draft through each voice.** Load one card with the draft and ask for that type's output in character. Run each type separately so the voices stay distinct.
4. **Collect the outputs side by side** and decide what to change, the same way you would weigh a panel in vpt/README.md (step 2: load the voices, then have them challenge each other). You remain the decision-maker; the types advise.
5. **Use the creator-type questions with real readers.** The simulated question set is a starting point for real beta readers, not a replacement for them.

## Output

- A beta-reader question set (creator type).
- An acquisition memo with an accept or reject verdict and its reasons (gatekeeper type).
- Section-by-section reader notes with flagged moments (first-time reader type).

## Template

```
DRAFT: [title]  STAGE: [draft number]

TYPES (each built from vpt/templates/card-template.md, provenance note filled)
1. [role, e.g. creator type]            Card: [file]
2. [role, e.g. acquisitions editor type] Card: [file]
3. [role, e.g. first-time reader type]   Card: [file]

CREATOR TYPE: questions for beta readers
1. ______________________
2. ______________________
3. ______________________

GATEKEEPER TYPE: acquisition memo
Verdict: [ ] Accept  [ ] Reject
Reasons: ______________________

FIRST-TIME READER TYPE: notes
Section | Note or question | Pulled me out? (Y/N, where)
________|__________________|__________________________

DECISIONS
Change: ______________________  Prompted by: [type]
```
