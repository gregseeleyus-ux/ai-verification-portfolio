# SKILLS-RECORD

Runtime file for your skill suite. It holds the promotion-gate evidence
described in guardian-context Section 1: one line per real test (date,
task, win or loss, one-sentence cause if a loss). A win means the skill
produced the intended result without manual rescue. Skill files never
carry this state; skill-forge maintains it.

Set maturity conservatively. A skill with no logged tests is classified
no higher than its evidence supports, whatever its build completeness.

Copy this file, rename it SKILLS-RECORD.md, and keep it outside the skill
folders.

---

## <skill-name>

- Version: <version> (saved <date>)
- Deployed surfaces: <where the skill is installed>
- Maturity: <BUILT | PROTOTYPE | DESIGNED | CONCEPT>
- <date> refactor: <what changed>. Reason: <the loss or evidence that
  prompted it>.
- Refactor flags (open): <issue seen in use, not yet fixed>
- First test: <the next real task that will exercise this skill>

Tests:
- <date>, <task in one line>, <win | loss>. <cause, if a loss>.
