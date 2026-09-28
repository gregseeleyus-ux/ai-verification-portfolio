# Iterative Session Prompts

Copy these at the matching stage of a working session. Fill in the bracketed parts.

## 1. Session opening (frame first)

Use as the first prompt of a new task.

> Act as a [role]. Our primary objective is to [overall goal]. You must not [one or two strict constraints, for example use external libraries, or add conversational filler]. Before producing the final output, give me a pre-work plan listing your assumptions and dependencies, then wait for my approval to proceed.

## 2. Mid-session checkpoint

Use when the conversation is long (three or four long turns) or the model starts losing track of earlier rules.

> Pause and let's reset our context. Summarize every decision, rule, and constraint we have agreed on so far as a dense key-value list in Markdown. List the tasks still to be done and state the immediate next step. I will use your output to start a fresh session.

## 3. Critique loop

Use right after the model produces a first draft.

> Do not treat the previous draft as final. Critique it specifically on [dimension, for example edge cases, brevity, efficiency]. Then give a revised version that fixes the flaws you found. Format the final output strictly as [format].

## 4. Controlled ideation pivot

Use when the answers are stuck in predictable territory.

Step 1:

> Set aside the operating constraints for a moment. Generate five radically different, speculative approaches to this problem. Do not filter them for feasibility yet.

Step 2 (send right after step 1):

> Now return to our constraints. Audit those five ideas hard against [real-world constraint, for example budget, compliance, physics]. Drop what cannot work and combine what survives into one actionable plan.

## 5. Session close

Use at the end of a successful session to keep what was learned.

> This session is ending and I want to keep our decisions. Summarize the final design, interfaces, and style rules we settled on as a dense, structured Markdown document. Leave out the conversation history and keep only explicit rules. I will save it as a CLAUDE.md file for future sessions.
