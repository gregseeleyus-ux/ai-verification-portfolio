# Operating Instrumentation System

Status: DESIGNED (architecture and form examples exist from two research passes; a pilot has not run)

The design principles below summarize those research passes. They have not been independently verified here; treat them as starting rules to test in your own pilot.

## What it is

A form-first way to run the operations of a work portfolio or small business, where the overwhelm comes less from volume than from unclear routing and friction that keeps repeating. A handful of short forms act as sensors: they capture what is happening, make friction and open commitments visible, feed a weekly routing decision, and preserve evidence of what actually got done. It follows a capture, diagnose, intervene, learn sequence. It is an instrumentation system, not a productivity system: the goal is visibility and closed loops, not task-completion counts or compliance.

## When to use it

- You carry many parallel threads (clients, deals, projects, vendors) over long cycles and things fall through the cracks.
- The same obstacles keep surprising you and you have no record of them.
- Capture is happening somewhere, but nothing gets routed and the inbox keeps growing.
- You have tried elaborate tools that did not last; this is the minimal alternative.

## Design rules

1. **Four to five active forms, no more.** Beyond that, maintaining the system becomes its own burden. Start with fewer.
2. **Separate capture from processing.** Forms capture during the day; routing happens in a weekly batch. Combining them recreates the overwhelm.
3. **Specificity closes loops.** A concrete plan ("draft proposal intro, 30 minutes, Tuesday 10am") settles an open item as well as finishing it; "work on proposal" does not.
4. **Brevity sustains practice.** Entries of 1 to 4 sentences. Nothing is too small to note.
5. **Evidence over compliance.** Archive what got done; do not track what you failed to do. No streaks or daily compliance metrics.
6. **Design for gaps.** A missed day or week must not break the system; resume at the next weekly review.
7. **Same fields across capture modes.** Paper, digital, or a quick phone note all use the same field order (for example TIME | WHAT | CONTEXT | STATUS | NEXT) so everything normalizes to one structure. An AI assistant can do the normalizing.
8. **"Consciously dropped" is a valid outcome.** Every item closes as done, delegated, deferred, or dropped.

## How to run it

The five forms map to the four stages. The stage labels are the architecture; the form contents come from the source examples.

### 1. Capture

**Daily intake form** (continuous, at task transitions). Purpose: externalize what you just did, what you are about to do, and any friction, without analysis or routing. Not for organizing, prioritizing, or deciding. Timestamped entries, 1 to 4 sentences, with the next action stated as a first physical step, not a project name.

**Obligation capture form** (whenever a commitment is made). Purpose: a reliable record of promises you made and things you are waiting for from others. Not for task planning. Two parts:
- Waiting-for list: what, from whom, date requested, due date, project. Belongs here: delegated tasks, blocking dependencies, expected replies, quotes, approvals, handoffs. Does not belong: your own tasks (next-action list), scheduled meetings (calendar), someday ideas (separate list).
- Promise tracker: who, what was promised, by when, status (not started, in progress, waiting for, done), notes.

**Friction log** (in the moment, when you hit resistance). Purpose: evidence for process improvement, not problem-solving on the spot. Fields: what you were trying to do, what created friction, impact, severity (Green minor annoyance, Yellow frustrating and slowed progress, Red would have quit), where you would have quit, what would have helped. Record facts, not judgments ("couldn't find the template", not "terrible organization"). One-line form: `[TIME] [TASK] - STUCK: [what blocked me] | SEVERITY: [G/Y/R]`.

### 2. Diagnose

At the weekly review, read the week's intake entries and friction log for patterns rather than one-off incidents: repeated obstacles, missing processes, tools that do not work, unclear routing, and places where time leaked. Red items and "where I would have quit" entries are the highest-priority fixes. Also scan the obligation lists for anything overdue or stalled.

### 3. Intervene

Run the **weekly routing form** (30 to 45 minutes, one batch):
1. Clear (about 10 minutes): check off completed items; empty every inbox and capture mode to zero; brain-dump anything not yet captured.
2. Current (about 15 minutes): review last week's calendar for loose ends and next two weeks for prep; review the waiting-for list and follow up on anything at or past due; review the project list and make sure each active project has a specific next action.
3. Route: for each open item, decide do next week, defer, delegate, or drop.
4. Fix: pick one process fix from the diagnosed friction.
5. Ready (about 5 minutes): pick 3 to 5 priorities for next week and schedule when you will work on them.

