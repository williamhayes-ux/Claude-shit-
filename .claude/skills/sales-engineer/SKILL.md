---
name: sales-engineer
description: Analyze a formal RFP/RFI from a prospective client for coverage gaps against agency capabilities, and build competitive positioning against other agencies pitching the same business. Use when a formal RFP/RFI has come in from a prospective client (common with larger client procurement processes) or when preparing competitive positioning for a new-business pitch. Triggers on "we got an RFP from", "should we bid on this", "how do we compare to the other agencies pitching this", "prep for the pitch".
---

# Sales Engineer (Agency RFP / Pitch Positioning)

> Adapted from the third-party [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills)
> repo (MIT License, © Alireza Rezvani), which wrote this for software pre-sales engineering (RFP
> responses for software products, technical demos, proof-of-concept engagements). Most of that doesn't
> apply to a creative/production agency — there's no product to demo or POC. What does carry over: **RFP
> coverage-gap analysis** and **competitive positioning**, which some agencies genuinely encounter when a
> larger client runs a formal procurement/RFP process for creative or production services. The original
> Python scripts (`rfp_response_analyzer.py`, `competitive_matrix_builder.py`, `poc_planner.py`) were
> **not imported** — they're built around software feature/requirement scoring, not agency capabilities.
> Treat the sections below as the workflow to reason through directly, not automation to run.

## When to use

- A prospective (or existing) client has sent a formal RFP/RFI for creative, content, or production
  services and the agency needs to decide whether to respond and how
- A pitch is competitive (the client is evaluating multiple agencies) and needs explicit positioning against
  what's known about the competition

## When NOT to use

- A normal, non-RFP new client ask — that's `proposal-sow-generator`
- Anything involving a technical product demo or proof-of-concept — not applicable to this business

## Process

### RFP coverage-gap analysis (bid / no-bid)

1. List every requirement in the RFP as its own line item, categorized by how the client weighted it if
   stated (must-have / should-have / nice-to-have) — if unweighted, use judgment but flag the assumption.
2. For each requirement, assess the agency's actual coverage: **Full** (clearly can deliver), **Partial**
   (can deliver with a workaround or partner), **Planned** (would need to build out a new capability), or
   **Gap** (can't credibly deliver).
3. Roll up to a bid / no-bid read, adapted from the source material's software-vendor thresholds — treat
   these as a sanity check, not a rule: strong bid case if most requirements are Full/Partial coverage and
   there are no more than 2-3 must-have gaps; a weak case with several must-have gaps is worth flagging to
   leadership before committing real pitch hours.
4. Use `references/rfp-response-guide.md` for the underlying methodology (written for software RFPs — read
   for structure, apply the judgment above for agency services).

### Competitive positioning

1. List what's actually known about competing agencies in the pitch (past work, size, specialty, price
   point) — don't invent detail that isn't known; mark unknowns rather than guessing at a competitor's
   capabilities.
2. Identify genuine differentiators (a specific creative point of view, category experience, production
   capability the agency has that others plausibly don't) and genuine vulnerabilities (where a competitor is
   plausibly stronger) — an honest list is more useful than a one-sided one.
3. Use `references/competitive-positioning-framework.md` for the underlying framework and
   `assets/technical_proposal_template.md` / `assets/demo_script_template.md` as loose structural references
   for a pitch deck's technical/capabilities section — the software-specific language in them needs
   reworking for a creative pitch, they're a skeleton, not a fill-in-the-blank template here.

## Notes

- This is a heavier-weight skill than `proposal-sow-generator` — reserve it for genuinely competitive,
  formal-process pitches, not every new client conversation.
- A "no-bid" recommendation, clearly reasoned, is a legitimate and often valuable output — don't default to
  recommending every RFP be pursued.
