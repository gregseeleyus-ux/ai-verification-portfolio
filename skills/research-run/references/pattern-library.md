# Deep Research Pattern Library

Contents: shared prompt skeleton; nine use-case templates (person and
entity public-record research; policy and market landscapes; book recon;
organizational and BD intelligence; personal decisions; program-status
inventories; federal funding and grant scans; craft and feasibility
landscapes; AI capability and product research).

## Shared skeleton

Every research prompt carries these seven elements. Tight scope and open
discovery are not in tension: the ask is narrow, the permission to surprise
is broad.

1. Gating question. One sentence naming the question that changes the
   decision. It runs first; if the run answers nothing else, it answers this.
2. Scope bounds. What is in, what is out, time window, geography. Three
   load-bearing questions maximum per run; more than that is two runs.
3. Exclusion list. "Already held, do not re-research:" followed by what is
   known, so effort goes past the known edge instead of repaving it.
4. Discovery clause. "Beyond the questions asked, surface significant
   findings I did not ask about. Disconfirming evidence outranks confirming
   evidence. A report that only sustains my framing has failed."
5. Source rules. Primary sources named for the domain; state what secondary
   sourcing is allowed, if any.
6. Classification. "Tag claims verified, inferred, or contested. Classify
   down when uncertain. Flag anything unverifiable rather than substituting
   adjacent data."
7. Deliverable spec. Length bound, structure, and the consumer named: what
   decision or document this feeds.

## 1. Person and entity public-record research

Covers a public official, candidate, executive, or counterparty.
Standards owner: a domain research skill, if you have one; this template
only shapes the run.
Gating pattern: one subject, one claim domain per run (a vote history, a
finance question, a business record), never the whole subject at once.
Sources: the jurisdiction's campaign finance or disclosure database,
legislative records and bill pages, court records, secretary of state
filings, contemporaneous local press for leads only, never as proof.
Traps: vote characterization (final passage versus committee action), leads
laundered into claims. Deliverable feeds a research file or briefing
document and must pass fresh-verify before use.

## 2. Policy and market landscapes

Gating pattern: what has actually been done or exists in X, and what is the
verified state of it now.
Sources: statutes and session laws, agency budgets and reports, legislative
fiscal office or equivalent fiscal analyses, program evaluations.
Traps: omnibus dilution (run per domain, not per project) and staleness
(require current operational status, not launch announcements).
Deliverable: status-graded landscape, each entry dated.

## 3. Book recon

Standards owner: book-recon skill, which caps searches and leads with a
triage verdict; use it in chat first. Promote to a Research run only when
the book has heavy secondary coverage worth synthesizing.
Traps: reviews mistaken for content, and jacket-copy claims inflated into
findings. Deliverable per book-recon format, verdict first.

## 4. Organizational and BD intelligence

Gating pattern: one organization, one question: who buys, who decides,
what has it won, or where is it exposed.
Sources: SAM.gov, USAspending, state procurement records, firm sites and
filings, press releases dated within the year.
Traps: stale org charts, vendor self-claims as capability fact, LinkedIn
titles as authority evidence. Deliverable: brief with named-source claims
only, feeds outreach or a bid decision.

## 5. Personal decisions (hybrid)

The run gathers evidence only: prices, rules, deadlines, eligibility,
options and their verifiable costs. The verdict is not delegated to the
report; it happens in chat under decision-brief logic with the run as input.
Gating pattern: what are the verifiable facts and real options bearing on X
by date Y. Traps: the report recommending, advice-shaped sources outranking
rule sources. Deliverable: fact base with tagged confidence, no
recommendation section.

## 6. Program-status inventories

Gating pattern: for each listed item, what exists, in which status.
Rubric: Operational, Attempted or Stalled, Partial, Genuine Gap; each entry
gets named programs, funding source, the gap, and a current-year leverage
point. Batch discipline: five to seven items per run; a twenty-domain
inventory is a series, not a prompt. Traps: presumed survival of programs
from prior years; require operational verification dated within a year.

## 7. Federal funding and grant scans

Gating pattern: eligibility and deadline first: can this applicant apply,
for what, by when.
Sources: grants.gov, agency NOFOs, assistance listings, appropriations
language, prior award records on USAspending.
Traps: expired NOFOs presented as open, forecasted programs presented as
funded. Deliverable: eligible-programs table with deadlines, award ranges,
and prior-award evidence, feeds a go or no-go.

## 8. Craft and feasibility landscapes

Gating pattern: what is genuinely doable at my access tier, at what full cost.
Rules proven in prior runs: classify by accessibility tier, count full setup
cost including hidden dependencies, use a controlled vocabulary for reuse
claims if you maintain one, tag vendor claims unverified.
Traps: lab-scale inflated to home-replicable, energy-only costs presented as
real costs, fabricated availability. Deliverable: tiered landscape,
classify down.

## 9. AI capability and product research

Rule proven in prior runs: primary sources only, stated in the prompt:
official docs, official repos, vendor engineering blogs; third-party
roundups excluded by name.
Gating pattern: what does the vendor officially say X does and where does it
fail. Traps: secondary contamination, benchmark numbers without provenance,
capability claims from screenshots. Deliverable: mechanics plus failure
modes, claims tagged, feeds skill or workflow design.
