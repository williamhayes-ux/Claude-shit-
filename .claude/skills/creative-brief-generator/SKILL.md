---
name: creative-brief-generator
description: Turn a raw client ask (email, call notes, Slack message, verbal request) into a structured creative brief for a marketing/creative campaign. Use when a client has requested a campaign, asset, video, or content project and the team needs a brief before creative work starts. Triggers on "write a brief", "brief this project", "turn this into a creative brief", "what did the client actually ask for".
---

# Creative Brief Generator

## Purpose

Clients rarely hand over a clean brief — they hand over an email, a rambling call recap, or a one-line Slack message. This skill turns that raw input into a structured creative brief the Creative Director and production team can actually work from, and flags what's missing so nobody builds on assumptions.

## When to use

- A client ask (email, transcript, notes) needs to become a brief before creative or production work starts
- An account manager needs to hand off a project to the Creative Director
- An existing brief needs tightening or is missing key sections

## Inputs needed

Ask for (or extract from what's provided):
- The raw client ask — paste the email/notes/transcript verbatim if available
- Client/brand name and any existing brand guidelines location
- Known budget range and hard deadline, if any
- Who the deliverable is going to (internal stakeholder, target audience)

Do not invent client goals, budget, or deadlines that weren't stated or implied — mark them `[NEEDS CLIENT INPUT]` instead of guessing.

## Process

1. Read the raw input closely. Separate what the client explicitly said from what you're inferring.
2. Identify the campaign/project type (brand campaign, social content, video/film production, single asset, retainer work, etc.) — this determines which sections matter most.
3. Fill in `references/brief-template.md` section by section. Where information is genuinely absent, write `[NEEDS CLIENT INPUT: specific question to ask]` rather than a plausible-sounding guess.
4. Keep the objective and single-minded proposition sharp — one sentence each. If the client ask contains multiple competing goals, surface that tension explicitly rather than averaging it away.
5. Save the completed brief to the client's project folder at `clients/<client-name>/01-brief-strategy/brief-<project-slug>.md` (create the folder from `new-project-setup` first if the project doesn't exist yet).
6. Summarize back to the user: what's ready to hand to Creative, and the specific open questions that need a client answer before work starts.

## Output

Use `references/brief-template.md` as the structure. The finished brief should be usable as-is by a Creative Director with no further client contact required, except for the items explicitly flagged as open questions.

## Notes

- A brief with 3 flagged open questions and accurate content beats a brief with 0 flags and 3 guesses baked in.
- If the ask is really a proposal/SOW request (new engagement, pricing, scope negotiation) rather than a creative brief for existing scope, say so and point to the `proposal-sow-generator` skill instead.
