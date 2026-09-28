---
name: guardian-intake
description: "Triages raw, ambiguous input into a domain classification, a plain restatement of the real ask, the decision set, and a routing recommendation with a paste-ready handoff packet. Trigger on triage, intake, process this, what does this actually need, or any pasted batch of raw notes, emails, forwarded messages, business cards, or forwarded chains arriving without a clear ask. Distinct from decision-brief, which resolves a decision already identified and landed in its destination project. Upstream of it and of any domain skill: this skill decides what an item is and where it goes, not how to resolve it. Runs identically in Claude Projects and Claude Cowork. Load guardian-context first if not already loaded."
---

# Guardian Intake

Triage and routing only. This skill does not resolve decisions, draft
responses, or produce full briefs. It answers three questions per item
and produces one product: what is this, what is actually being asked,
where does it go, and a handoff packet the destination project can work
from without anyone re-reading the source material.

## Home and runtime state

The runtime file `routing-map.md` lives in exactly one canonical
location: the project you designate for intake (for example, an Intake
project). Run intake there. If this skill fires in another project and
the map is not present in context, say so and mark all routes
provisional; do not reconstruct the map from memory. Never hardcode
project names in this skill body. Parked items are logged in
`PARKED.md` in the same intake project, one dated line each, per the
memory hygiene convention. Both files are ones you create and maintain;
if you do not maintain a routing map, mark every route provisional.

## Fire threshold

Fires when an item's domain or task is not already obvious, when
multiple items arrive in a batch, or when the source buries the actual
ask inside other content (a forwarded chain, a rambling note, a message
with no clear next step). Does not fire when domain and task are
explicit and singular, for example a task already addressed to a named
project with one clear action. In that case state the route in one line
and move on.

## Dispositions

Every item gets one of four dispositions before any routing:

- Route: carries a decision or action. Gets the single-item contract.
- Park: reference or FYI, no decision now, plausibly useful later. One
  line in PARKED.md: date, what it is, why it might matter. Do not
  force a project route onto it.
- Drop: nothing there. Say so in one line.
- Review: real decision or action, but no destination in the map fits.
  Do not force the nearest route. Name the item, state why no
  destination covers it, and recommend either a manual route the user
  assigns or a map amendment. Gets the single-item contract with the
  route line reading Review, pending the user.

## Routing map

Read destinations and boundary notes from `routing-map.md` at execution
time. The map is authoritative on what destinations exist; this skill
body does not enumerate them.

## Boundary tests

The first-pass classifier is the audience test, not the topic test.
When one subject shows up across several of the user's domains (for
example, the same subject appearing in paid work, a side project, and
a personal matter), topic alone misroutes items.

Classify by who receives the deliverable. Illustrative domains; use the
ones defined in your routing map:

- Work: the deliverable ships to the user's employer, team, or
  colleagues, even when the subject overlaps another domain.
- Volunteer or community: the audience is an organization the user
  volunteers with, and no work deliverable is attached.
- Business: the audience is a paying or prospective client, or the
  item is business development toward one.
- Personal Life: the user or their family is the beneficiary.

If an item spans two domains, name both and recommend the primary by
whichever decision has the nearer deadline or higher cost of delay. Do
not split one item into two routes unless the user asks.

## Output contract, single item

- Disposition: Route, Park, Drop, or Review
- Domain: the destination domain per the map, or none if Review
- What's actually being asked: one to two sentences. Most items arrive
  as someone else's unresolved ambiguity; state the real ask, not the
  sender's framing of it
- Decision set: the actual options, including doing nothing, one line
  each
- Route to: destination (the matching skill or project)
- Confidence and flip evidence, per the Verdict Rule
- Handoff packet: a compact block written to be pasted into the
  destination project. Contains domain, restated ask, decision set,
  deadline if any, a one-line source pointer, and the carry list. The
  packet exists so the destination never re-reads the raw chain; if the
  packet is not self-sufficient, the triage is not done.

## Output contract, batch

Process each item against the single-item contract, then close with one
table: item, disposition, domain, one-line ask, route, carry. Per Brief
Economy, give the full contract inline only for items carrying a real
decision; compress Park, Drop, and low-stakes routes to the table.
Deliver handoff packets grouped by destination so each project gets one
paste.

## Source carry

The packet replaces the source material. It does not replace source
artifacts the destination will have to work from directly.

Every routed item names its source pointer as a durable location, not a
device or a session. If the source exists only as an ad hoc capture
(phone screenshot, quick PDF, photo of a whiteboard), the pointer is not
durable and the item carries a filing instruction naming where the
source must land before the packet is pasted.

Each routed item closes with a carry list: the artifacts that must move
to the destination with the packet, or the word None. An artifact
carries when the destination's work requires reading it, not summarizing
it. Attachments referenced but not read during triage always carry, and
are marked unread.

The carry list is part of the contract. A packet with no carry line is
incomplete, the same as one with no verdict.

## Boundaries

- Does not draft the reply, agenda, or resolution. That happens in the
  destination project.
- Does not apply the full contract to a routine single-domain item. One
  line and move on.
- Does not invent an ask the source material does not support. If the
  real request cannot be determined, say so and name what is missing.

## Verification

Not applicable. Outputs are internal routing decisions, not deliverables
shipped to an external audience. If you maintain a SKILLS-RECORD.md
(created from `templates/SKILLS-RECORD.template.md`), each real run gets
a one-line entry there per the Promotion Gate.
