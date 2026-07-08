---
name: post-production-review-tracker
description: Track client and internal feedback across post-production review rounds for video/film/design deliverables - consolidating notes, resolving conflicts, and logging what changed each round. Use when collecting feedback on a cut/design, consolidating notes from multiple stakeholders, or tracking revision history across rounds. Triggers on "consolidate feedback", "review round notes", "client notes on the cut", "revision tracker".
---

# Post-Production Review / Feedback Tracker

## Purpose

Multi-stakeholder feedback on a cut, design, or deliverable tends to arrive messy — scattered across email, Slack, timestamped video comments, and calls — and often contains contradictions. This skill consolidates it into one authoritative note set per review round, flags conflicts instead of silently picking a side, and keeps a running history so "didn't we already try that" has an answer.

## When to use

- Feedback has come in on a cut/design/deliverable from one or more stakeholders and needs consolidating for the editor/designer
- Two stakeholders gave contradicting notes and someone needs to make the call
- A project needs a running revision history across multiple review rounds

## Inputs needed

- The deliverable being reviewed and which round this is
- Raw feedback (paste emails, timestamped comments, call notes — as many sources as exist for this round)
- Who gave which feedback (needed to resolve conflicts by stakeholder seniority/ownership, and to know who to follow up with)

## Process

1. Use `references/feedback-tracker-template.md`.
2. Extract every discrete note from the raw input as its own row — don't merge multiple notes into one line even if they came from the same email.
3. Timestamp/location each note against the deliverable (e.g., "0:42", "slide 3", "logo on homepage hero") wherever the source material allows it — vague notes like "the middle part" should be flagged for clarification rather than guessed at.
4. Categorize each note: must-fix, suggestion/optional, or question needing client clarification.
5. Actively check for contradictions across stakeholders (e.g., one reviewer wants the pacing faster, another wants a beat added in the same section). Flag these explicitly — don't silently resolve them by picking one. Surface the conflict to the account manager/creative director for a decision.
6. Mark each note's status as rounds progress: Open / In progress / Addressed / Declined (with reason).
7. Append to `clients/<client-name>/05-post-production/feedback-<deliverable-slug>.md` — this is a running log across rounds, not a new file per round, so history is preserved.

## Notes

- "Addressed" should mean the editor/designer confirms it was actually done, not that the note was received.
- A "Declined" note needs a one-line reason (budget, technically infeasible, conflicts with brief) so it doesn't resurface unexplained in round 3.
