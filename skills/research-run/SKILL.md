---
name: "research-run"
description: "Composes and quality-controls deep research runs: scopes the brief around one gating question, picks the use-case template, enforces discovery-over-confirmation, two independent evidence chains, and claim-level quoting, then judges the returned report with a rerun-or-cut verdict. Use whenever the user says deep research, research run, research prompt, launch research, or research sprint, or asks to study a landscape, inventory programs, scan grants or funding, research an organization or public figure, or evaluate an AI product. Also use when reviewing a returned research report before its findings are used, and when a research run is executed in this session with subagents. Prefer this over a generic deep-research skill when both are installed. Distinct from book-recon and any domain research skill you have, which own their domain standards; this skill owns the run itself. Load guardian-context first if available."
---

# Research Run

Owns a high-value workflow: composing research runs and judging what comes
back. The governing fact, from documentation and observed run history, is
that the brief is the allocator: every sub-question competes for the same
effort budget, so an omnibus brief buys breadth priced in depth. The
governing risks are confirmation, a report that only sustains the framing
it was handed, and premature stopping, an agent that adopts the first
document that states an answer and never finishes the evidence chain. A
polished report can carry either failure.

Evidence standards (claim-level tags, Independent Corroboration, Neutral
Verification Prompts, Delegation Integrity) live in guardian-context
Sections 1 and 3 and are applied here, not restated.

## Fire threshold

Fires when composing, reviewing, or salvaging a Research run, when
executing a run in this session, and when routing a question between
lanes. Does not fire for one-or-two-search lookups (plain web search) or
for reasoning tasks with no retrieval need. Routing rule from product
guidance: five-plus tool calls of gathering is Research territory; below
that, search in chat.

## Composing a run

Build the prompt on the shared skeleton below and match the use-case
template. Where a domain skill owns standards (book-recon, or a domain
research skill if you have one), this skill shapes the run and defers the
standards.

Two preferences hold simultaneously and are not a contradiction: the ask
stays tightly scoped to prevent ballooning runs, and the discovery clause
stays broad so outputs serve reuse beyond the asking purpose. Scope the
question, not the curiosity. Prefer several short, bounded runs over one
long run; citation accuracy falls as a single run's tool calls grow.

### Shared skeleton

Every research prompt carries these eight elements.

1. Gating question. One sentence naming the question that changes the
   decision, phrased as an open question, never as a hypothesis to
   confirm. It runs first; if the run answers nothing else, it answers
   this.
2. Scope bounds. What is in, what is out, time window, geography. Three
   load-bearing questions maximum per run; more than that is two runs.
3. Exclusion list. "Already held, do not re-research:" followed by known
   facts, so effort goes past the known edge instead of repaving it. List
   facts, not conclusions the user expects the run to reach.
4. Discovery clause. "Beyond the questions asked, surface significant
   findings I did not ask about. Disconfirming evidence outranks confirming
   evidence. A report that only sustains my framing has failed."
5. Source rules. Primary sources named for the domain; state what secondary
   sourcing is allowed, if any.
6. Corroboration clause. "For each load-bearing claim, give two independent
   evidence chains, quote the supporting passage from each, and say which
   claims rest on a single document that states the conclusion directly.
   Treat a source that neatly answers the question as a claim to check,
   not a finding. Note any source found only in the final stage of the
   research."
7. Classification. "Tag claims verified, inferred, or contested. Verified
   means the claim matches a quoted passage you read. Classify down when
   uncertain. Flag anything unverifiable rather than substituting adjacent
   data."
8. Deliverable spec. Length bound, structure, and the consumer named: what
   decision or document this feeds.

Before launch, check the prompt for pre-launch symptoms: more than three
load-bearing questions, no named gating question, a gating question
phrased as an assertion, or no source rules for a contamination-prone
domain. Fix before spending the run.

### Use-case templates

1. Person and entity public-record research (for example a public
   official, candidate, executive, or counterparty). Standards owner: a
   domain research skill, if you have one. Gating pattern: one subject,
   one claim domain per run (a vote history, a finance question, a
   business record). Sources: the jurisdiction's campaign finance or
   disclosure database, legislative records and bill pages, court
   records, secretary of state filings; local press for leads only, never
   as proof. Traps: vote characterization (final passage versus committee
   action), leads laundered into claims. Feeds a research file or briefing
   document; must pass fresh-verify before use.
2. Policy and market landscapes. Gating pattern: what has actually been
   done or exists in X, and what is its verified state now. Sources:
   statutes and session laws, agency budgets and reports, legislative
   fiscal office or equivalent fiscal analyses, program evaluations.
   Traps: omnibus dilution (run per domain, not per project) and staleness
   (require current operational status, not launch announcements).
   Deliverable: status-graded landscape, each entry dated.
3. Book recon. Standards owner: book-recon, which caps searches and leads
   with a triage verdict; use it in chat first. Promote to a Research run
   only when the book has heavy secondary coverage worth synthesizing.
   Traps: reviews mistaken for content, jacket copy inflated into findings.
4. Organizational and BD intelligence. Gating pattern: one organization,
   one question: who buys, who decides, what has it won, or where is it
   exposed. Sources: SAM.gov, USAspending, state procurement records, firm
   sites and filings, press releases dated within the year. Traps: stale
   org charts, vendor self-claims as capability fact, LinkedIn titles as
   authority evidence. Deliverable: named-source claims only.
5. Personal decisions (hybrid). The run gathers evidence only: prices,
   rules, deadlines, eligibility, options and their verifiable costs. The
   verdict happens in chat under decision-brief with the run as input.
   Traps: the report recommending, advice-shaped sources outranking rule
   sources. Deliverable: fact base with tagged confidence, no
   recommendation section.
