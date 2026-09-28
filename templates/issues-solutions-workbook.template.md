# Issues and Solutions Synthesis Workbook

Status: DESIGNED. The two-tab fixed-column schema was instantiated once in a policy research effort. This generalized form has not been used.

## What it is

A two-tab workbook that turns a pile of research, notes, and stakeholder input into two linked inventories: the issues a jurisdiction faces, and the candidate solutions for them. The Solutions tab forces the same questions on every recommendation: does our jurisdiction already do this, who else does it, what return is documented, who would own it, and when it could happen. Fixed columns keep every row comparable, and gaps show up as blank cells instead of disappearing into prose.

## When to use it

- Synthesizing a body of research into a policy platform, issue plan, or advisory recommendation set.
- Checking whether a proposed solution already exists locally before recommending it.
- Building the evidence base that an executive brief (templates/executive-brief.template.md) will draw from.

## How to run it

1. Build the Issues Inventory first. One issue per row, stated as a problem, not a solution.
2. Build the Solutions and Recommendations tab. One solution per row, linked to the issue or issues it addresses.
3. Fill the five fixed columns on every solution row. Leave a cell blank or mark it Unknown rather than guessing; a blank is a research task, not a failure.
4. Documented ROI takes only a figure that a source actually documents, with the source named. Do not estimate or extrapolate a return to fill the cell.
5. Tier every figure and claim against your ground truth reference (templates/ground-truth-reference.template.md) before the workbook feeds a deliverable.

Column note: the source schema named the five fixed columns (does our jurisdiction do this, peer jurisdictions, documented ROI, responsible agency, timeline). The ID, statement, source, and link columns are structural fields added so the two tabs can be joined. Placing the five fixed columns on the Solutions tab is this template's reading of the schema.

## Output

One workbook (spreadsheet or Markdown) with two tabs. Every solution row traces to at least one issue row, and every filled cell traces to a source.

## Template

### Tab 1: Issues Inventory

Column definitions:

| Column | Definition |
|---|---|
| Issue ID | Short unique ID (I-01, I-02, ...). |
| Issue statement | The problem in one sentence, stated as a condition, not a fix. |
| Evidence | The data point or finding that shows the problem exists, with its figure if one exists. |
| Source | Where the evidence comes from (document, dataset, interview notes), specific enough to find again. |

Blank tab:

| Issue ID | Issue statement | Evidence | Source |
|---|---|---|---|
| I-01 | | | |

### Tab 2: Solutions and Recommendations

Column definitions:

| Column | Definition |
|---|---|
| Solution ID | Short unique ID (S-01, S-02, ...). |
| Addresses issue(s) | Issue IDs from Tab 1 this solution targets. |
| Recommendation | The action in one sentence, starting with a verb. |
| Does our jurisdiction do this? | Yes, Partly, No, or Unknown, with a one-line note on what exists now. |
| Peer jurisdictions | Other jurisdictions that do this, named. Blank if none found. |
| Documented ROI | The return a source documents (figure and source). Blank if none is documented. Never an estimate. |
| Responsible agency | The body that would own implementation. |
| Timeline | When it could take effect and what it waits on. |
| Source | Sources for this row not already cited in the cells above. |

Blank tab:

| Solution ID | Addresses issue(s) | Recommendation | Does our jurisdiction do this? | Peer jurisdictions | Documented ROI | Responsible agency | Timeline | Source |
|---|---|---|---|---|---|---|---|---|
| S-01 | | | | | | | | |
