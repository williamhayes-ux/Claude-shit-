---
name: production-docs
description: Generate video/film production documents - shot lists, call sheets, production schedules, and production budgets. Use when planning or prepping a shoot, when a producer needs a call sheet for a shoot day, when a director needs a shot list, or when a project needs a production timeline or budget. Triggers on "shot list", "call sheet", "shoot schedule", "production schedule", "production budget", "prep for the shoot".
---

# Production Docs (Shot Lists, Call Sheets, Schedules, Budgets)

## Purpose

Covers the four documents that carry a video/film production from greenlight to wrap: shot list, call sheet, production schedule, and budget. Each has its own reference template in `references/`. Pick the one(s) the request needs — don't generate all four unless asked for a full production packet.

## When to use

- A director/DP needs a shot list from a script, treatment, or brief
- A shoot day needs a call sheet (crew, cast, location, times, contacts)
- A project needs a production schedule (pre-pro through delivery)
- A project needs a production budget (line-itemized estimate or actuals)

## Inputs needed

Ask for whatever isn't already provided:
- **Shot list**: script/treatment/storyboard, or a scene-by-scene description; visual style references; runtime target
- **Call sheet**: shoot date, call time, location(s) with address, weather/sunrise-sunset if exterior, crew list with roles and call times, cast list, key contacts (producer, 1st AD, location contact) and phone numbers, parking/basecamp info, nearest hospital
- **Production schedule**: deliverable date, shoot day(s), known constraints (talent availability, location holds, post-production turnaround needed)
- **Budget**: scope (shoot days, crew size, cast, locations, gear, post scope), and whether this is a rough estimate or a locked budget

Never fabricate real-world details that carry safety or legal weight — nearest hospital address, insurance certificate numbers, permit numbers, exact crew phone numbers. Mark these `[CONFIRM]` if not supplied.

## Process

1. Identify which document(s) are being requested.
2. Use the matching reference template:
   - `references/shot-list.md`
   - `references/call-sheet.md`
   - `references/production-schedule.md`
   - `references/budget-template.md`
3. Fill in everything known from the brief/context. Flag unknowns rather than inventing them — especially safety-relevant fields on a call sheet.
4. For a shot list: number shots sequentially per scene (e.g. 1A, 1B, 2A), note shot size/angle/movement, lens if specified, and estimated setup time if the schedule is tight.
5. For a call sheet: double-check that every listed crew/cast member has a call time and every location has an address. A call sheet with a blank contact field is worse than no call sheet.
6. For a schedule: work backward from the hard delivery date through post, shoot day(s), prep, and pre-pro approvals, and flag if the available time looks unrealistic for the scope.
7. For a budget: separate above-the-line (talent, director, producer fees), below-the-line (crew, gear, locations, catering), and post-production (editing, color, sound, motion graphics, music licensing) line items, plus a contingency line (10-15% is standard).
8. Save to the client's project folder: shot lists/call sheets/schedules/budgets go under `clients/<client-name>/02-production/{shot-lists,call-sheets,schedules,budgets}/`.

## Notes

- Call sheets are safety documents as much as logistics documents — never guess emergency/medical info.
- If asked for a "production packet," generate all four using the same source scope so they stay internally consistent (same shoot dates, same crew list, same budget assumptions).