Optional daily bookends (5 minutes each): evening, what got done (move to the archive), what is still open (keep, drop, defer), what created friction (one sentence), tomorrow's first action; morning, the single most important thing and when you will work on it.

Coaching prompts, if you add them, come after capture is a habit, never before. Keep them optional, context-triggered, and one at a time (for example "What is creating friction right now?", "What single item would create the most relief if resolved?", "Done, delegated, deferred, or dropped?"). Prompts that fire on a fixed schedule, highlight failures, or must be answered to proceed do harm. If prompts need their own tracking, they have become overhead.

### 4. Learn

**Progress evidence archive** (from day one). Purpose: a searchable record of what actually happened, for pattern recognition. Not for analysis. Items move here when completed or consciously dropped: date, item, project, effort, outcome or handoff, notes (for example "client liked the cost comparison table; reuse the format"). Once a week, write a short evidence summary: completed, progress by project, friction observed, process improvements.

### Rollout

1. Weeks 1 and 2: daily intake form only. Keep the evidence archive from day one.
2. Week 3: add the friction log.
3. Week 4: add the weekly routing form.
4. Add obligation capture when commitments start slipping; stay at or under five active forms.
5. Add prompts only once the capture rhythm is established.
6. Refresh the practice through small variations (a different notebook, a different capture spot) rather than switching systems. Tool-hopping resets the benefit of consistent use.

### Test and success criteria

Test first: a single intake form with at most three fields; friction logging for one week to surface repeated patterns; the four-way routing in the weekly review; "consciously dropped" as an explicit closure option.

Avoid from the start: multiple tools that must stay in sync; elaborate tags or properties; daily compliance metrics or streaks; prompts before capture is habitual; optimizing the design before testing the minimal version.

The pilot succeeds if: the system is used for 14 consecutive days without major gaps; friction patterns become visible in the logs; the weekly review takes under 45 minutes; fewer items slip through unnoticed; at least one process improvement comes out of the evidence.

### Failure signals

- **Over-logging:** more time logging than doing; avoiding the forms because they are burdensome; more than 15 minutes a day of maintenance; logging more than you review.
- **Under-logging:** cannot remember what you worked on yesterday; the same friction keeps surprising you; things regularly fall through cracks; no evidence of progress accumulating.
- **Needs routing:** capture works but nothing gets done; no weekly review in two or more weeks; urgent drowns out important every day.
- **Helping:** clearer sense of what to do next; completed work accumulating as evidence; fewer dropped handoffs; friction patterns visible.

## Output

Weekly: a routed list (each open item marked do, defer, delegate, or drop), 3 to 5 scheduled priorities, one process fix drawn from the friction log, and an evidence summary. Over time: an archive and friction history that show where the operation's processes break.

## Template

```
DAILY INTAKE
[TIME] - Just did: ______________________
[TIME] - Next (first action): ______________________
[TIME] - Friction or thoughts: ______________________

OBLIGATIONS
Waiting for | From whom | Requested | Due | Project
____________|___________|___________|_____|________
Promised | To whom | By when | Status | Notes
_________|_________|_________|________|______

FRICTION LOG
Time: ______  Trying to: ______________________
Friction: ______________________
Impact: ______________________
Severity: [ ] Green  [ ] Yellow  [ ] Red
Where I would have quit: ______________________
What would have helped: ______________________

WEEKLY ROUTING
Clear
[ ] Completed items checked off
[ ] All inboxes and capture modes at zero
[ ] Brain dump done
Current
[ ] Last week's calendar: loose ends captured
[ ] Next two weeks: prep noted
[ ] Waiting-for list: follow-ups sent
[ ] Every active project has a specific next action
Route (one line per open item)
Item: ______________  [ ] Do  [ ] Defer  [ ] Delegate to ______  [ ] Drop
Diagnose
Repeated friction this week: ______________________
Process fix to try: ______________________
Ready
Priorities (3 to 5), with when:
1. ______________________
2. ______________________
3. ______________________

EVIDENCE ARCHIVE
Date completed | Item | Project | Effort | Outcome | Notes

WEEKLY EVIDENCE SUMMARY
Week of: ______
Completed: ______________________
Progress by project: ______________________
Friction observed: ______________________
Process improvements: ______________________
```
