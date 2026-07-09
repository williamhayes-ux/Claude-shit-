---
name: revenue-operations
description: Analyze the agency's own new-business pipeline health, forecast accuracy, and growth efficiency - not client work. Use when reviewing how many active pitches/proposals the agency has in flight versus its revenue targets, checking whether past revenue forecasts were accurate, or assessing the agency's own growth efficiency. Triggers on "how's our pipeline looking", "are we tracking to target this quarter", "review our new business pipeline", "forecast accuracy for the agency".
---

# Revenue Operations (Agency New-Business Pipeline)

> Adapted from the third-party [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills)
> repo (MIT License, © Alireza Rezvani), which wrote this for B2B SaaS revenue teams (ARR, CAC:LTV, NDR).
> Those metrics don't map onto a client-services agency, so this version keeps the underlying analytical
> frameworks (pipeline coverage, forecast accuracy, growth efficiency) but reframes them around the
> **agency's own new-business pipeline** — pitches and proposals in flight, not client engagements. The
> original Python scripts (`pipeline_analyzer.py`, `forecast_accuracy_tracker.py`,
> `gtm_efficiency_calculator.py`) were **not imported** — they expect SaaS-shaped JSON (ARR, ACV) that
> doesn't fit this business. If you want automation here, it needs to be rebuilt around agency deal data
   (proposal value, close probability, expected start date) rather than reused as-is.

## Purpose

This is about the agency's own health as a business — new client acquisition — not a specific client
engagement. Don't confuse this with `invoice-retainer-tracker` (existing client billing) or
`proposal-sow-generator` (drafting one proposal). This skill is for looking across *all* open pitches at
once and asking "are we going to hit our new-business target this quarter."

## When to use

- Reviewing how many active proposals/pitches the agency has out, and whether that's enough to hit a
  revenue target
- Checking whether the agency's past revenue forecasts have been accurate
- A quarterly/annual business review of the agency's growth trajectory

## Process

### Pipeline coverage review

1. List every open pitch/proposal: prospective client, proposed engagement value, stage (initial
   conversation / proposal sent / verbal yes / contract out), expected close date, and owner (which account
   person is running it).
2. Calculate coverage: total pipeline value in play ÷ the revenue target for the period. A coverage ratio
   below ~3x the target is a warning sign — most pitches don't close, so a thin pipeline relative to target
   means the target is at risk. (This 3x guideline comes from the source material's SaaS pipeline coverage
   benchmark — treat it as a starting heuristic, not a fixed rule, and calibrate to the agency's own
   historical close rate once there's enough history.)
3. Flag concentration risk: if one prospective deal is more than ~40% of total pipeline value, the forecast
   is fragile — surface this explicitly rather than presenting a coverage number that hides it.
4. Flag aging: pitches sitting in the same stage far longer than the agency's typical sales cycle need a
   decision (push forward, or write off) rather than sitting on the list indefinitely.
5. Use `references/pipeline-management-framework.md` for the underlying framework and
   `assets/pipeline_review_template.md` for the write-up (both still SaaS-flavored — read for the
   *approach*, adapt the field names to agency deal data as you use them).

### Forecast accuracy review

1. For each past period, compare what was forecast to close against what actually closed.
2. Calculate the error rate (MAPE — mean absolute percentage error) and note the direction: is the agency
   systematically over-forecasting (assuming pitches will close that don't) or under-forecasting?
3. Use `references/revops-metrics-guide.md` for the metric definitions and
   `assets/forecast_report_template.md` for the write-up.

### Growth efficiency (optional, lighter-weight for an agency than for a SaaS company)

The source material's Magic Number / LTV:CAC / Burn Multiple metrics assume subscription revenue and don't
translate cleanly to project/retainer-based agency revenue. If a growth efficiency review is genuinely
wanted, the useful adapted version is simpler: cost of new-business effort (hours/spend on pitching) versus
revenue actually won from it, over a comparable period. See `references/gtm-efficiency-benchmarks.md` for
the original framework if adapting further.

## Notes

- This skill produces an internal business-health view for agency leadership — it is not client-facing and
  doesn't belong in a `clients/` folder. Save output somewhere like `internal/pipeline-review-<period>.md`
  if a running record is wanted (create that top-level folder if it doesn't exist yet).
- Don't import client engagement data into "pipeline" — a signed client isn't pipeline anymore, they move to
  `invoice-retainer-tracker`.
