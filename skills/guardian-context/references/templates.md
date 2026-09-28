# Guardian Output Templates

These templates define the concrete output formats for the user's most frequent
deliverable types. Use the exact structure specified here. Do not improvise
formatting.

---

## Knowledge Card (Universal Format)

Use this format for any atomic unit of project intelligence, research
finding, or meeting extract.

```yaml
---
title: "[Descriptive title of the finding or entity]"
id: "[YYYYMMDDHHmm timestamp]"
created: [YYYY-MM-DD]
updated: [YYYY-MM-DD]
sector: [infrastructure | advocacy | policy | consulting | nonprofit | research]
project: "[Project name]"
tags:
  - "[tag1]"
  - "[tag2]"
status: [verified | inferred | extrapolated | needs-verification]
confidence: [0.0-1.0]
sources:
  - "[Source description with date]"
related_cards:
  - "[card ID if applicable]"
---

## Summary
[2-3 sentences. The BLUF. What does this card tell you and why it matters.]

## Key Findings
[Numbered list. Each finding tagged as verified/inferred/extrapolated.]

## Implications
[What this means for the project. Who needs to act. What changes.]

## Open Questions
[What remains unverified. What needs follow-up.]
```

---

## Stakeholder Map Table

Use this format whenever mapping actors in any sector.

```markdown
| Actor | Stance | Incentive | Blocking Power | Key Relationships | Entry Path |
|-------|--------|-----------|----------------|-------------------|------------|
| [Name/Entity] | [Support/Oppose/Movable/Unknown] | [What they gain or lose] | [High/Medium/Low + mechanism] | [Who they influence or defer to] | [Warm intro / Cold outreach / Needs cover from X] |
```

Always follow the table with:

**Minimum Viable Coalition:** [Who must be on board for this to move]

**Sequencing:** [Who moves first, what permission structure each actor needs]

**Blocking Scenario:** [Who can kill this and through what mechanism]

---

## Intelligence Brief (Meeting/Deal)

Use this format for meeting-note-derived intelligence or deal status updates.

```markdown
## [Entity Name]: [Date] Intelligence Brief

**BLUF:** [One sentence. What changed, what matters, what to do next.]

### Current Status
[2-3 sentences on where this deal/project/relationship stands RIGHT NOW.]

### Stated Commitments
[Bulleted list. What specific actors said they would do. Named and dated.]

### Stated Blockers
[What they told you is in the way.]

### Implied Blockers
[What they didn't say but the conversation revealed: procurement delays,
internal politics, budget uncertainty, risk aversion.]

### Relationship Signals
[Trust indicators, enthusiasm level, who deferred to whom, who was
absent and why that matters.]

### Next Actions
| Action | Owner | Deadline | Dependencies |
|--------|-------|----------|--------------|
| [Specific action] | [Named person] | [Date or "ASAP"] | [What has to happen first] |
```

---

## Adversarial Audit Output

Use this format when stress-testing any deliverable.

```markdown
## Adversarial Audit: [Deliverable Name]

**Overall Assessment:** [One sentence. How vulnerable is this?]

### Dangerous Findings
[Findings that could kill the project or create serious exposure.
Each finding gets: the problem, why it's dangerous, specific remediation.]

### Exploitable Findings
[Findings an opponent could weaponize even if technically minor.
Each finding gets: the attack vector, likely attacker, recommended defense.]

### Residual Risk
[What cannot be fully mitigated and must be accepted or monitored.]

### Evidence Classification
| Claim | Classification | Source | Remediation Needed |
|-------|---------------|--------|-------------------|
| [Claim text] | [Verified/Inferred/Extrapolated] | [Source] | [Yes/No + what] |
```

---

## Research Deliverable (Standard Brief)

Use this for any research-to-deliverable output.

```markdown
## [Topic]: Research Brief

**BLUF:** [2-3 sentences. The bottom line finding and recommended action.]

### Context
[Brief background. What prompted this research. What question we're answering.]

### Key Findings
[Numbered. Each finding includes evidence classification.]

### Political Feasibility Assessment
[Who this affects. Who can block it. What the implementation path looks like
given the human system, not just the technical requirements.]

### Adversarial Considerations
[What a hostile actor would say about these findings. Where the argument
is weakest.]

### Recommended Actions
[Sequenced. Named by responsible party. Realistic timeline.]

### Open Questions / Verification Needed
[What we still don't know. What primary sources should be checked.]
```

---

## Project State Document

Use this as a running status tracker for active engagements. Updated
after each working session rather than created fresh.

```markdown
## [Project Name]: State Document
**Last Updated:** [Date]
**Sector:** [infrastructure | advocacy | policy | consulting | nonprofit | research]

### Current Phase
[One sentence. Where are we in the engagement.]

### Key Actors & Postures
[Brief stakeholder summary: who matters right now and where they stand.]

### Active Workstreams
[What's in progress. What's waiting on what.]

### Decisions Made
[Logged with date and rationale.]

### Decisions Pending
[What needs to be decided, by whom, by when.]

### Blockers
[What's actually stopping progress right now.]

### Next Session Priorities
[What to work on next time we pick this up.]
```
