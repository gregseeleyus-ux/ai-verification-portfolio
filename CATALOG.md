# Systems Catalog

This is the catalog of the author's AI systems built since 2024, many of them before Claude, in ChatGPT and other tools. Systems are grouped by domain, and each carries a status label (BUILT, PROTOTYPE, DESIGNED, CONCEPT) with the same meaning as in the root README; where the evidence is thin, the label is classified down, not up. Some systems are listed without files because they live as prompt patterns rather than packaged artifacts; those entries say "Not packaged yet."

## Skills (packaged for Claude)

### guardian-context (BUILT)

The shared standards every other skill in this repo loads first: evidence tiers and confidence tags, claim-level verification, a feasibility filter for decisions that depend on people, an adversarial pre-mortem, voice and formatting rules, and the standards for building new skills.

In this repo: skills/guardian-context/

### adversarial-pass (BUILT)

A structured red-team pass on a draft, including drafts produced by other AI models. It classifies findings as Dangerous, Exploitable, Boring, or Irrelevant, marks each claim as verified, inferred, extrapolated, or unsourced, and ends with an audit you can act on.

In this repo: skills/adversarial-pass/

### research-run (PROTOTYPE)

Composes and judges deep research runs: one gating question, a discovery clause so the run can disconfirm your framing, two independent evidence chains with quoted passages, and named failure modes. Each returned report gets a verdict of ship, correct, rerun, or cut; a pattern library and mechanics brief ship with it.

In this repo: skills/research-run/

### fresh-verify (PROTOTYPE)

A clean-context verification pass on a finished deliverable: it checks every claim, quote, figure, and attribution against the sources, then runs a separate omission pass in which one context lists what the sources require and another checks the draft against that list. It returns Pass, Pass pending confirmation, or Fail, and sends uncertain source reads back to you as named lookups.

In this repo: skills/fresh-verify/

### skill-forge (BUILT)

Designs, tests, refactors, and retires skills, and keeps the promotion-gate record. A skill moves up the four-tier scale only when logged real use shows it works.

In this repo: skills/skill-forge/

### decision-brief (DESIGNED)

Turns a real decision into a one-page brief: what is being decided and by when, the options priced (including doing nothing), and a mandatory verdict with confidence and the evidence that would change it.

In this repo: skills/decision-brief/

### book-recon (PROTOTYPE)

Reconstructs a book's useful content from public sources when you do not have the book. It opens with a read, skim, or skip verdict, then harvests the transferable frameworks, heuristics, data, and arguments.

In this repo: skills/book-recon/

### guardian-intake (DESIGNED)

Triage for raw, ambiguous input such as notes, emails, and forwarded chains: it classifies the item, restates the real ask, names the decisions inside it, and recommends where it should go, with a paste-ready handoff.

In this repo: skills/guardian-intake/

## Consulting and Analysis

### Decision Journal (BUILT)

A log of strategic choices that captures the rationale behind each one explicitly. The entry structure lives in how it is used rather than in a written form.

Not packaged yet.

### Collaborator Input Template (BUILT)

A structured way to gather feedback from collaborators, with a consistent set of questions and a defined route for where each answer goes.

Not packaged yet.

### Minimum Viable Company Roadmap (BUILT)

A framework for standing up a lean operation, developed for the author's own consulting practice.

Not packaged yet.

### Virtual Project Team (PROTOTYPE)

Multi-perspective reasoning with defined roles (Strategist, Analyst, Navigator, Ethicist, Comms Architect, Systems Architect): the model works a problem through each role, the roles argue, and you decide. Used as a prompting practice; role cards, a card template, and a worked example ship here.

In this repo: vpt/

### VProjT (PROTOTYPE)

A standardized execution environment for running a project through the Virtual Project Team: kickoff structures, templates, and deliverable models. Used as patterns; not packaged.

In this repo: methods/README.md (description only)

### ImpactMetrist and ClientArchitect Roles (DESIGNED)

Two additional consulting roles designed as extensions of the Virtual Project Team. The role designs exist; there is no logged use.

