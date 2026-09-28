# Snapshot-vs-Benchmark Tracking

Status: DESIGNED. Generalized from a domain-specific tracking practice; this general form has not been used yet.

## What it is

A loop for reading data that arrives as recurring snapshots, building toward a known end point. Before the first snapshot you set a benchmark. Each snapshot is then scored against that benchmark on a fixed set of metrics, and the forecast for the end point is revised every cycle. Because the metric set stays fixed, cycles can be compared. Because the benchmark was set in advance, the read stays honest.

## When to use it

- A source publishes cumulative counts on a schedule (daily, weekly, monthly) before a final result is known.
- You need a running forecast of the final result, not just a report of the latest numbers.
- Examples: program enrollment during an open-enrollment window, registrations or pre-orders ahead of a launch, donations toward a fundraising deadline, ticket sales ahead of an event date.

## How to run it

1. **Write the benchmark before the first snapshot.** Give an expected value or range for each metric. Base it on a prior comparable cycle. If part of the current cycle is new and has no local history (a new customer group, a new channel), benchmark that part against an outside analog that already has the feature.
2. **Fix the metric set and keep it for the whole run.** Start from these five and adapt the labels:
   - **Mix:** each category's share of the running total.
   - **Pace:** change since the last snapshot.
   - **New-segment rate:** the uncertain or new segment's rate, compared with its analog.
   - **Composition by past behavior:** the share of repeat or reliable participants versus first-time participants.
   - **Unit share:** each geographic or organizational unit's share of the total.
3. **Record each snapshot in the same format.** For each category, record the total as of that snapshot, its share of the total, and the change since the last snapshot. Add a breakdown by unit showing category counts, unit total, and composition shares.
4. **Score against the benchmark.** For each metric, note whether it is running ahead of, on, or behind the benchmark, and by how much.
5. **Revise the forecast.** Update the end-point projection and say which metric moved it. Carry named reads forward (a working hypothesis such as "the new channel is not adding volume yet") and state each cycle whether each one still holds.
6. **Close the run.** When the final result arrives, compare it with the last forecast and with each named read.

## Output

A snapshot update for each cycle (the table, the scoring against the benchmark, and the revised forecast), plus a running log of named reads.

## Template

```
Snapshot Update [n]: [series name], as of [snapshot date]
Snapshots to date: [n]   Units covered: [count]

Totals
| Category | Total as of [date] | % of total | Change since last snapshot |
|----------|--------------------|------------|----------------------------|
| All      |                    |            |                            |
| [cat A]  |                    |            |                            |
| [cat B]  |                    |            |                            |
| Repeat / reliable   |         |            |                            |
| First-time          |         |            |                            |

Breakdown by unit
| Unit | [cat A] | [cat B] | [cat C] | Total | % repeat | % first-time |
|------|---------|---------|---------|-------|----------|--------------|

Scored against benchmark
| Metric | Benchmark | This snapshot | Ahead / on / behind | By how much |
|--------|-----------|---------------|---------------------|-------------|
| Mix |  |  |  |  |
| Pace |  |  |  |  |
| New-segment rate (vs analog) |  |  |  |  |
| Composition by past behavior |  |  |  |  |
| Unit share |  |  |  |  |

Forecast
- End-point projection: [value] (previous: [value])
- What moved it: [metric]
- Named reads: [read]: holds / weakening / broken
```
