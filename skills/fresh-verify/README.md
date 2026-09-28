# fresh-verify

Status: PROTOTYPE

An independent verifier for finished deliverables. Checks every claim, quote, figure, citation, and attribution verb against the sources, then runs a separate two-stage omission pass: one context lists what the sources require, another checks the draft against that list. Returns Pass, Pass pending confirmation, or Fail.

**Use it:** Before anything with sourced claims goes to an outside audience. Works best in a clean conversation holding only the draft and its sources.

**Depends on:** guardian-context

**Note:** Measured against a labelled test set you build yourself; see templates/VERIFY-TESTSET.template.md.

**Install:** see docs/INSTALL.md. The skill itself is SKILL.md in this folder.
