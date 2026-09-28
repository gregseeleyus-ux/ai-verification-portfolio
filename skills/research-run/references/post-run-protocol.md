# Deep Research Post-Run Protocol

Run this on every returned report before its findings are used anywhere.

## Step 1: Symptom scan

Check the report against the five failure modes in references/mechanics-brief.md:
omnibus dilution, nonexistent-source substitution, classification inflation,
confirmation drift, secondary-source contamination. The drift check is
specific: if the report contains zero surprising findings and zero
disconfirmations, treat that as a symptom, not a success.

## Step 2: Citation spot-check

Identify the three to five load-bearing claims: the ones the consuming
decision or document actually rests on. For each, open the cited source and
confirm the claim is there, is current, and traces to a primary anchor
rather than a roundup site repeating it. Any miss marks the claim contested
and it does not ship until independently verified. Non-load-bearing claims
are sampled, not exhaustively checked; the full pass belongs to fresh-verify.

## Step 3: Fresh-verify routing

If the findings feed a product headed to an external audience (client
deliverable, published report, briefing or advocacy material), the product
runs the fresh-verify pass in a clean context. The spot-check above does
not substitute for it.

## Step 4: Rerun-or-cut rule

Rerun once, with a changed prompt, when the gating question went unanswered
and a specific prompt fix is identifiable: narrower scope, a source
restriction, a split into two runs, or a corrected exclusion list. Never
rerun an unchanged prompt; same input, same failure.

Cut when the evidence says the data is not public: the run substituted
proxies, or the sources that would hold the answer are internal, sealed, or
paywalled beyond reach. Cutting routes the question to a different lane:
records request, direct fetch of a known document, a human source, or a
NotebookLM corpus if the documents are already held.

Two failed runs on the same gating question is a hard stop on the Research
lane for that question.

## Step 5: Harvest and record

If you maintain a SKILLS-RECORD.md (created from
templates/SKILLS-RECORD.template.md), log the run there under research-run:
one line, date, gating question, win or loss with cause. Route durable
findings into the relevant runtime project files per memory hygiene: one
finding per entry, dated, tagged, superseding stale entries. A report left
as a chat artifact is a finding lost by next month.
