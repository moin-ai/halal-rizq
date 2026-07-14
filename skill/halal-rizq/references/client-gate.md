# Client Gate — Freelance Client & Engagement Validation

Validates a CLIENT and a SPECIFIC ENGAGEMENT for a freelancer/agency before signing. Third sibling of the job-side Halal Gate and the Business Gate: same ledger, same verification protocol, same verdict language, same integrity rules. Different fiqh territory: the center of gravity is **i'anah 'ala al-ithm** — what YOUR hands would produce for them (Quran 5:2) — not just what the client's business is.

Triggers: "is this client halal to work with?", "should I take this gig/contract?", "can I build X for this company as a freelancer?", "/halalclient", "/halalcheck" with a freelance client or gig described.

**The unit of verdict is the ENGAGEMENT (client × deliverable), not the client alone.** A halal company can request a haram deliverable; a mixed company can request a neutral one. The client gets a standing profile (cached research); every new gig gets its own quick verdict on top of it.

## Step 0 — Madhab

Same as the other gates: `config/profile.yml → fiqh.madhab`, ask once if missing, present the user's madhab first, all schools shown.

## Step 1 — Client index check

Look up `knowledge/clients/_index.md` (user repo). Fresh entry (<12 months) → reuse the client-level research, skip to Step 3 intake questions about THIS engagement only. Stale or missing → full intake.

## Step 2 — Client research

Freelance clients are often small businesses or individuals with no filings — the 6-tier protocol in `company-research.md` degrades gracefully:

- **Registered company** → run the normal tiers (identity/ownership → revenue truth → screeners → ethics databases). Watchlist pre-filter applies identically (`oppression-watch/_index.md` or `watchlist-snapshot.md` + fresh WebSearch).
- **Small business / individual** → Tier 0 takes over: website, social profiles, platform profile (Upwork/Fiverr job history and reviews say a lot about what they actually commission), and the intake answers below. Low external verifiability → confidence capped at Medium, said openly in the report.

## Step 3 — Intake (ALWAYS before any verdict)

Extract what the user already said; ask ONLY the unanswered questions, batched (AskUserQuestion where it fits, ≤4 per call; else one numbered message).

**A. The client's business**
1. What does the client sell, and to whom? List their revenue sources as far as you know them.
2. Anything connected to the ruled axes — alcohol, gambling, riba products, conventional insurance, adult content, weapons, tobacco, dating platforms?

**B. The deliverable (the heart of this gate)**
3. Exactly what would you build/write/design/manage for them? What is it FOR — which part of their operation does it serve?
4. Where does your work sit relative to any haram element: is the deliverable itself the haram thing, does it promote it, does it keep the operation running, or does it serve a clean part of the business?

**C. The contract**
5. Scope and fee defined before you start (fixed price or defined rate × defined scope)? Payment terms — milestones, net-X, escrow?
6. One-off gig, or retainer/ongoing relationship?
7. Direct contract or through a platform (Upwork, Fiverr, Toptal, Malt…)? Which one?

**D. Payment & red lines**
8. Any indication the client's income is predominantly from a haram source (relevant to payment purity, asked without takalluf — outward check only, no inquisition)?
9. Anything in the brief requiring dishonesty from YOU — fake reviews, fabricated testimonials, deceptive ad claims, plagiarism, academic ghostwriting for submission as the buyer's own work? (These fail regardless of the client's own halal status — Bukhari 2079, Tirmidhi 1315.)

## Step 4 — Decompose and rule

Load `rulings.md` § Freelance & Client Work, plus any business-axis section the client's industry fires (riba, insurance, gambling, alcohol, music, gender interaction…). Same source hierarchy and fetch rules as `business-gate.md` § Step 3.

