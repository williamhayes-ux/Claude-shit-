# Agency Operations Backbone

This repo is the operational backbone for a hybrid marketing/creative agency and film/video
production house. It's not a codebase — it's the structured place Claude Code works from to
help run the business: creative briefs, production docs, client proposals, content calendars,
invoicing/retainer tracking, and status reporting, executed through role-based subagents.

## How this repo is organized

```
CLAUDE.md              — this file
CONNECTORS.md          — recommended claude.ai connectors to attach manually (Slack, Notion, etc.)
.claude/
  settings.json         — enabled plugins + marketplace config (project-scoped, versioned)
  skills/               — recurring-work skills (see "Skills" below)
  agents/               — team-role subagents (see "Roles" below)
clients/
  _template/            — canonical folder structure for a new client/project (copy, don't edit in place)
  <client-slug>/        — one folder per client (see "Client project conventions")
```

## Roles (subagents in `.claude/agents/`)

Delegate to a specific role instead of a generic assistant when the ask maps cleanly to one:

| Role | File | Owns |
|------|------|------|
| Creative Director | `creative-director.md` | Concepting, brief quality, creative feedback, creative quality bar |
| Producer | `producer.md` | Shoot logistics, shot lists, call sheets, schedules, budgets, production risk |
| Editor | `editor.md` | Post-production, feedback consolidation, revision planning |
| Project/Account Manager | `account-manager.md` | Client relationship, proposals/SOWs, status reporting, scope management |
| Social Media Manager | `social-media-manager.md` | Content calendars, platform strategy, caption direction |
| Finance/Ops | `finance-ops.md` | Invoices, retainer burn tracking, budget-vs-actuals |

Each agent file documents its own scope, what it explicitly hands off, tone, and working
conventions. When a request spans roles (e.g., "a client wants to add a video to their
retainer" touches Account Manager, Producer, and Finance/Ops), either delegate to the primary
owner and let them note the handoffs, or work through it step by step yourself using the same
scope boundaries.

## Skills (`.claude/skills/`)

Skills are the reusable "how we do this recurring thing" playbooks. Agents use these; so can
you directly without going through an agent persona.

| Skill | Produces |
|-------|----------|
| `creative-brief-generator` | Structured creative brief from a raw client ask |
| `production-docs` | Shot lists, call sheets, production schedules, budgets |
| `proposal-sow-generator` | Client proposals and Statements of Work |
| `content-calendar-builder` | Social/content calendars |
| `invoice-retainer-tracker` | Invoices and retainer burn tracking |
| `post-production-review-tracker` | Consolidated, conflict-flagged feedback across review rounds |
| `new-project-setup` | Scaffolds a new client/project folder from `clients/_template/` |
| `status-report-generator` | One-page client/internal status updates |
| `meeting-notes-action-tracker` | Structured meeting notes with owned, dated action items |

Plus two installed plugins (project-scoped, see `.claude/settings.json`):
- **`claude-md-management`** — audits/improves this file and any nested `CLAUDE.md` files over time
- **`project-artifact`** — publishes a shareable, continuously-refreshable client/program status
  page via the built-in Artifact tool, for programs too large for a one-page status report

Every skill's `SKILL.md` follows the same discipline: flag missing information explicitly
(`[NEEDS CLIENT INPUT]`, `[CONFIRM]`, `[ESTIMATE — pending quote]`) rather than inventing
plausible-sounding numbers, dates, or contact details. This matters most on call sheets
(safety-relevant fields) and financial documents (never fabricate a rate or a payment status).

## Client project conventions

**Folder naming:** `clients/<client-slug>/`, lowercase and hyphenated (`acme-beverages`, not
`Acme Beverages Inc`). A client with multiple concurrent distinct engagements nests by project:
`clients/<client-slug>/<project-slug>/`.

**File naming:** `<doc-type>-<descriptive-slug>-<YYYY-MM-DD or version>.md`, e.g.
`brief-summer-launch.md`, `call-sheet-day1-2026-08-03.md`, `invoice-acme-2026-08-001.md`.
No spaces or special characters — hyphens only.

**New project setup:** always run the `new-project-setup` skill before creating any brief,
production doc, or invoice for a new client or a new distinct engagement. It copies the
`clients/_template/` structure (including the `.gitkeep`-anchored subfolders and starter
`README.md`) so every project is discoverable the same way. Check `clients/` for an existing
client folder before assuming a new ask is net-new — most new asks are a new project *under*
an existing client, not a new top-level client.

**Standard structure inside a project** (mirrors `clients/_template/`):
```
00-admin/               contracts, proposals, SOWs, invoices/, retainer tracker
01-brief-strategy/      creative briefs, meeting notes, strategy docs
02-production/          shot-lists/, call-sheets/, schedules/, budgets/
03-content-calendar/    social/content calendars
04-assets-deliverables/ final deliverables or links to where they live
05-post-production/     feedback/review round tracking
README.md               one-page project snapshot — keep this current
```

It's fine to skip subfolders that genuinely don't apply to an engagement (e.g., no
`02-production/` for a project with no video component) — don't force empty structure for
its own sake.

## Plugins & marketplaces

The `claude-plugins-official` marketplace (`anthropics/claude-plugins-official`) is registered
in `.claude/settings.json`. Only plugins that work without an external account/API key/OAuth
are installed directly here — anything that requires connecting a real service (Slack, Notion,
Asana, Adobe, Canva, Stripe, etc.) is deliberately *not* installed as a plugin. Those are
listed in `CONNECTORS.md` instead, to be attached by a human from the claude.ai session UI,
since this repo has no access to your credentials and shouldn't try to acquire any.

If you're evaluating whether to add a new plugin: check whether it bundles an MCP server that
needs a login/API key. If it does, it belongs in `CONNECTORS.md`, not `.claude/settings.json`.

## Working principles for anyone (human or agent) operating in this repo

1. **Never fabricate client-facing facts.** Budgets, deadlines, contact info, legal terms,
   payment status — flag what's missing, don't guess plausibly.
2. **Every action item needs an owner and a date**, or it gets flagged as missing one — see
   `meeting-notes-action-tracker`.
3. **Surface risk early, not at the deadline.** Retainer burn, unrealistic timelines, and scope
   creep should be flagged the moment they're visible, in the relevant role's tone (Finance/Ops
   for burn, Producer for schedule, Account Manager for scope).
4. **One project = one folder**, following the naming conventions above, so both agents and
   humans can navigate the repo without a lookup table.
5. **Route requests to the right role/skill** rather than defaulting to a generic response —
   that's the point of the role and skill structure above.
