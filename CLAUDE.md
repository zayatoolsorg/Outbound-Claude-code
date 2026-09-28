# Zaya Outbound — Operating Manual for AI Agents

This repository is the outbound lead-generation and client-acquisition system for
**Zaya Productions** (https://www.zayaproductions.com/), a premium visual creative studio.

Read this file first. Then read the relevant file in `system/` before doing any task.

---

## 1. What this system is for

Find, research, qualify and prepare personalised outreach for a **small number of
highly relevant prospects**, globally. Quality over volume: 10 strong prospects beat
500 random companies.

The system **researches, analyses, drafts, organises and tracks**.
The founder **reviews and sends** every message personally.

## 2. Hard rules (non-negotiable)

1. **Never send anything.** No DMs, emails, connection requests, comments, likes or
   follows. Drafts only.
2. **Never fabricate.** Do not invent emails, names, job titles, revenue, funding,
   employee counts, budgets, campaigns, client relationships or social activity.
   If something cannot be verified, write `Not verified.`
3. **Separate FACT / OBSERVATION / INFERENCE** in every research and audit file.
   - FACT: directly observed or reliably verified (include the source).
   - OBSERVATION: a creative judgement about their actual content.
   - INFERENCE: a possible opportunity derived from facts and observations.
   Never present an inference as a fact, in files or in outreach.
4. **Public, professional information only.** No private data, no bypassing logins,
   paywalls or platform restrictions, no scraping at scale.
5. **Do not overstate Zaya's experience.** Claim only what `system/proof-library.md`
   allows. Block Agency (an independent OOH agency headquartered in Dubai) is the one
   full case study: identity, website (designed and built), social post and motion
   system, and guidelines. It was **not** OOH campaigns or video production.
   Other proof is labelled film/motion work for named clients (e.g. Captain Fresh,
   Aspora, Groww, Equitas), with no results shown. Never write "global client
   portfolio", "international network", "clients across the world" or similar.
6. **Never guess URLs.** The only confirmed Zaya link is https://www.zayaproductions.com/.
   Never construct deep links to case studies or work pieces.
7. **Do not start prospecting, research or outreach unless the founder asks for it.**

## 3. Positioning in one paragraph

Zaya is a premium, selective, international-minded visual studio: social content,
video production, post-production, motion design, 3D, brand films, performance ad
creative, editing, visual storytelling, creative direction and production. It is
**not** a generic social media agency, a cheap outsourcing shop, a content factory or
a freelancer chasing any work. Every file and draft should sound confident,
refined and visually literate, never desperate or salesy.

## 4. Directory map

```
CLAUDE.md                 ← you are here
leads/
  master.csv              ← single source of truth for every lead (one row per company)
  new/                    ← raw candidate lists from discovery runs (before research)
  qualified/              ← one lead card per qualified prospect: <slug>.md
  rejected/               ← one short note per rejected prospect: <slug>.md (reason = learning data)
research/                 ← deep research files: <slug>.md
audits/                   ← concise creative audits: <slug>.md
outreach/
  instagram/              ← DM drafts: <slug>.md
  linkedin/               ← LinkedIn drafts: <slug>.md
  email/                  ← email drafts: <slug>.md
followups/                ← follow-up drafts and schedule: <slug>.md
system/
  icp.md                  ← who we target and why (Lane A brands, Lane B agencies)
  qualification.md        ← Creative Opportunity Index (scoring + tiers)
  outreach.md             ← outreach philosophy, tone, channel rules, follow-ups
  proof-library.md        ← Zaya case studies and when to use them
  proof-assets/           ← source screenshots for each case study (evidence, not for sending)
  learnings.md            ← what's working, what isn't; updated over time
```

### Naming convention

- **Slug** = lowercase company name, hyphenated, ASCII only, e.g. `block-agency`,
  `maison-example`. Use the same slug in every folder and in the `Lead ID` column.
- Discovery batch files in `leads/new/`: `YYYY-MM-DD-<lane>-<market-or-theme>.md`
  e.g. `2026-10-01-agencies-uae-ooh.md`.
- Dates are always ISO: `YYYY-MM-DD`.

## 5. Lead database: `leads/master.csv`

One row per company. Update the row whenever a stage changes. Multi-value cells
use ` | ` as a separator. Wrap any cell that contains commas in double quotes.

| Column | Meaning |
|---|---|
| Lead ID | Slug (see naming convention). Primary key; check it before adding a lead to avoid duplicates. |
| Company | Official company name. |
| Website | Official URL (verified). |
| Instagram | Official handle URL, or `Not verified.` |
| LinkedIn | Official company page URL, or `Not verified.` |
| Country / City | HQ or the relevant market office. |
| Industry | e.g. Skincare, OOH agency, Hospitality. |
| Prospect Type | `Lane A – Brand` or `Lane B – Agency`. |
| Decision Maker | Name, **only** if publicly verifiable; otherwise `Not verified.` |
| Decision Maker Role | Title as publicly listed. |
| Contact Method | Recommended first channel + handle, e.g. `Instagram DM @brand`, `LinkedIn – <name>`, `Email – publicly listed address`. Never guessed emails. |
| Evidence | Short list of facts with sources (URLs). |
| Creative Observations | 1–3 observations on their actual content. |
| Creative Opportunity | 1–2 sentence inference: the specific gap or project Zaya could address. |
| Opportunity Index | Tier + score + confidence, e.g. `A · 21 · High`. See `system/qualification.md`. |
| Relevant Proof | Case study ID(s) from `system/proof-library.md`, or `None`. |
| Proof Relevance | `High` / `Medium` / `Low` / `None`, plus a few words on why. |
| Recommended Portfolio Piece | The single best piece to show, plus when: `First message` / `After reply` / `Don't use`. |
| Status | See status list below. |
| Date Added / Date Contacted / Follow-up Date | ISO dates. `Date Contacted` is filled **by the founder** (or on their instruction) after they send. |
| Response | `None yet` / `Positive` / `Neutral` / `Not now` / `Negative` / `Referred`, plus a short summary. |
| Notes | Anything else. |

### Status values (in order)

`New` → `Researching` → `Qualified` / `Rejected` / `Parked` → `Drafted` →
`Contacted` → `Follow-up 1` → `Follow-up 2` → `Replied` → `Call booked` →
`Proposal` → `Won` / `Lost` / `Closed – no response`

- `Parked`: good fit, but the timing or access isn't right. Revisit later.
- `Contacted` and later are only set after the founder confirms they sent the message.

## 6. Workflow

```
1. DISCOVER   → leads/new/<batch>.md          (candidate list, light evidence only)
2. SCREEN     → quick pass on ICP + gates      → add row to master.csv (Status: New)
3. RESEARCH   → research/<slug>.md             (Status: Researching)
4. QUALIFY    → score the Creative Opportunity Index
                ├─ Qualified → leads/qualified/<slug>.md
                ├─ Parked    → note in master.csv
                └─ Rejected  → leads/rejected/<slug>.md (reason)
5. AUDIT      → audits/<slug>.md               (concise creative audit)
6. PROOF      → match case study via system/proof-library.md
7. DRAFT      → outreach/<channel>/<slug>.md   (Status: Drafted)
8. FOUNDER REVIEWS AND SENDS                    (founder sets Status: Contacted)
9. FOLLOW UP  → followups/<slug>.md            (drafts only, on schedule)
10. LEARN     → system/learnings.md            (patterns from responses and rejections)
```

Stop at the end of any stage the founder asked for. Don't run ahead to later stages.

## 7. File templates

### Research file: `research/<slug>.md`

```markdown
# <Company> — Research
Lead ID: <slug> · Lane: A/B · Researched: YYYY-MM-DD

## Snapshot
- Website / Instagram / LinkedIn:
- Location(s):
- What they do (1–2 lines):
- Positioning (how they present themselves):

## Facts (with sources)
- ... [source URL]

## Signals (from system/icp.md §Signals)
- ... [source URL]

## Visual communication — observations
- Website:
- Social (formats, cadence, quality, consistency):
- Video / motion / 3D:
- Advertising (if publicly visible, e.g. Meta Ad Library):

## Inferences — possible creative opportunities
- ...

## Decision-maker (public professional info only)
- Name / Role / Source — or `Not verified.`

## Open questions / not verified
- ...
```

### Creative audit: `audits/<slug>.md`

Keep it to roughly one screen. It's for internal use and for later conversations,
not for pasting into a first message.

```markdown
# <Company> — Creative Audit
## The gap in one sentence
## What's working (be honest)
## 3 specific observations (each labelled OBSERVATION, linked to a FACT)
## The opportunity (INFERENCE) — what Zaya could make
## Relevant Zaya capability
## Proof match — case study, relevance, timing
## Outreach angle — the one thing worth saying first
```

### Outreach draft: `outreach/<channel>/<slug>.md`

```markdown
# <Company> — <Channel> draft
To: <name/handle or "Not verified.">   Angle: <one line>
Proof used: <case study ID / none>   Status: Draft — founder to review

<message>

---
Why this angle: <1–2 lines referencing the audit>
Facts the message relies on: <list with sources>
```

## 8. Future commands (not implemented yet)

These will be built as `.claude/commands/*.md` once the foundation is approved.
Each must follow the rules and templates above.

| Command | Does | Writes to |
|---|---|---|
| `/find-brands [market] [industry]` | Discover a small batch (5–15) of Lane A candidates | `leads/new/`, `master.csv` |
| `/find-agencies [market] [type]` | Discover a small batch of Lane B candidates | `leads/new/`, `master.csv` |
| `/research [company]` | Deep research using public sources | `research/`, `master.csv` |
| `/audit [company]` | Qualify + creative audit + proof match | `audits/`, `leads/qualified|rejected/`, `master.csv` |
| `/outreach [company]` | Draft IG / LinkedIn / email variants | `outreach/*/`, `master.csv` |
| `/followups` | List follow-ups due today or overdue; draft them | `followups/` |
| `/pipeline` | Summarise `master.csv` by status, tier, lane and market | none (read-only) |
| `/learn` | Analyse outcomes and update learnings | `system/learnings.md` |

## 9. Open items (ask the founder; don't assume)

Settled (2026-09-28): Block case study screenshots are authoritative; no deep link,
use the homepage. Zaya built the Block website. Competitors of Block may be approached.

Still open:
- Clients for work pieces PW-07 (Naga), PW-08 (Showcase) and PW-09 (Brand Film).
- Zaya's scope on each work piece; any results for any project.
- Proof for luxury, fashion, hospitality, 3D and performance creative: none yet.
