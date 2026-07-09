---
name: status-report-generator
description: Generate a client-facing or internal weekly/biweekly status report summarizing project progress, blockers, upcoming milestones, and decisions needed. Use when it's time to send a client update, prep for a status call, or summarize where a project stands. Triggers on "status report", "client update", "weekly recap", "where do things stand on".
---

# Status Report Generator

## Purpose

Produces a status update that a client can read in 90 seconds and know exactly what happened, what's next, and what they need to do. Not a diary of everything the team did — a decision-oriented summary.

For a bigger, more visual, continuously-refreshed status page (multi-workstream programs, ongoing retainers), consider using the `project-artifact` plugin skill instead, which publishes a shareable, redeployable status page rather than a one-off written report.

## When to use

- Weekly/biweekly client status update is due
- Prepping talking points for a status call
- Internal leadership needs a quick read on project health across accounts

## Inputs needed

- Project/client name and reporting period
- What happened this period (pull from project docs, recent briefs/production docs/feedback trackers if this skill is being run in the project's context)
- Any blockers or client-dependent items
- Upcoming milestones in the next period

## Process

1. Use `references/status-report-template.md`.
2. Lead with overall health (on track / at risk / blocked) — don't bury this at the bottom.
3. List what shipped/completed this period as concrete outcomes, not activity ("Delivered final cut of Video 2" not "worked on editing").
4. List blockers with an explicit owner and ask — a blocker with no named owner won't get resolved.
5. List what's coming next period so the client isn't surprised by upcoming asks (approvals needed, shoot dates, content needed from them).
6. Keep it to one page. If there's more detail worth preserving, put it in the relevant tracker (feedback tracker, retainer tracker) and link to it rather than inflating the status report.

## Notes

- If a project is genuinely at risk (timeline, budget, or scope), say so plainly in the health line — don't let a cheerful tone bury a real problem the client needs to know about.
