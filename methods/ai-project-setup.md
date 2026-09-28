# AI Project Setup Pattern

Status: DESIGNED (generalized from a project-space practice used routinely across several workstreams; this written form has not yet been used to set up a new project)

## What it is

A repeatable way to set up an AI project space (a Claude Project or any tool with standing instructions plus uploaded files) so that each workstream keeps its own role, rules, and reference material across sessions. It has three parts: custom instructions that fix the operating frame, structured uploads that hold persistent context the model loads on demand, and a deliberate split of work across more than one model where that helps. The goal is to stop re-explaining the same context at the start of every chat.

## When to use it

- A workstream will run for weeks or months and you keep pasting the same background into new chats.
- You juggle several domains (for example consulting, research, writing, finance) and want each one to answer by its own rules.
- You want a single front-door space that sorts incoming material and sends it to the right workstream.
- You are about to use a second model for drafting, critique, or checking and want a defined role for each.

## How to run it

### 1. Decide the project map

1. One project per workstream that has its own rules, sources, or audience. Do not create a project for a one-off question.
2. Optional: a front-door (intake) project whose only job is to sort pasted material and say which workstream each item belongs to. Its instructions can be one line that runs a triage skill (for example guardian-intake, if you use it) on anything pasted in.

### 2. Write the custom instructions

Keep them short and structural. Use these sections:

1. **Operating frame:** the role the model plays, the objective, and the stance (for example analytical, structured, concise, acting as a senior peer rather than a generic assistant).
2. **Global constraints:** the absolute rules. Typical ones: no conversational filler, begin with the requested content; no unsolicited lecturing unless a plan breaks a law, a hard constraint, or the arithmetic; default output format (for example Markdown, no raw JSON or XML unless asked); when a request is highly ambiguous, do not guess, list the specific clarifying questions (for example three) first.
3. **Routing to knowledge files:** for each domain or task type, a trigger and an action: "When the request is about [domain], read [file] first and rely on it rather than general training." Add a domain constraint where one matters (for example "numbers only in tables", "use the voice in the style guide").
4. **Execution protocols:** for multi-step requests, a pre-work plan before the deliverable: the files or data needed, the 2 or 3 core assumptions, then pause for approval. Optionally a keyword (for example IDEATE) that suspends constraints to produce five divergent approaches, followed by a return to constraints and a viability critique of all five.
5. **Standard output format:** the default shape for complex answers (for example a two-bullet summary, then analysis, then numbered next steps).

### 3. Structure the uploads

1. One topic per file, named for what it holds (style guide, strategy rules, reference data, glossary). The routing lines in the instructions point to these names.
2. Put stable rules and reference material in files; keep the instructions themselves about behavior.
3. Add small working files the project needs to function, for example a routing map that lists destination projects, or a parked-items file with one dated line per item.
4. Replace every placeholder in uploaded templates with real names before uploading.
5. When a session produces rules worth keeping, save them as a file (the session-close prompt in iterative-session-prompts.md does this) and upload it, so the next session starts from them.

### 4. Assign roles if you use more than one model

1. Give each model a defined job rather than asking all of them the same question: for example one drafts, one critiques hard, one checks the final against the sources.
2. Treat agreement between models as a weak signal, not confirmation. Models from different vendors share many of the same errors. Confirmation comes from independent sources plus one check no model controls (a primary record, a person, a calculation you run yourself).

### 5. Test before relying on it

1. Open a new chat in the project and give it a real, messy input of the kind it will see.
2. Check that it loaded the right file, followed the constraints, and produced the standard format.
3. Fix the instructions or files, not the individual answer, when it misses.

## Output

A set of project spaces, each with a one-screen instruction block, a small library of named reference files it routes to, and (if used) a front-door project that sorts incoming material; plus a written role for each model in any multi-model workflow.

## Template

```
PROJECT: [name]

## 1. Operating frame
Role: [role]
Objective: [what this project exists to do]
Stance: [e.g. analytical, structured, concise; a senior peer]

## 2. Global constraints (absolute)
- No conversational filler. Begin with the requested content.
- No unsolicited warnings unless a plan breaks a law, a hard constraint, or the math.
- Default format: [Markdown / tables for numbers / etc.]
- If a request is highly ambiguous, do not guess. List [3] clarifying questions first.

## 3. Routing to knowledge files
- Trigger: [domain or task]  Action: read [file.md] first.  Constraint: [rule]
- Trigger: [domain or task]  Action: read [file.md] first.  Constraint: [rule]

## 4. Execution protocols
- Multi-step requests: give a pre-work plan (files needed, 2 to 3 assumptions), then wait for approval.
- Keyword [IDEATE]: five divergent approaches, then return to constraints and critique all five.

## 5. Standard output
- Summary: [max 2 bullets]
- Analysis: [format]
- Next steps: [numbered]

UPLOADS
- [file.md]: [what it holds]
- [file.md]: [what it holds]

MODEL ROLES (if more than one model)
- [model]: [draft / critique / final check]
- Agreement between models is not confirmation; name the independent check.
```