| Component | What to rule on |
|-----------|-----------------|
| Client's business | Same test as an employer's business (Halal Gate logic) — but it feeds the ladder below rather than deciding alone |
| **The deliverable** | Position on the assistance ladder (rulings.md) — decisive |
| Contract structure | Ijarah soundness: scope/fee defined (gharar — Muslim 1513), no compound-contract traps (Tirmidhi 1231) |
| Payment source | Purity positions when client income is predominantly haram |
| Platform | Platform-structure rulings (escrow, fees, bidding tokens) |
| Your own conduct | Ghish red lines in the brief itself |

## Step 5 — Verdict

Per component, then overall — same scale as the Business Gate:

- ❌ **HARAM** — deliverable on a prohibited rung of the ladder (the haram thing itself, or its direct promotion), or client on a High-confidence watchlist flag, or the brief demands dishonesty.
- 🔧 **CONDITIONAL** — fixable: carve the haram part out of the scope ("take the brand identity, decline the sports-betting landing pages"), convert undefined scope into defined milestones, route around a haram platform mechanic. List each fix + the verdict after it. Expected to be the most common outcome, as in the Business Gate.
- 🟠 **MUKHTALAF** — genuine split (e.g., neutral back-office work for a mixed-revenue client — the employment khilaf transfers here in lighter form, since a freelancer's tie is weaker than an employee's).
- 🟡 **MASHBOOH** — doubt (unverifiable small client, unclear what the deliverable will be used for); strict tolerance leans prohibitive and says so.
- ✅ **HALAL** — clean business or clean separable scope, sound contract, no flags.

Bukhari 52 / Muslim 1599 quoted for any non-clear verdict. Dua from `duas.md`.

## Step 6 — Report + index update

Save to `evaluations/client-{slug}-{YYYY-MM-DD}.md`:

```
# Client Gate — {client} — {engagement} — {date}
**Verdict:** {✅|🔧|🟠|🟡|❌} ({one line — engagement-level})
**Client standing profile:** {✅ clean | mixed: which parts | ❌} — research date
**Confidence:** {H/M/L} — unknowns: {list or "none"}

## Client business     (what they do, revenue sources, watchlist result)
## This engagement     (deliverable, ladder rung, basis with citations)
## Contract & payment  (ijarah check, platform notes, payment-purity note if fired)
## Required changes    (CONDITIONAL only — each fix + resulting verdict)
## Scholarly positions (user's madhab first; named scholars; linked fatwas)
## Sources             (every citation + direct reader URL + fetch date)
## Dua
```

…followed by the Mandatory Disclaimer (SKILL.md § Mandatory Disclaimer) — never omitted.

**After every verdict:** append/update the client's row in `knowledge/clients/_index.md` (see § Client index below). A ✅ or 🔧-satisfied engagement also updates the Green List flag.

## Client index & Green Client List

`knowledge/clients/_index.md` — private user data (in the user's private repo, junctioned into the working tree; NEVER in the public repo). Self-growing, same pattern as the employer index. One row per client:

| Client | Sector | Business profile | Engagements ruled (type → verdict) | Green | Payment notes | Evidence | Updated |
|--------|--------|------------------|------------------------------------|-------|---------------|----------|---------|

- **Business profile** = client-level standing (✅ clean / mixed: named parts / ❌), so gig #2 skips re-research inside 12 months.
- **Green** = ✅ when at least one engagement passed and nothing haram surfaced since — this column IS the Green Client List (filter Green=✅). Kept private; the format deliberately works anonymized (drop Client+Evidence columns) so an opt-in public directory stays possible later.
- Detailed dossiers, when research was deep: `knowledge/clients/{slug}.md`.

## Scope limits

- Rules on the engagement as DESCRIBED; the signed contract's actual wording is the user's to verify — recommend bringing unusual terms to a scholar.
- Client's inward affairs are not investigated beyond the outward check — fiqh operates on the apparent (zahir); say so when payment-purity is raised.
- Never issues fatwas. Novel platform mechanics or payment structures → cite closest analyses, label `[analysis — no source]` where sources run out, route to a qualified mufti.
