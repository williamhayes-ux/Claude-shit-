---
name: content-calendar-builder
description: Build a social/content calendar for a client or brand - post scheduling, platform-specific formatting, campaign tentpoles, and caption drafts. Use when planning a month/quarter of social content, slotting a campaign into an existing content cadence, or organizing content around key dates. Triggers on "content calendar", "social calendar", "plan our posts for", "schedule content around".
---

# Social Content Calendar Builder

## Purpose

Builds a structured, platform-aware content calendar — not just a list of dates, but a plan that accounts for each platform's format constraints, the brand's posting cadence, and any campaign tentpoles or key dates that need to anchor the plan.

## When to use

- Planning a month or quarter of organic social content for a client
- Slotting a new campaign's content into an existing always-on calendar
- Building a launch calendar around a specific date (product launch, event, seasonal moment)

## Inputs needed

- Client/brand, platforms in scope (Instagram, TikTok, LinkedIn, X, YouTube, Facebook, etc.)
- Posting cadence/frequency per platform (if not specified, ask rather than assume — cadence varies wildly by client budget and platform)
- Any campaign brief, key dates, or product/launch calendar to anchor content around
- Brand voice/tone reference if available
- Approval workflow: who reviews/approves before scheduling

## Process

1. Confirm platforms and cadence per platform before building anything — a LinkedIn cadence of 3x/week is very different from a TikTok cadence of 1x/day.
2. Lay out the calendar using `references/calendar-template.md`, one row per post, grouped by week.
3. Anchor key dates first (campaign launches, holidays relevant to the brand, product releases), then fill in always-on/evergreen content around them.
4. For each post, note: platform, format (reel/carousel/static/story/long-form), pillar/theme, a caption draft or caption direction, and any asset dependency (needs new shoot vs. can reuse existing asset).
5. Flag content pillars that are underrepresented or platforms where the plan is thin relative to the stated cadence.
6. Save to `clients/<client-name>/03-content-calendar/calendar-<month-or-quarter>.md`.

## Notes

- Don't write final captions for platforms/brands you don't have a voice reference for — draft caption *direction* instead and flag that final copy needs brand review.
- Content pillars (e.g., product, culture/BTS, education, UGC/testimonial, promotional) should be identified explicitly so the mix can be sanity-checked — a calendar that's 80% promotional is a red flag worth surfacing, not silently building.
