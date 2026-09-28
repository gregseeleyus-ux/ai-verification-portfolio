# Verification Evidence Register

Status: DESIGNED. Blank form; generalized from a register structure used in practice.

## What it is

A runtime file that holds the claim-level evidence behind your standards and skills. When a rule in a skill rests on outside research (a study, a benchmark, a report), the finding goes here as one dated entry with its verification status, its number of independent evidence chains, and the quoted passages that support it. The skill states the rule; the register holds the proof, so evidence can be superseded without editing the skill.

## When to use it

- Adding or changing a rule in guardian-context or another skill because of research findings.
- Judging a research briefing before any of its findings change how you work.
- Logging that a finding you relied on was retracted, weakened, or could not be checked.

## How to run it

1. Copy the template block below to a file named VERIFICATION-EVIDENCE.md, kept outside the skill folders.
2. Judge the source briefing claim by claim (the research-run post-run protocol, if you use it). Open each cited source; a source cited but not opened is not a checked chain.
3. Write one finding per entry. Quote the passage that supports each figure or claim.
4. Count chains only across independent sources. Say how many were checked.
5. When newer evidence arrives, supersede the entry here. A retraction gets its own entry naming what it removes.
6. Log what could not be checked as a needs-verification entry instead of dropping it.

## Output

One register file. Entries are numbered in order and never silently edited; corrections are new entries or marked superseded.

## Template

```markdown
# VERIFICATION-EVIDENCE

Runtime file. Claim-level record of the evidence behind <the standards
or skill versions this register supports>. One finding per entry,
dated, with verification status and chain count. Source: <the briefing
or research run>, judged with <the protocol used> on <YYYY-MM-DD>.
Supersede entries here when newer evidence arrives rather than editing
the skills.

Status values: verified; verified (retraction); inferred (single source
or confounded); needs-verification. Qualify a status when it holds for
part of the finding only (for example, verified for one figure but
single-chain for another).

Chains: independent evidence chains behind the finding. Count only
sources that were opened and read; note any that were cited but not
opened. Agreement between AI models is not a chain.

## Entries

**E1. <The finding, stated in one sentence.>**
<YYYY-MM-DD>. Status: <status>. Chains: <number> <(checked / cited but
not opened, if they differ)>.
- Chain 1: <source title, venue, and whether peer reviewed or
  preprint>. Quoted: "<exact passage>"; "<exact passage>"
- Chain 2: <source>. Quoted: "<exact passage>"
- Supports: <the skill rule or standard this finding backs>.
- Limits: <domain, sample, or confound that bounds the finding; any
  wording in the skill to soften at the next refactor>.

**E2. <Source or finding> is retracted.**
<YYYY-MM-DD>. Status: verified (retraction). Chains: <number> <(the
authors' own correction, if so)>.
- What was claimed: <figures or claim, and where they came from>.
- Correction: Quoted: "<the retraction or correction text>"
- Effect: <which entry or rule loses this as evidence, and whether that
  entry still holds on its remaining chains>.

**E3. Unverifiable in this pass.**
<YYYY-MM-DD>. Status: needs-verification.
- <Source>: <why it could not be checked>. <Figure or claim left
  unconfirmed>.
- <Findings left unchecked, and why>.
```
