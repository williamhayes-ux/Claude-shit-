# Connectors — What's On You To Attach

Everything in `.claude/skills/` and `.claude/agents/` works today with no external
accounts — they read/write files in this repo. Real operational leverage comes from
connecting the actual tools your team and clients live in. I can't do that from inside
this sandbox: connectors require OAuth login or a paid account, and I don't have (and
shouldn't try to get) your credentials.

Below is what's already connected to this session, what's available in your org's
connector directory but not yet turned on, and what's worth requesting if it isn't
there. Attach these from the connector settings in the claude.ai session UI — it's a
couple of clicks per connector.

## Already connected (nothing to do)

| Connector | Why it matters here |
|-----------|----------------------|
| **Gmail** | Client email — pulling raw client asks straight into `creative-brief-generator`, drafting replies from status reports |
| **Google Drive** | Asset/document storage — natural home for `04-assets-deliverables/` links and shared brand guideline docs |
| **ClickUp** | Project/task management — the real system of record for the tasks these skills generate (briefs, action items, production milestones) |

These are connected at the org level but you should confirm they're **enabled for this
specific chat/session** (toggle in the connector panel) whenever you want to use them —
`enabledInChat` can be off even when the org-level connection is live.

## In your org's connector directory — recommended to turn on, in priority order

1. **HubSpot** — if this is your CRM (or you want one), this is the highest-leverage
   connector for the Account Manager role: client contact history, deal stage, and
   pipeline context feed directly into proposals, status reports, and scope
   conversations instead of living in someone's head.
2. **Canva** — directly supports the Social Media Manager and Creative Director roles:
   pulling/pushing design assets for content calendar items and campaign creative
   without leaving the conversation.
3. **Figma** — same rationale as Canva for teams doing brand/web design work; connect
   whichever of the two (or both) matches your actual design stack.
4. **Notion** — if any team or client documentation lives in Notion, connecting it lets
   briefs, SOWs, and status reports pull real context instead of you re-pasting it.
5. **Webflow** or **WordPress.com** — connect whichever your clients' sites actually run
   on, if the agency does web/landing page work alongside campaigns.
6. **Asana** or **monday.com** — only if a specific client or team actually runs PM
   there instead of ClickUp. Don't turn on redundant PM tools for their own sake.

Lower priority for this business (skip unless you have a specific need): **Atlassian**
(Jira/Confluence — dev-team oriented), **Linear** (software issue tracking), **Intercom**
(customer support inbox), **Box** (redundant with Google Drive unless a client mandates
it), **n8n** (workflow automation — powerful but adds complexity; revisit once the core
connectors are in use and you find a repetitive cross-tool task worth automating).

## Not in your org's directory yet — worth adding if relevant

I couldn't query live availability for these from the sandbox, but they're the connectors
that would most directly extend what's built here. Search for them by name in the
claude.ai connector directory:

| Connector | Why | Maps to |
|-----------|-----|---------|
| **Slack** | Where client and internal conversations actually happen day to day — huge unlock for `meeting-notes-action-tracker` and status updates | Account Manager |
| **Stripe / QuickBooks / Xero** (whichever you actually bill through) | Turns `invoice-retainer-tracker`'s drafts into real sent invoices and real payment status instead of markdown-only tracking | Finance/Ops |
| **Frame.io or Vimeo Review** | Purpose-built video review/timestamped-comment tools — would make `post-production-review-tracker` pull real client timestamped notes instead of you transcribing them from email | Editor |
| **Adobe (Creative Cloud)** | If your team works in Premiere/After Effects/Photoshop, Adobe's official plugin/connector lets Claude assist directly in that workflow | Creative Director / Editor |
| **Zoom** or **Google Calendar** | Meeting recordings/transcripts and scheduling context feed `meeting-notes-action-tracker` and production scheduling directly | Producer / Account Manager |

## What I deliberately did NOT install as a Claude Code plugin

The `claude-plugins-official` marketplace has plugins for several of the tools above
(Notion, Asana, Airtable, Box, Slack, Stripe, Canva, Figma, monday.com CRM, Airwallex,
etc.). I skipped installing all of them, per the ground rule for this task: any plugin
that bundles an MCP server requiring your login or API key isn't mine to authorize.
Installing the plugin wouldn't have made it usable anyway without you connecting the
underlying account — so the actionable version of "get these working" is this file, not
a plugin install. The two plugins I did install (`claude-md-management`,
`project-artifact`) work with zero external accounts.
