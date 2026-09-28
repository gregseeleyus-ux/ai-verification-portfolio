---
name: "adversarial-pass"
description: "Runs an adversarial stress-test protocol on any draft deliverable: proposals, briefs, strategies, playbooks, policy analyses, advocacy plans, research reports, or consulting recommendations. Use this skill whenever the user asks to \"red team,\" \"stress test,\" \"scrutinize,\" \"attack,\" \"find what breaks,\" run a \"pre-mortem,\" or any variation of adversarial review on a document or strategy. Also use when the user brings output from another AI system (ChatGPT, Gemini) and asks for critical review. This skill depends on guardian-context for evidence standards; load guardian-context first if not already loaded."
---

# Adversarial Pass Protocol

This skill implements an established adversarial review process: the
same logic applied manually across policy analysis, advocacy strategy,
infrastructure proposals, and consulting deliverables. It codifies
criteria that would otherwise need to be re-explained each session.

**Before using this skill:** Ensure the guardian-context skill standards
are loaded (evidence standard, political feasibility filter, voice rules).

**Fresh-context discipline:** An adversarial pass run in the same
conversation that drafted the deliverable is a weaker pass; the reviewer
inherits the drafter's assumptions. For any deliverable whose failure
cost is political exposure, legal liability, or client-facing credibility,
run this protocol in a clean conversation containing only the deliverable
and its cited sources, with no drafting history. If the pass must run
in-context, say so in the Audit Parameters and treat the result as a
first pass, not a clearance. Apply the guardian-context Neutral
Verification Prompts rule: present the deliverable as a third party's
submission, and keep the author's preferred conclusion out of the
request.

**Scale to stakes:** The full six-step protocol is for deliverables with
real failure cost. A low-stakes internal draft gets a targeted pass:
evidence audit plus the top two attack vectors, stated as such. Do not
run the full protocol on everything; a pass that fires at full depth on
every document trains the user to skip it.

---

## Step 1: Identify the Deliverable and Its Stakes

Before attacking, understand what you're attacking and why it matters:

- **What is this?** (proposal, brief, strategy, playbook, analysis, letter)
- **Who is the intended audience?** (elected official, organization or
  campaign leadership, client, legislative committee, federal agency,
  general public)
- **What decision does this support?** (procurement, vote, funding,
  partnership, policy position)
- **What's the cost of failure?** (political exposure, financial loss,
  reputational damage, missed opportunity, legal liability)

If the stakes are unclear, ask the user. The depth and angle of the
adversarial review should match the stakes. An internal field playbook
gets a different intensity than a fiscal analysis going to a legislative
finance committee.

---

## Step 2: Run the Evidence Audit

Go through every factual claim in the deliverable and classify it:

| Classification | Definition | Action Required |
|---|---|---|
| **Verified** | The specific claim matches a quoted passage in a primary source provided in the material (guardian-context claim-level definition); a relevant citation alone does not qualify | None; mark as solid |
| **Inferred** | Logical conclusion from verified data, but not directly stated in source | Flag and state the reasoning chain |
| **Extrapolated** | Plausible but not verified; could be wrong | Flag prominently; recommend verification before delivery |
| **Unsourced** | Claim with no apparent evidentiary basis | Flag as critical vulnerability |

Present this as a table. Do not bury evidence classification in prose.

**Specific things to catch:**
- Numbers presented without methodology or source
- "Studies show" or "research indicates" without specific citation
- Claims about opponent or competitor behavior, voting records, or
  positions that haven't been verified against primary sources
  (campaign finance filings, legislative records, public statements)
- Load-bearing claims resting on a single document that states the
  conclusion directly, or supported only by agreement between AI
  systems; per guardian-context Independent Corroboration, neither
  counts as confirmation
- Projections presented as facts
- Averages or rolled-up totals that mask important variance
- Verdict avoidance: a decision-facing deliverable that ends in a
  balanced summary of options with no recommendation fails the
  guardian-context Verdict Rule. Classify this as Exploitable at
  minimum; a skeptical reader treats a verdict-free brief as the
  author hedging against accountability.

---

## Step 3: Run the Political Feasibility Stress Test

Apply the guardian-context Political Feasibility Filter to every
recommendation in the deliverable:

**For each recommendation, answer:**
1. Who has to say yes for this to happen?
2. What's their incentive to say yes? To say no?
3. Who can block this unilaterally, and would they?
4. Does the recommendation provide "political insurance" for the
   decision-maker, or does it expose them?
5. Is the sequencing realistic? Does it assume actors will move
   in an order that their incentives don't support?