Not packaged yet.

### ResponseMatrix (CONCEPT)

A named consulting tool idea. Nothing has been created yet.

Not packaged yet.

### RFI Intent-Reconstruction Method (CONCEPT)

Reverse-engineers the unstated evaluation priorities in a solicitation or request for information, and traces the buyer's real constraint back to the statute or authority behind the program.

Not packaged yet.

### Case Study Crosswalk (DESIGNED)

Answers each expected objection with a four-link chain: the objection, a place where the model works anyway, the mechanism that made it work there, and the local translation. The mechanism carries the argument, not the outcome.

In this repo: methods/case-study-crosswalk.md

### Collaborative War-Gaming (CONCEPT)

The people who will use the intelligence help define what it must answer, through war-room sessions, research sprints, and a synthesis workshop, instead of one analyst deciding what matters.

In this repo: methods/collaborative-war-gaming.md

### Stakeholder-Type Feedback Simulation (DESIGNED)

Runs a draft through the voices of anonymized stakeholder types (creator, first-time reader, gatekeeper) before real readers see it. A Virtual Project Team variant; never simulates a real, named person.

In this repo: methods/stakeholder-type-feedback.md

### Self-Coaching Toolkit for High-Ambiguity Work (DESIGNED)

A numbered library of fifteen coaching cards and fifteen forms for work with scarce feedback and no coach: name the stall, interrupt it, and track it over time.

In this repo: methods/self-coaching-toolkit.md

### Operating Instrumentation System (DESIGNED)

A form-first way to run a work portfolio or small business: a few short forms capture what is happening, expose repeating friction, feed a weekly routing decision, and keep evidence of what got done. Capped at four or five active forms.

In this repo: methods/operating-instrumentation-system.md

## Research and Knowledge Methods

### Multi-AI Verification Protocol (PROTOTYPE)

Cross-checks one model's output with another through verification sequences, synthesis steps, and alignment checks. Agreement across models is a weak signal, not confirmation: a second model catches slips and argues the opposite case, while confirmation comes from independent sources plus one check no model controls. A three-model council variant (independent analysis, cross-critique, synthesis) is designed but has not been run end to end.

In this repo: methods/README.md

### Five-Phase Cross-AI Workflow (PROTOTYPE)

The mature form of the protocol above: each phase of an analysis goes to a model with a defined role (creative design, hostile audit, integration, synthesis, final QC), and a confidence level is tracked for each claim through the phases. Run end to end once. Phase agreement is still not corroboration.

In this repo: methods/README.md

### Research and Verification Practices (BUILT)

Structured research with cross-checking, used routinely across research projects; a cross-check between models counts only as a model check, and corroboration needs independent sources. A time-boxed variant (PROTOTYPE) caps the time spent per claim, runs in phases, and flags confidence explicitly.

Not packaged yet.

### Verification Test Set (PROTOTYPE)

A labelled benchmark of your own drafts with known defects (wrong content and omissions) plus clean controls, used to score any verification component before a change is promoted. Each item carries its origin, sources, defect type, severity, ground truth with a supporting quote, and the expected catch.

In this repo: templates/VERIFY-TESTSET.template.md

### Knowledge Cards (PROTOTYPE)

A modular format for storing operational rules and standards: one short Markdown file per rule, with YAML frontmatter (method cards carry title, category, version, status, and origin; findings cards use templates/knowledge-card-template.md). Cards recur across domains as a retrieval layer, small enough to load, cite, and version one at a time; the cards/ folder holds working examples on strategy, processing, quality, collaboration, and tools.

In this repo: templates/knowledge-card-template.md, cards/

### Multi-Layer Report Generation (BUILT)

A repeatable report architecture in three layers: executive summary, then analysis, then evidence.

In this repo: methods/README.md

### Project Status Brief (PROTOTYPE)

A fixed five-part recap for re-entering a project after time away: purpose in one sentence, status, work completed, active threads and next steps, and overlap with other projects. Prompt-driven, with no tooling; it recurs as the standard re-entry format across several projects.

In this repo: methods/README.md

