---
name: customer-success-manager
description: Score retainer client health, flag churn/non-renewal risk, and identify expansion opportunities on existing accounts. Use when checking whether a retainer client relationship is healthy, assessing the risk a client doesn't renew, or spotting where an existing client could reasonably be sold more work. Triggers on "is this account healthy", "are we at risk of losing this client", "could we upsell this client", "renewal risk check".
---

# Customer Success (Retainer Client Health)

> Adapted from the third-party [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills)
> repo (MIT License, © Alireza Rezvani), which wrote this for SaaS customer success teams scoring
> product-usage telemetry (login frequency, feature adoption, ARR). An agency has no usage telemetry on a
> client relationship, so this version keeps the four-dimension health-scoring *structure* but replaces the
> SaaS inputs with signals an account team actually has: engagement, delivery/satisfaction, commercial, and
> relationship health. The original Python scripts (`health_score_calculator.py`, `churn_risk_analyzer.py`,
> `expansion_opportunity_scorer.py`) were **not imported** — they're built around ARR/usage JSON inputs that
> don't exist for this business. Score manually using the dimensions below.

## Purpose

Gives the Account Manager a structured way to answer "is this retainer client actually healthy" beyond gut
feel — and to catch a quietly deteriorating relationship before it becomes a non-renewal, or a strong
relationship worth proposing more work into.

## When to use

- Ahead of a retainer renewal conversation
- Periodic (quarterly) health check across the client roster
- Something feels off with a client relationship and it's worth structuring why

## Health scoring dimensions (adapted from the source's usage/engagement/support/relationship split)

Score each dimension Green / Yellow / Red and note the evidence — don't just assign a color without a
reason:

1. **Engagement** — Is the client actively engaged (responsive to requests, attends status calls, gives
   timely feedback/approvals) or is engagement thinning (slow replies, skipped calls, feedback rounds
   dragging)?
2. **Delivery & satisfaction** — Is work landing well (per `post-production-review-tracker` history and
   direct client sentiment) or is there a pattern of dissatisfaction, heavy revision rounds, or unresolved
   complaints?
3. **Commercial** — Is retainer burn healthy per `invoice-retainer-tracker` (using close to what's paid for,
   not wildly over or under), and is billing current (no aging unpaid invoices)?
4. **Relationship** — Is the agency's day-to-day contact still the right one, still empowered, still an
   advocate internally at the client? A key contact leaving or getting reorganized out of the relationship
   is one of the biggest real churn signals — flag it explicitly if it's happened.

Roll up to an overall Green/Yellow/Red — if any single dimension is Red, the overall score shouldn't be
Green even if the others look fine; a real risk in one area is a real risk.

## Churn/non-renewal risk signals to check explicitly

- Declining engagement or a downgraded/paused workstream
- A pattern of dissatisfaction on recent deliverables
- Retainer consistently underused (client not getting value, may not see the point of renewing) — as
  distinct from overused (different risk: margin, not renewal)
- Key contact change
- Client has gone quiet on a renewal/expansion conversation that was previously moving

## Expansion opportunities to look for

- A workstream currently outside the retainer that keeps coming up informally (client asking for "one more
  thing" repeatedly — that's a signal there's appetite for more scope, not just a favor to keep granting for
  free)
- Positive sentiment plus underused budget — room to propose more ambitious work at the same spend before
  proposing more spend
- A new business need mentioned by the client that maps to a service the agency offers but isn't currently
  contracted

Use `references/health-scoring-framework.md` and `references/cs-playbooks.md` for the underlying methodology
(SaaS-flavored — read for structure) and `assets/qbr_template.md` /
`assets/executive_business_review_template.md` as a loose starting structure for a client-facing quarterly
review, reworked with agency language rather than product-usage language.

## Notes

- This is diagnostic, not client-facing — the output is for the Account Manager/agency leadership, not to be
  sent to the client as-is.
- A Yellow or Red finding should turn into an actual action (a check-in call, a scope conversation, an
  internal delivery fix) — a health score that doesn't change behavior isn't useful.