6. What happens if the first step fails: is there a fallback,
   or does the entire strategy collapse?

**Flag any recommendation that:**
- Assumes cooperation from a known blocker without explaining
  what changed their incentive
- Requires perfect sequencing with no contingency
- Exposes the decision-maker to blame without transferring risk
- Depends on a timeline that assumes best-case processing at
  every step

---

## Step 4: Run the Hostile Opponent Simulation

Assume the most capable, motivated opponent is reading this
deliverable. What do they attack?

**For campaign or advocacy deliverables:**
- What opposition research lines does this create or leave open?
- Which claims would an opponent fact-check first?
- What does the 30-second attack ad version of this look like?
- Where is the "gift quote" that gets taken out of context?

**For policy deliverables:**
- What's the constitutional or legal challenge pathway?
- Which lobbying group would oppose this and through what mechanism?
- What does the legislative fiscal note objection look like?
- Where does the math not work under less favorable assumptions?

**For infrastructure/consulting deliverables:**
- What does the competing vendor say to undermine this?
- Where does a skeptical procurement officer find reason to delay?
- What happens to this proposal if the political environment changes
  (new administration, budget crisis, scandal)?
- Where is the "too good to be true" claim that triggers institutional
  skepticism?

**For cross-AI review (when the user brings output from another system):**
- Where did the other system make unsupported logical leaps?
- What did it present with false confidence?
- Where did it fail to consider the political/institutional dimension?
- What did it get right that should be preserved?
- Where this output and another system's output agree, treat the
  agreement as a weak prior, not corroboration; models share errors.
  Check load-bearing points against the sources instead.

Omissions: Step 4 names the counter-arguments and caveats an opponent
would say are missing. A systematic check of whether the deliverable
carries everything its sources require belongs to fresh-verify's
omission pass; recommend it for any deliverable with load-bearing
claims.

---

## Step 5: Classify All Findings

Every finding from Steps 2-4 must be classified using the four-tier
severity scale:

**Dangerous:** Could kill the project, create serious legal/political
exposure, or fundamentally undermine credibility. Requires immediate
remediation before the deliverable ships.

**Exploitable:** An opponent or skeptic could weaponize this even if
it's technically minor. Worth fixing but won't sink the project alone.

**Boring:** Real but unlikely to move any decision-maker. Document
for completeness but don't let it distract from dangerous findings.

**Irrelevant:** Technically true but strategically meaningless. Note
only if the user specifically asked for comprehensive review.

Focus the output on Dangerous and Exploitable. Do not pad the audit
with Boring and Irrelevant findings to appear thorough. The reviewer's
time is better spent on findings that actually matter.

---

## Step 6: Produce the Audit Output

Use this Adversarial Audit template:

```markdown
## Adversarial Audit: [Deliverable Name]

**Overall Assessment:** [One sentence. How vulnerable is this deliverable?
Scale: Battle-Ready / Needs Work / Significant Exposure / Not Ready to Ship.
Name the single highest-priority fix and what evidence or change would
move the assessment up one level.]

**Audit Parameters:** [What angle of attack was used. What stakes were
assumed. What audience was considered.]

### Dangerous Findings
[Each finding gets:]
1. **The Problem:** [What's wrong, specifically]
2. **Why It's Dangerous:** [What happens if this isn't fixed]
3. **Remediation:** [Specific fix, not vague advice]

### Exploitable Findings
[Each finding gets:]
1. **The Attack Vector:** [How an opponent uses this]
2. **Likely Attacker:** [Who would exploit this and why]
3. **Recommended Defense:** [How to neutralize or preempt]

### Evidence Classification Table
| Claim | Classification | Source | Fix Needed |
|-------|---------------|--------|------------|
| [Claim] | [Verified/Inferred/Extrapolated/Unsourced] | [Source or "None"] | [Yes/No + what] |

### Residual Risk
[What cannot be fully mitigated. What the user needs to accept, monitor,
or have a contingency plan for.]

### What Works
[Do not only attack. Identify what is solid, well-sourced, and
strategically sound. The user needs to know what to protect as well
as what to fix.]
```

---

## Quality Checks Before Delivering

- Every Dangerous finding has a specific remediation, not "consider
  revising this section"
- Evidence classification table covers ALL major claims, not just
  the problematic ones
- The "What Works" section is present and substantive: adversarial
  review that only attacks is less useful than review that also
  validates
- Findings are classified by severity, not listed in order encountered
- The overall assessment is honest: do not soften "Not Ready to Ship"
  to be polite
- Voice matches guardian-context Section 4 standards throughout
