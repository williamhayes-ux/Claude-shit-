---
name: proposal-sow-generator
description: Generate a client proposal or statement of work (SOW) for a new engagement, project, or retainer - including scope, deliverables, timeline, pricing, and terms. Use when pitching new business, scoping a new project for an existing client, or converting a verbal agreement into a signable document. Triggers on "write a proposal", "draft an SOW", "scope this project", "put together pricing for".
---

# Client Proposal & SOW Generator

## Purpose

Produces two related but distinct documents:
- **Proposal**: sells the engagement — problem, approach, why us, indicative pricing. Used pre-close.
- **Statement of Work (SOW)**: locks the engagement — precise scope, deliverables, timeline, payment terms, assumptions/exclusions. Used post-close, often as a contract exhibit.

Don't conflate them. A proposal can be optimistic and persuasive; an SOW has to be precise enough to prevent scope creep and disputes later.

## When to use

- New business pitch needs a proposal
- An existing client wants a new project or an add-on to a retainer — needs an SOW
- A verbal "yes, let's do it" needs to become a document both sides can sign

## Inputs needed

- Client name, the problem/opportunity they're trying to solve
- Scope discussed so far (what's in, what's explicitly out)
- Pricing model: fixed fee, retainer, time & materials, or hybrid — and rate/amount if known
- Timeline expectations
- Payment terms if the agency has standard terms (e.g., 50% upfront / 50% on delivery, net 30)

Flag `[NEEDS INPUT]` for pricing or terms not yet decided — do not invent rates.

## Process

1. Determine which document is needed (proposal vs. SOW) — ask if ambiguous, since they have different tone and legal weight.
2. For a **proposal**, use `references/proposal-template.md`: lead with the client's problem in their language, not the agency's service menu. Keep pricing as a range or "starting at" unless a firm number was given.
3. For an **SOW**, use `references/sow-template.md`: be exhaustive about what's included and explicit about what's excluded (revision rounds, usage rights, rush fees, out-of-scope requests). Vague SOWs are where agencies lose margin.
4. Always include an assumptions/exclusions section in the SOW — this is the section that protects both the client's budget and the agency's time.
5. Save to `clients/<client-name>/00-admin/proposal-<slug>.md` or `sow-<slug>.md`.
6. Remind the user that this is a draft for internal/legal review — not a substitute for actual contract review on high-value engagements.

## Notes

- Revision rounds must be a number, not "reasonable revisions." Put "2 rounds of revisions included; additional rounds billed at $X/hour" or equivalent.
- If usage rights (where/how long content can run, whitelisting/paid media usage, buyouts) aren't addressed, flag it — this is a common source of disputes with video/film deliverables specifically.
