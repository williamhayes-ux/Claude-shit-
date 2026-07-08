---
name: new-project-setup
description: Scaffold a new client or project folder using the agency's standard structure and naming conventions. Use when starting a new client engagement or a new project for an existing client, before any briefs/production docs/invoices are created. Triggers on "set up a new project", "new client", "start a new engagement for", "create the project folder for".
---

# New Project Setup

## Purpose

Every client project should use the same folder structure so skills, agents, and humans can find things without guessing. This skill scaffolds a new project folder correctly the first time, instead of every project inventing its own layout.

## When to use

- Onboarding a new client
- Starting a new, distinct project for an existing client (treat each distinct engagement as its own project folder, not a subfolder buried in an old one)

## Naming conventions

- Client folder: `clients/<client-slug>/` — slug is lowercase, hyphenated (e.g. `acme-beverages`, not `Acme Beverages Inc`)
- If a client has multiple concurrent distinct projects, nest by project: `clients/<client-slug>/<project-slug>/`
- File naming inside a project: `<doc-type>-<descriptive-slug>-<YYYY-MM-DD or version>.md` (e.g. `brief-summer-launch.md`, `call-sheet-day1-2026-08-03.md`, `invoice-acme-2026-08-001.md`)
- Never use spaces or special characters in filenames; use hyphens.

## Process

1. Confirm the client name and, if applicable, a specific project name distinct from other work for that client.
2. Create the folder structure by copying `clients/_template/` (structure, `.gitkeep` placeholders, and `README.md` starter) to `clients/<client-slug>/`:
   ```
   clients/<client-slug>/
     00-admin/              # contracts, SOWs, proposals, invoices, retainer tracker
       invoices/
     01-brief-strategy/     # creative briefs, strategy docs
     02-production/         # video/film production docs
       shot-lists/
       call-sheets/
       schedules/
       budgets/
     03-content-calendar/   # social/content calendars
     04-assets-deliverables/# final deliverables, links to shared drives
     05-post-production/    # feedback/review tracking
     README.md              # one-page project snapshot (see below)
   ```
3. Populate `README.md` in the new project folder with: client name, primary contact, engagement type (project/retainer), key dates, and a link/pointer to the SOW once it exists.
4. Report back the created path and remind the user which skill to use next (creative-brief-generator for a new brief, proposal-sow-generator if there's no signed SOW yet).

## Notes

- Don't create a new client folder for what's actually a new project under an existing client relationship — check `clients/` first for an existing folder before assuming this is net-new.
- If the engagement doesn't cleanly fit the template (e.g., a one-off asset with no production phase), it's fine to skip unused subfolders — don't force empty folders into version control for the sake of completeness.
