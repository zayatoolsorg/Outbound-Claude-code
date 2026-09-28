# Qualification — Creative Opportunity Index (COI)

The **Creative Opportunity Index** is an internal tool for deciding **who to
approach first**. It is **not** a measure of how good a company is, and it is never
shared with prospects.

It's deliberately coarse. Scores exist to force a structured judgement and
make prospects comparable. Don't treat a 17 as meaningfully different from an 18.

---

## Step 1 — Gates (pass/fail)

A prospect must pass **all** gates before it is scored. If any gate fails, it's
`Rejected` (or `Parked` if the failure is temporary). Record the reason in
`leads/rejected/<slug>.md`.

| Gate | Pass when |
|---|---|
| G1 Verifiable | Company, website and official channels are real and current |
| G2 Visual relevance | Their business benefits from premium visual communication |
| G3 Active | Some evidence of marketing activity in roughly the last 6 months |
| G4 Plausible buyer | Nothing in the evidence suggests they can't buy premium creative |
| G5 No conflict | No known conflict with an existing Zaya client (flag doubts to the founder) |
| G6 Fit with positioning | Approaching them wouldn't make Zaya look cheap, generic or desperate |

---

## Step 2 — Score eight factors (0–3 each)

| # | Factor | 0 | 1 | 2 | 3 |
|---|---|---|---|---|---|
| F1 | **Relevance to Zaya** (industry/lane fit) | Off-profile | Loose fit | Good fit | Core ICP |
| F2 | **Creative gap** — Lane A: gap between positioning and execution. Lane B: need for specialist execution capacity | None visible | Minor / generic | Clear, specific | Obvious and significant |
| F3 | **Marketing momentum** (signals from `icp.md` §5) | None | One weak signal | Several signals | Strong, recent, multiple |
| F4 | **Ability to buy premium creative** (**evidence only**) | Evidence against | Unclear | Some indicators | Strong indicators |
| F5 | **Capability match** (does the need map to video, motion, 3D, post, production?) | No | Partly | Clearly | Squarely in Zaya's strengths |
| F6 | **Opportunity specificity** (can we name a concrete thing Zaya would make?) | Vague | Generic idea | Specific idea | Specific, timely idea (tied to a launch or campaign) |
| F7 | **Decision-maker accessibility** | No verified person or channel | Generic channel only | Verified person or active DM channel | Verified relevant person with a reachable channel |
| F8 | **Proof match** (see `proof-library.md`) | None | Low | Medium | High |

**Weighting:** F2 (creative gap) counts **double**, because it's the core of the
Zaya thesis.

**Max score:** 7 factors × 3 + F2 × 6 = **27**

Guidance:
- F4 must be based on observable indicators (e.g. premium pricing, multiple
  locations, visible paid media, large team on LinkedIn, press coverage). If there's
  no evidence, score 1 (unclear), not 0.
- A score of 0 on F7 doesn't reject a lead. It usually means `Parked` until a
  channel is found.
- A score of 0 on F8 is fine. Many good prospects have no proof match yet.

---

## Step 3 — Tier

| Tier | Score | Meaning | Action |
|---|---|---|---|
| **A** | 20–27 | Strong, specific, timely | Full audit + outreach drafts |
| **B** | 14–19 | Good, but something is weaker | Audit; draft if the angle is strong |
| **C** | 9–13 | Marginal | Park; revisit if a new signal appears |
| **—** | 0–8 | Not a fit now | Reject with reason |

**Override rule:** a strong angle can move a lead up one tier (and a weak angle
can move it down one), but only with a one-line written justification in the
lead card. Overrides should be rare.

---

## Step 4 — Confidence

Rate how much of the score rests on facts rather than inferences.

- **High**: most factors are backed by sourced facts
- **Med**: a mix; key facts verified, some factors inferred
- **Low**: mostly inference; more research needed before outreach

A **Low**-confidence lead should not go to outreach, whatever its tier.

---

## Step 5 — Record it

`Opportunity Index` column format: `Tier · Score · Confidence`
e.g. `A · 22 · High`, `B · 15 · Med`.

In the lead card (`leads/qualified/<slug>.md`), include the factor breakdown:

```markdown
## Creative Opportunity Index
Gates: G1 ✓ G2 ✓ G3 ✓ G4 ✓ G5 ✓ G6 ✓
F1 3 · F2 2 (×2 = 4) · F3 2 · F4 2 · F5 3 · F6 2 · F7 2 · F8 1  → 19 / 27
Tier: B · Confidence: Med
Override: none
One-line rationale: ...
```

---

## Lead card template: `leads/qualified/<slug>.md`

```markdown
# <Company>
Lead ID: <slug> · Lane: A/B · Market: <country> · Added: YYYY-MM-DD

## Why this prospect (2–3 lines)
## Creative Opportunity Index (breakdown as above)
## Proof match
- Relevant proof: <case study ID / None>
- Relevance: High/Medium/Low/None, because ...
- Use: First message / After reply / Don't use
## Recommended channel and contact
## Links → research/<slug>.md · audits/<slug>.md
```

## Rejection note template: `leads/rejected/<slug>.md`

```markdown
# <Company> — Rejected YYYY-MM-DD
Gate/score: <e.g. G4 failed / scored 7>
Reason (1–2 lines):
Revisit? yes/no, and when/why:
```

Rejections are learning data. Keep the reasons specific.

---

## Calibration

After the first ~20 scored leads and the first outreach results, `/learn` should
check whether the tiers predict replies. Adjust the weights or thresholds here
(and log the change in `learnings.md`) instead of drifting informally.