### Intelligence Gap Tracker (DESIGNED)

A carried-forward list of open questions, each with an owner and a resolution path, surfaced at the top of every status review. The same gap list has been carried across many working sessions; there is no standalone artifact yet.

Not packaged yet.

### NotebookLM Research Sprint (PROTOTYPE)

Load a corpus of peer documents (charters, reports, comparable programs) into a dedicated NotebookLM notebook, run a sequenced set of test queries, and harvest the answers into report sections.

Not packaged yet.

### Tool-Routed Research Prompt Library (DESIGNED)

A prompt set that routes each open research question to one of three lanes: NotebookLM, a deep research run, or direct verification. It is paired with a development tracker.

Not packaged yet.

### AI Conversation History Analysis Method (PROTOTYPE)

A corpus-mining method for an export of your own AI conversation history: two-pass categorization, a multi-dimension skills inventory, prompt-complexity scoring, and an enriched conversation index.

Not packaged yet.

### Iterative Session Design (DESIGNED)

Five prompts for the stages of a long working session: a frame-first opening, a mid-session checkpoint, a critique loop, a controlled ideation pivot, and a session close that extracts what to carry forward. A broader prompt template library is still at concept.

In this repo: methods/iterative-session-prompts.md

### Context Engineering Enhancement Framework (DESIGNED)

A method for structuring persistent context across projects, built on session dump rituals and context isolation between workstreams, with links to a record schema and multi-model checks.

Not packaged yet.

### Storytime Translation (CONCEPT)

Recasts dense technical notes as a plain-language narrative for a non-technical reader, to test whether the ideas are understood and to produce plain language ready for policy or public use. A recurring habit with several finished examples; not yet written up as a procedure.

Not packaged yet.

### Snapshot-vs-Benchmark Tracking (DESIGNED)

Scores each recurring data snapshot against a benchmark set in advance, on a fixed metric set, and revises the forecast every cycle.

In this repo: methods/snapshot-benchmark-tracking.md

### Benchmark-Anchored Forecast Sheet (DESIGNED)

A one- or two-page forecast sheet a team fills in before a known outcome, built by anchoring to a historical benchmark, cutting redundant questions, using proxies for what cannot be measured, and reviewing twice.

In this repo: methods/benchmark-forecast-sheet.md

### AI Project Setup Pattern (DESIGNED)

How to set up an AI project space so each workstream keeps its role, rules, and reference files across sessions: standing instructions, structured uploads, and a deliberate split of work across models.

In this repo: methods/ai-project-setup.md

### Verification Evidence Register (DESIGNED)

A runtime file for the claim-level evidence behind your standards: one dated entry per finding, with status, number of independent evidence chains, and quoted support.

In this repo: templates/VERIFICATION-EVIDENCE.template.md

### Ground Truth Reference (DESIGNED)

A standing project file sorting the claims a body of work relies on into Verified, Reported (verify before use), and Do not use, so every deliverable draws from one checked list.

In this repo: templates/ground-truth-reference.template.md

## Strategy and Innovation

### Strategy Kernel Lab (PROTOTYPE)

A strategy engine that combines Rumelt's kernel (diagnosis, guiding policy, coherent actions), Martin's strategy cascade, and Munger-style stress testing, run in three modes: Evaluate, Build, and Improve. It uses a ten-item quality checklist and fixed output formats, installed as project instructions, and includes a phased strategy-review variant.

In this repo: cards/rumelt-good-strategy.md, cards/munger-mental-models.md (reference cards; the lab instructions are not packaged)

### Strategy Kernel Applied-Assumptions Format (BUILT)

A standard opening for strategy products: diagnosis, guiding policy, and coherent actions, followed by numbered assumptions, each with a confidence level and a cited source, that later sections cite by number. Derived from Strategy Kernel Lab and used as a standing rule across strategy documents and training outlines.

Not packaged yet.

### Choose-Your-Adventure Reasoning System (PROTOTYPE)

A branching reasoning tool for complex decisions: scenario trees, decision pathways, and consequence mapping.

