---
name: Spec stress-tester
description: >-
  Use when reviewing a PRD, product brief, Notion spec, or feature write-up
  before eng starts. Finds decisions the PM must make: ambiguities, untestable
  acceptance criteria, missing edges, trust/compliance gaps. Outputs a PM
  decision artifact, not an eng bug dump.
---

# Spec stress-tester

Stress a product spec so a PM can decide in a sync without opening eng docs.

## When to run

- Before kicking eng on a PRD or brief
- When a spec feels "almost ready" but fuzzy
- After a big rewrite of goals, AC, or rollout

Do not use for design critique of screens, code review, or writing the PRD from scratch.

## Inputs

Require one of:

- Pasted PRD / brief
- Notion or doc link the user can access
- Rough notes labeled as a draft spec

If the doc is missing, ask once for it. Do not invent product facts.

## Checklist (run every item)

Work the list. Skip only with an explicit "N/A — reason" line.

1. **Status / state enum + map** — Customer-facing states listed? 1:1 map from backend/API? Who owns ambiguous terminals?
2. **AuthZ matrix** — Who sees what (roles × capabilities × scope: property, portfolio, amounts)?
3. **API / data contract** — Fields the UI needs attached (or field table). No assumed codes.
4. **Trust semantics for terminal states** — What does success mean to the user (e.g. Paid = sent vs landed)? Slip / recovery copy?
5. **Retention / time window** — Default list window, max history, what happens after.
6. **Measurable acceptance criteria** — Perf targets, a11y bar, browser matrix, metric baselines + targets. Kill fuzzy words: accurate, fast, materially, accessible, major browsers.
7. **Error / empty / failure copy ownership** — Strings locked? Who writes, who maps codes?
8. **Compliance / PII** — What identifiers show, Legal bar, masking rules.
9. **Rollout / kill criteria** — Flag name, audience, success/kill thresholds.
10. **Capacity confirmation** — Eng/design capacity acknowledged, or called out as risk.

Also scan for: multi-currency/formatting, rails in/out of scope, calendar vs business-day ETAs, open questions left without owners.

## Output format (required)

Lead with a one-line verdict: Ready / Ready with decisions / Not ready.

Then two buckets:

### Decide this week

For each finding, use this exact card shape:

```
### Severity P0|P1|P2 — <short title>
What's wrong: <one line, plain language>
Decision: <the choice the PM must make>
Default: <opinionated suggested default>
Who: <roles to pull in>
Done-when: <what lands in the PRD to close it>
```

Severity guide:

- **P0** — Blocks a correct build or burns user trust / compliance
- **P1** — Untestable AC or fuzzy success (ship risk)
- **P2** — Missing edge or product hole (can wait a sprint)

### Can wait

Same card shape, or a short bullet list if truly minor.

### Spec patch (paste back)

End with 3–7 imperative lines the PM can paste into the PRD (no prose). Example:

- Freeze status enum + API→UI map
- Add role × capability table
- Attach API field table
- Define Paid = landed + slip copy
- Set list window = 90 days

## Style

- Plain, direct, Apple HIG writing style: verbs over adjectives, no hype
- Decision-first. Never a wall of critique without a Decision and Done-when
- Do not invent metrics, API fields, or legal requirements. Say what is missing
- One finding per card. Merge duplicates
- If the spec is already tight, say so and list only residual risks

## Example (condensed)

Verdict: Not ready — five P0 decisions before UI eng.

### Decide this week

### Severity P0 — Status map
What's wrong: Pending/Processing/Paid/Failed/On hold? with no backend map.
Decision: Freeze the customer-facing enum and when Paid means (rail accepted vs bank landed).
Default: Pending → Processing → Paid (landed) → Failed; drop On hold from v1 or fold into Failed+reason.
Who: Eng (payments) + Product.
Done-when: Table of API state → UI status + copy keys in the PRD.

### Spec patch (paste back)
- Freeze status enum+map
- Role matrix for amounts and property scope
- Attach API field table
- Define Paid=landed + slip copy
- Set list=90 days
