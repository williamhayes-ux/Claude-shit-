---
name: invoice-retainer-tracker
description: Draft invoices, track retainer hours/budget burn, and maintain a billing status log for a client. Use when generating an invoice, checking retainer burn rate against hours or budget, or reviewing accounts receivable status. Triggers on "draft an invoice", "how much of the retainer is left", "retainer burn", "billing status", "what's outstanding on this client".
---

# Invoice & Retainer Tracker

## Purpose

Handles two related but distinct jobs: generating individual invoices for project/milestone billing, and tracking ongoing retainer burn so account managers know before the client does whether a retainer is running hot, on track, or underutilized.

This skill produces documents and tracking sheets — it does not connect to an actual accounting/payment system. For sending real invoices or reconciling payments, see `CONNECTORS.md` for the finance tools (Stripe, QuickBooks, Xero, Airwallex, etc.) that need to be connected separately.

## When to use

- A project milestone or monthly retainer needs an invoice drafted
- Someone needs to know retainer burn (hours or budget) to date
- Building/updating an AR (accounts receivable) status log across clients

## Inputs needed

- Client name, engagement type (project/fixed-fee vs. monthly retainer vs. time & materials)
- For invoices: what's being billed (milestone, deliverable, monthly retainer amount, hours at rate), invoice date, payment terms
- For retainer tracking: monthly retainer amount or hours allocation, hours/spend logged to date this period, team members who logged time

## Process

### Drafting an invoice
1. Use `references/invoice-template.md`.
2. Pull the amount/scope from the relevant SOW or retainer agreement — don't invent a number if it isn't stated; ask or flag `[CONFIRM AMOUNT]`.
3. Include the invoice number using the convention `[client-slug]-[YYYY-MM]-[sequence]`.
4. Save to `clients/<client-name>/00-admin/invoices/invoice-<number>.md`.

### Tracking retainer burn
1. Use `references/retainer-tracker-template.md`.
2. Calculate burn rate: (hours or spend to date) / (days elapsed in period) vs. (total allocation) / (total days in period). Flag if burn rate is pacing >15% over or under allocation.
3. Note which workstreams/team members are consuming the retainer, so overages can be traced to a cause, not just a number.
4. Update `clients/<client-name>/00-admin/retainer-tracker.md` — this should be a living document updated regularly, not regenerated from scratch each time.

## Notes

- Never mark an invoice as sent or paid unless told so explicitly — this skill drafts documents, it doesn't confirm real-world payment status.
- If retainer burn is trending to blow through the monthly allocation, flag it early enough for the account manager to have the scope conversation with the client before the client notices on their own.
