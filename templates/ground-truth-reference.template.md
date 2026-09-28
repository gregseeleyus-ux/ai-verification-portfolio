# Verified Ground Truth Reference

Status: DESIGNED. The three-tier evidence classification was built once as a reference for one analysis workspace. This generalized form has not been used.

## What it is

A standing reference file that sorts the claims a body of work relies on into three tiers: Verified, Reported (verify before use), and Do not use. It sits beside a project so that every deliverable draws facts from one checked list instead of re-deriving them, and so that claims already found wrong stay visibly blocked instead of creeping back in. It applies the guardian-context evidence standard to a project's recurring facts.

## When to use it

- A project will produce several deliverables from the same set of figures and facts.
- Research from several sources, including AI research runs, needs a single sorted list before anything ships.
- A claim has been found wrong, retracted, or unsupported and must not reappear.

## How to run it

1. List each claim the project's deliverables rely on, one claim per entry, stated exactly as it would be used.
2. Assign a tier using the rules below. When unsure, assign the lower tier.
3. Deliverables draw facts from the Verified tier. A Reported claim is used only after it is verified and moved up, or with its unverified status stated in the deliverable.
4. When a claim fails a check, move it to Do not use with the reason. Do not delete it.
5. Date every tier change. Supersede an entry when newer evidence arrives; do not leave a corrected claim standing in its old tier.

## Tier rules

**Verified.** The specific claim was matched against a quoted passage in a primary source that was actually read, not merely cited. A load-bearing claim (one a decision or an external product rests on) also needs two independent evidence chains plus one check no model controls: a direct read of the primary document, a deterministic lookup or calculation, or a human source.

**Reported, verify before use.** The claim appears in a secondary source, an AI summary, or a single document, or its source was cited but not opened. It may be true. It is not yet usable as fact.

**Do not use.** The claim is contradicted by a primary source, retracted, unsupported after a real search, or outside what the source actually says. Keep the entry and its reason so the claim is recognized if it resurfaces.

Rules that apply across tiers:

- Agreement between AI models is not independent evidence and never raises a tier.
- Tier by corroboration, never by format or apparent authority. A polished report or official-looking page earns nothing on appearance.
- A single document that states the conclusion directly is a flag, not a confirmation.
- Tags attach to the claim, not the source. An on-topic source with a working link does not make the sentence citing it Verified.

## Output

One Markdown file per project, three sections in fixed order, each entry in the format below.

## Template

```markdown
# Ground Truth Reference: <project>

Last reviewed: <YYYY-MM-DD>
Rule: deliverables draw facts from Verified only. Reported entries are
used only after verification or with their status stated. Do not use
entries stay listed with their reason.

## Verified

**GT-001. <Claim, stated exactly as it will be used.>**
- Chain 1: <primary source>. Quoted: "<passage that states the claim>"
- Chain 2: <independent source, if load-bearing>. Quoted: "<passage>"
- Non-model check: <direct read, calculation, or human source>
- Checked: <YYYY-MM-DD>

## Reported, verify before use

**GT-002. <Claim.>**
- Where it appears: <source and why it is not yet enough>
- To verify: <the primary source or check that would settle it>
- Logged: <YYYY-MM-DD>

## Do not use

**GT-003. <Claim, as it has appeared.>**
- Reason: <contradicted by X / retracted / unsupported after search / beyond what the source says>
- Evidence: <source and quote that shows the problem>
- Use instead: <the Verified entry or wording to use, if any>
- Moved: <YYYY-MM-DD>
```
