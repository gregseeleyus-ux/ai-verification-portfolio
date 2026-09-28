# The Virtual Project Team Method

Status: PROTOTYPE (has produced real output more than once as a prompting practice; held below BUILT until the packaged cards in this repo have logged uses of their own)

## The idea in three sentences

Instead of asking an AI one question and getting one blended answer, you define a small team of expert perspectives (a strategist, an analyst, a systems engineer) as written role cards, and run your problem through them. Each card makes the AI hold one viewpoint with named standards, so you get distinct, arguable perspectives instead of mush. You are the decision-maker; the team advises.

## Why we think it works

A single AI answer tends to blend competing considerations into one even-handed voice. Role cards force separation: the risk view and the opportunity view stop canceling each other out inside one paragraph and instead argue on the page, where you can see the disagreement and judge it. The method turns intuition ("something feels off about this plan") into a structured pass ("the Navigator flags a dependency, the Ethicist flags a consent problem").

## How to run it

1. Pick two to four cards from vpt/cards/ that fit the problem. More is noise.
2. Load them with your question or draft. Ask each role to respond in character, then ask them to challenge each other.
3. When output quality drifts across a long session, add a project-manager instruction: a short standing note telling the team to keep answers tight, disagree openly, and end with a recommendation. In our sessions this has consistently cleaned up the output: shorter answers, open disagreement, and an actual recommendation at the end. We have not measured it formally.
4. Capture anything worth keeping as a short, single-topic Markdown file in the repo so the next session starts smarter.

## Making a new team member

Use vpt/templates/card-template.md. The rule from vpt/cards/README.md applies with no exceptions: real-person-inspired cards come only from public material, generalized and anonymized, framed as "a person of this kind," never a named individual. You are building an understanding of a perspective, not an imitation of a specific person.
