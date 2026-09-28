# Deep Research Mechanics Brief

Version 1.0. Claims tagged Verified (Anthropic documentation or directly observed runs), Inferred (consistent evidence, not confirmed), or Contested (sources conflict or only secondary).

## How the tool spends its effort

1. The feature runs agentically: it decomposes the brief, conducts multiple searches that build on each other, decides what to investigate next, and explores angles of the question automatically. Verified (support.claude.com, claude.com/blog/research).

2. It searches connected internal context (Gmail, Calendar, Drive) alongside the web when integrations are on, and requires web search enabled. Verified (support docs).

3. Anthropic positions the tool by call volume: web search for one-to-two call questions, Research for gathering needing five or more tool calls; product guidance routes twenty-plus call tasks to Research. Verified (support docs).

4. The underlying architecture Anthropic describes is orchestrator-worker: a lead agent plans, spawns parallel subagents as filters, and a citation agent attributes claims. Effort scales with the brief: simple fact-finding one agent and three to ten calls, comparisons two to four subagents, complex questions ten-plus. Token spend explains most output-quality variance; multi-agent runs cost roughly fifteen times chat. Verified as Anthropic-published for their research system; the mapping to the consumer feature's exact behavior is Inferred.

5. Practical implication of 3 and 4 combined: the brief is the allocator. Each distinct sub-question in a prompt becomes a workstream competing for the same budget, so an omnibus brief buys breadth priced in depth. Inferred from documentation plus observed runs.

6. Run duration in practice: minutes typical, tens of minutes on complex briefs; reports run long-form with citations. Documentation says minutes; longer figures are third-party. Contested on specifics.

## Top five failure modes, each with its early symptom

1. Omnibus dilution. Many-section briefs return shallow coverage of everything instead of depth on what matters. Observed directly: a critique of a multi-question run forced a split into three single-question runs with the gating question first. Symptom, visible in the prompt before launch: more than three load-bearing questions, or no single question named as the one that changes the decision.

2. Nonexistent-source chasing. The agent scours for data that is not public (internal actuarials, unpublished splits) and stalls or substitutes proxies. Verified as a documented failure of Anthropic's research agents; observed in the same multi-question run's unfindable targets. Symptom: a narrow question runs long, or the report answers an adjacent question without flagging the substitution.

3. Classification inflation. Lab-scale presented as accessible, aspirational as operational, vendor claims as fact; worst observed case fabricated consumer availability of a research material. Observed across a series of materials-feasibility runs on more than one model. Symptom: capability or availability claims with no cost anchor, purchase path, or named operator, and uniform confidence across the report.

4. Confirmation drift. The report mirrors the brief's outline and sustains every hypothesis, because the prompt supplied the frame the agents filled. Observed: reports that strayed from the real goals yet confirmed the framing; the materials-feasibility series improved only after the prompt balanced known terrain against open discovery and required downward classification. Symptom: zero surprising findings and zero disconfirmations in the returned report.

5. Secondary-source contamination. Roundup sites, SEO posts, and forum summaries outrank primary documents, importing their errors. Observed as a direct A/B: a report with unrestricted sourcing (multiple unverifiable claims) against a report with a primary-sources-only clause (converged cleanly with official docs). Symptom: the citation list is dominated by roundup sites, and key numbers have no primary anchor.

## Standing implication

The levers that worked in observed runs are all prompt-side: one gating question run first and alone, source restrictions stated up front, classify-down and disconfirmation clauses, exclusion of already-held knowledge, and a bounded deliverable spec. Where documentation and run history conflicted, run history was preferred and marked.