Not packaged yet.

### Integrated Innovation Multi-Framework System (DESIGNED)

A multi-method innovation engine that selects among TRIZ, Theory of Constraints, Design Thinking, biomimetics, Axiomatic Design, Lean Six Sigma, systems thinking, SCAMPER, and Synectics, using a selection decision tree and an effectiveness matrix. Custom instructions and three slash commands are written; there is no logged use.

Not packaged yet.

## Schemas and Patterns

### The Recurring Design Spine (DESIGNED)

The shape most of these systems share: input, then scoring, then storage, then activation, then interface, with a knowledge-card retrieval layer and a verification layer that rests on independent anchors (source-derived checklists, primary-record reads, human lookups) rather than agreement between models. Labelled DESIGNED as a method because it was extracted from working systems and there is no log of it being applied deliberately to a new build.

In this repo: methods/README.md

### Meta-Architecture Pattern Library (DESIGNED)

A library of reusable system-design templates that turn recurring patterns into teachable form. One of five templates is complete, a Schema Design Template with anti-patterns and an implementation sequence; the pipeline, role-based routing, trust scoring, and knowledge card templates are not started.

Not packaged yet.

### docx Generation Pattern Library (PROTOTYPE)

Reusable Node.js patterns for generating Word documents with the docx library: table of contents, tables, cover pages, callout boxes, and page breaks. Working code has been reused across several deliverables but is not yet packaged as a module.

In this repo: methods/README.md (description only; no code in v1)

### Finding Classification Schema (BUILT)

Every adversarial finding is classified as Dangerous, Exploitable, Boring, or Irrelevant, and the audit leads with the first two.

In this repo: skills/adversarial-pass/SKILL.md

### Stakeholder Map Schema (PROTOTYPE)

One row per actor: stance, incentive, blocking power, and relationships. Used by hand across many projects; an agent version is still a concept.

In this repo: skills/guardian-context/references/templates.md

### Sourced-Claim Format (PROTOTYPE)

A one-line claim, a confidence rating, and a single working URL per claim, so each line of a brief can be checked on its own.

Not packaged yet.

### Skill Test Record (BUILT)

One entry per skill: version, where it is deployed, maturity, refactor flags, and one line per real test (date, task, win or loss, cause). It is the evidence the promotion gate reads.

In this repo: templates/SKILLS-RECORD.template.md

### Systems Index (BUILT)

A single working inventory of your AI systems by domain, each with a status label, with dated archive copies kept in place of deletions so the history of the work stays visible.

In this repo: templates/SYSTEMS-INDEX.template.md, cards/ground-truth-guardrails.md

### Executive Brief Template (DESIGNED)

Bottom line up front, then Situation, Complication, Question, Answer, supported as a Minto pyramid; each recommendation opens with Accelerate, Pause, or Reframe.

In this repo: templates/executive-brief.template.md

### Issues and Solutions Workbook (DESIGNED)

Two linked fixed-column tabs, issues and candidate solutions, asking of every solution whether it is already done here, who else does it, documented return, owner, and timeline.

In this repo: templates/issues-solutions-workbook.template.md

## Retired and paused

Entries here carry RETIRED or PAUSED in place of a maturity label and record only the general lesson.

### Integrated Mega-Platforms (RETIRED)

Three efforts to build integrated platforms were retired: a unified architecture spanning every tool, routing and edge-case engines built as one platform, and systemic risk mapping as a standalone toolset. One further full build is paused rather than abandoned. Lesson: oversized architecture documents prevented execution, and the parts that survived were the ones useful on their own, such as schemas, cards, and verification steps.

### Model Agreement as Verification (RETIRED)

Earlier verification methods counted agreement between models as confirmation. Models from different vendors share errors, so agreement is now treated as a weak prior, and confirmation requires independent sources plus one check no model controls.

### Stock Deep Research Skill (RETIRED)

A generic deep research skill was switched off and replaced by research-run. Lesson: build the research discipline (one gating question, a discovery clause, independent evidence chains) into the skill itself rather than relying on a general-purpose one.
