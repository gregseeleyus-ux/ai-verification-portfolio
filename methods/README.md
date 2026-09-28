# Methods

Working methods behind the skills. Most are prompt patterns and document structures, not software. Each carries a status label on the same evidence rule as the skills.

## Verification

**Multi-AI Verification Protocol (PROTOTYPE).** Cross-checking one model's output with another: verification sequences, synthesis steps, and alignment checks. Important limit: models from different vendors share many of the same errors, so agreement across models is a weak signal, not confirmation. A second model is useful for catching one model's slips and for arguing the opposite case; confirmation comes from independent sources plus one check no model controls (a primary record, a person, a calculation you run yourself).

**Five-Phase Cross-AI Workflow (PROTOTYPE).** The mature form of the protocol above: assign each phase to a model with a defined role (creative design, hostile audit, integration, synthesis, final QC) and track a confidence level for each claim through the phases. Run end to end once on a policy analysis. Phase agreement is still not corroboration.

## Structured thinking

**Virtual Project Team (PROTOTYPE).** Full method, role cards, and a worked example in vpt/. Multi-perspective reasoning with defined roles: Strategist, Analyst, Navigator, Ethicist, Comms Architect, Systems Architect. Ask the model to work a problem through each role, then reconcile. Define each role by title, functional background, and interests only; do not give roles personal names or cultural or ethnic backgrounds. Any role modeled on a real person is built only from public material, generalized and anonymized, and framed as stakeholder alignment, not a simulation of that person.

**VProjT execution templates (PROTOTYPE).** Kickoff structures and deliverable models for running a project through the Virtual Project Team. Used as patterns; not packaged.

**The recurring design spine (DESIGNED).** Most of the systems behind these skills follow one shape: input, then scoring, then storage, then activation, then interface. With a retrieval layer (knowledge cards) and a verification layer, it is a reusable way to design new tools.

## Knowledge and reporting

**Knowledge Cards (PROTOTYPE).** Method cards in cards/; blank findings-card format in templates/knowledge-card-template.md. A modular format for storing operational rules and standards: a short Markdown file with YAML frontmatter and a body stating one rule, method, or finding. Cards recur across domains as a retrieval layer: small enough to load, cite, and version one at a time.

**Multi-Layer Report Generation (BUILT).** A repeatable report architecture in three layers: executive summary, then analysis, then evidence.

**Project Status Brief (PROTOTYPE).** A fixed five-part recap for re-entering a project after time away:
1. Purpose, in one sentence.
2. Status: active, paused, or complete.
3. Work completed.
4. Active threads and next steps.
5. Overlap with other projects.

## Sessions

**Iterative Session Prompts (DESIGNED).** Five prompts for the stages of a long working session: opening, mid-session checkpoint, critique loop, controlled ideation pivot, and session close. See iterative-session-prompts.md.

## Build patterns

**docx Generation Pattern Library (PROTOTYPE).** Reusable Node.js patterns for generating Word documents with the docx library: table of contents, tables, cover pages, callout boxes, page breaks. Reused across several deliverables; not yet packaged, so no code ships in v1.

## Methods with their own files

Each has its own file in this folder: case-study-crosswalk.md, collaborative-war-gaming.md, snapshot-benchmark-tracking.md, benchmark-forecast-sheet.md, self-coaching-toolkit.md, ai-project-setup.md, operating-instrumentation-system.md, stakeholder-type-feedback.md. New templates in templates/: executive brief, ground truth reference, issues and solutions workbook, verification evidence register. See CATALOG.md for one-line summaries.
