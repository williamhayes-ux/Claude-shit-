---
name: meeting-notes-action-tracker
description: Turn raw client call notes, transcripts, or meeting recordings into structured meeting notes with clear action items, owners, and due dates. Use after a client call, internal meeting, or when a transcript needs to become a followable action list. Triggers on "notes from the call", "turn this transcript into action items", "what did we agree to on that call", "meeting recap".
---

# Meeting Notes → Action Tracker

## Purpose

Raw call transcripts and hastily-typed notes are hard to act on. This skill extracts what was actually decided and who owes what, separate from general discussion, so nothing agreed to on a call quietly evaporates.

## When to use

- Right after a client or internal call, with a transcript, recording notes, or rough notes to process
- Someone needs to confirm what was actually agreed to versus just discussed

## Inputs needed

- Raw transcript or notes from the meeting
- Attendee list (if not clear from the transcript)
- The project/client this meeting relates to

## Process

1. Use `references/meeting-notes-template.md`.
2. Separate three categories clearly: **Decisions made** (final, agreed), **Action items** (someone owes a deliverable), and **Discussion/context** (useful background, not actionable).
3. Every action item needs an owner and a due date. If the meeting didn't assign one, mark `[NEEDS OWNER]` or `[NEEDS DUE DATE]` rather than assuming — assigning work to someone who didn't agree to it causes real problems.
4. Distinguish client-owed action items from agency-owed ones — these need different follow-up (a client action item may need a reminder email; an agency one goes straight into the team's workflow).
5. Flag anything ambiguous — a "maybe" or a trailed-off sentence in a transcript shouldn't get promoted to a firm decision.
6. Save to `clients/<client-name>/01-brief-strategy/meeting-notes-<date>.md` (or the most relevant project subfolder if the meeting was about a specific phase, e.g. `05-post-production/` for a feedback call).

## Notes

- If the meeting effectively produced a new or changed brief, scope, or budget, flag that explicitly and point to the relevant skill (`creative-brief-generator`, `proposal-sow-generator`) rather than letting it live only as a buried note.