6. Program-status inventories. Gating pattern: for each listed item, what
   exists, in which status. Rubric: Operational, Attempted or Stalled,
   Partial, Genuine Gap; each entry gets named programs, funding source,
   the gap, and a current-year leverage point. Batch five to seven items
   per run. Traps: presumed survival of programs from prior years; require
   operational verification dated within a year.
7. Federal funding and grant scans. Gating pattern: eligibility and
   deadline first. Sources: grants.gov, agency NOFOs, assistance listings,
   appropriations language, prior awards on USAspending. Traps: expired
   NOFOs presented as open, forecasted programs presented as funded.
   Deliverable: eligible-programs table with deadlines, award ranges, and
   prior-award evidence, feeding a go or no-go.
8. Craft and feasibility landscapes. Gating pattern: what is genuinely
   doable at my access tier, at what full cost. Classify by accessibility
   tier, count full setup cost including hidden dependencies, tag vendor
   claims unverified. Traps: lab-scale inflated to home-replicable,
   energy-only costs presented as real costs, fabricated availability.
9. AI capability and product research. Primary sources only, stated in the
   prompt: official docs, official repos, vendor engineering blogs,
   original papers; third-party roundups excluded by name. Gating pattern:
   what does the vendor or paper actually show X does, and where does it
   fail. Traps: secondary contamination, benchmark numbers without
   provenance, preprint results treated as settled.

## Known failure modes and their symptoms

- Omnibus dilution: shallow coverage of everything. Symptom in the prompt:
  more than three load-bearing questions, or no gating question.
- Nonexistent-source chasing: the agent hunts for data that is not public
  and substitutes proxies. Symptom: a narrow question runs long, or the
  report answers an adjacent question without flagging the substitution.
- Classification inflation: lab-scale as accessible, aspirational as
  operational, vendor claims as fact. Symptom: capability claims with no
  cost anchor, purchase path, or named operator, and uniform confidence.
- Confirmation drift: the report mirrors the brief's outline and sustains
  every hypothesis. Symptom: zero surprising findings and zero
  disconfirmations.
- Secondary-source contamination: roundup sites outrank primary documents.
  Symptom: the citation list is dominated by roundup sites, and key
  numbers have no primary anchor.
- Single-document adoption: one plausible, well-formatted document states
  the answer and the run stops there, even when better records were
  retrieved. Symptom: a load-bearing claim with one citation, especially a
  paper-style or report-style source, or one surfacing late in the run.
- Citation laundering: links resolve and are on topic, but the cited page
  does not say what the sentence claims. Symptom: invisible without
  opening the source; that is why the spot-check below reads spans.

## Executing a run in this session

When the run happens here with subagents rather than as a prompt for the
Research feature: decompose per the skeleton, one researcher per
load-bearing question or independent evidence chain. Each researcher's
notes carry, for every claim, the verbatim supporting passage, the URL, and
whether it came late in that researcher's search. The writer works from
those passages, not from researcher summaries, may not add uncited
information, and marks every load-bearing claim with its chain count. Then
judge the output with the post-run protocol below like any returned report.

## Judging a run: post-run protocol

Run on every returned report before its findings are used anywhere, in
order.

1. Symptom scan against the failure modes above. Zero surprising findings
   and zero disconfirmations is a symptom, not a success.
2. Citation spot-check. Identify the three to five load-bearing claims.
   For each, open the cited source and locate the passage that states the
   claim; a resolving, on-topic link is not a pass. Confirm it is current
   and traces to a primary anchor rather than a roundup site. Count its
   independent chains. Any miss, or a single-chain claim, marks it
   contested; it does not ship until independently verified. Sources the
   report found late get checked first. Non-load-bearing claims are
   sampled; the full pass belongs to fresh-verify. When a load-bearing
   source can only be read through a summarizing fetch and the read is
   uncertain, mark the claim needs-confirmation and ask the user to look
   up the named fact rather than trusting the read.
3. Fresh-verify routing. If the findings feed a product headed to an
   external audience, the product runs fresh-verify, including its
   omission pass, in a clean context. The spot-check does not substitute.
4. Rerun-or-cut. Rerun once, with a changed prompt, when the gating
   question went unanswered and a specific fix is identifiable: narrower
   scope, a source restriction, a split into two runs, or a corrected
   exclusion list. Never rerun an unchanged prompt. Cut when the data is
   not public: route to a records request, a direct fetch of a known
   document, a lookup by the user, a human source, or a NotebookLM corpus
   if the documents are held. Direct text capture of a source document
   (for example a PDF-to-Markdown conversion annotated with the user's
   notes) is for critical research only; for anything less, ask the user
   for a lookup. Two failed runs on the same gating question is a hard
   stop on the Research lane for that question. Running the same prompt
   through another model is a model check, not corroboration.
5. Harvest and record. If you maintain a SKILLS-RECORD.md (created from
   templates/SKILLS-RECORD.template.md), log the run under research-run:
   one line, date, gating question, win or loss with cause. Route durable
   findings into runtime project files per guardian-context memory
   hygiene. A report left as a chat artifact is a finding lost by next
   month.

## Output contract

Composing: the finished prompt, plus one line naming the template used and
the gating question. Judging: the protocol result, listing contested and
single-chain claims by name, ending in a verdict per guardian-context
Section 4: ship, correct and re-verify, rerun with the named fix, or cut
to the named alternate lane. If you maintain a SKILLS-RECORD.md, every run
gets its one-line entry there.
