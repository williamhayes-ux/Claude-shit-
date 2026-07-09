---
name: contract-and-proposal-writer
description: Generate jurisdiction-aware business documents - freelance/consulting contracts, NDAs, and Master Service Agreements (MSAs) - covering US (Delaware), EU (GDPR), UK, and DACH (German law) frameworks. Not a substitute for legal counsel. Use when a client relationship needs an NDA before sharing sensitive material, a contract/MSA beyond what proposal-sow-generator covers, or jurisdiction-specific legal clause guidance. Triggers on "draft an NDA", "we need an MSA", "what clauses does GDPR require", "jurisdiction for this contract".
---

# Contract & Proposal Writer

> Sourced from the third-party [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills)
> repo (MIT License, © Alireza Rezvani), imported with minimal changes. For this agency's proposals and
> SOWs, prefer `proposal-sow-generator` — it's tailored to the creative/production engagement model. Reach
> for this skill specifically for **NDAs, MSAs, and jurisdiction-specific clause guidance** that
> `proposal-sow-generator` doesn't cover.

## Overview

Produces jurisdiction-aware business documents — freelance/consulting contracts, NDAs, and MSAs — in
structured Markdown with docx conversion guidance. Coverage spans US (Delaware), EU (GDPR), UK, and DACH
(German law) frameworks.

**Disclaimer:** These templates are not legal counsel substitutes. Treat them as professional starting
points; consult an attorney for high-value or complex arrangements — same caveat as
`proposal-sow-generator`.

## Core capabilities

- Freelance/consulting contracts (fixed-price & hourly, and monthly retainer models)
- Mutual and one-way NDAs
- Master Service Agreements (MSA)
- Jurisdiction-specific clauses addressing US, EU, UK, and DACH requirements
- GDPR Data Processing Addenda for EU/DACH engagements handling personal data

## When to use

- A client needs an NDA before sharing sensitive creative concepts, footage, or unreleased campaign material
- An ongoing multi-project client relationship needs an MSA as an umbrella agreement (with individual SOWs
  as exhibits under it — pair with `proposal-sow-generator` for those SOWs)
- A contract needs to address a specific jurisdiction's requirements (an EU/DACH client, a UK client
  post-Brexit, etc.)

## Workflow

1. **Requirements gathering:** document type, jurisdiction, engagement structure, party information, scope
   summary, financial terms, timeline, and any special requirements (IP assignment, subcontracting).
2. **Template selection:** choose the template matching the engagement (consulting retainer, project
   contract, NDA, MSA) and jurisdiction.
3. **Generation & completion:** fill every bracketed placeholder; flag any missing required data rather than
   guessing — same discipline as every other skill in this repo (`[NEEDS CLIENT INPUT]`, `[CONFIRM]`).
4. **DOCX conversion (optional):** `pandoc contract.md -o contract.docx --number-sections -V fontsize=11pt`

## Key clauses reference

Customizable terms include payment structures (Net-30, milestone-based, monthly retainer), IP ownership
frameworks, liability caps, termination conditions, confidentiality periods, warranty disclaimers, and
dispute resolution mechanisms. For video/creative work specifically, make sure IP ownership and usage-rights
language matches what `proposal-sow-generator`'s SOW template captures in its "Usage rights & ownership"
section — don't let the two documents contradict each other on the same engagement.

## Jurisdiction-specific guidance

**US (Delaware):** Applies work-for-hire doctrine; uses AAA Commercial Rules for arbitration; enforces
non-competes within reasonable bounds.

**EU (GDPR):** Mandates Data Processing Addenda for personal data handling; some member states require
separate written IP deeds; employs ICC arbitration.

**UK (post-Brexit):** References English law, Patents Act 1977, CDPA 1988, UK GDPR equivalent; uses LCIA
Rules for arbitration.

**DACH (Germany/Austria/Switzerland):** Governed by BGB; written form required for certain clauses; authors
retain moral rights; explicit *Nutzungsrechte* transfer necessary; non-competes limited to 2 years with
required compensation; DSGVO mandatory for personal data.

## Common pitfalls to avoid

- Inadequate IP assignment language for EU markets
- Vague acceptance criteria enabling scope disputes
- Absent change order protocols facilitating scope creep (see `proposal-sow-generator`'s change order section)
- Misaligned governing law and jurisdiction selections
- Missing liability limitations
- Verbal contract modifications lacking written documentation

## Best practices

- Use milestone payments for projects exceeding $10K
- Include Data Processing Agreements when handling personal data
- Add written form clauses (*Schriftformklausel*) for DACH projects
- Incorporate force majeure provisions for engagements exceeding 3 months
- Define response time SLAs for retainer arrangements
- Maintain template versions with change tracking
- Conduct annual reviews reflecting evolving regulatory landscapes

## Notes

- Route through legal/leadership review before sending, same as any SOW — this generates a strong draft,
  not a signed-off legal document.
- Save output to `clients/<client-name>/00-admin/` alongside proposals/SOWs.
