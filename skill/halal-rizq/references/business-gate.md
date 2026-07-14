# Business Gate — Venture & Business-Idea Validation

Validates a business idea, side hustle, or existing business the user OWNS (or would own) against Quran, Sunnah, and cited scholarship. Sibling of the job-side Halal Gate: same ledger, same verification protocol, same verdict language, same integrity rules — different fiqh territory (fiqh al-muamalat: contracts, ownership, funding), so it has its own intake and decomposition.

Triggers: "is this business idea halal?", "validate my startup", "can I sell X?", "/halalbiz", "/halalcheck" with a business described.

## Step 0 — Madhab

Same as the job gate: `config/profile.yml → fiqh.madhab`, ask once if missing, present the user's madhab first, all schools shown.

## Step 1 — Intake (ALWAYS before any verdict)

Never rule on a one-line idea. First extract what the user already said, then ask ONLY the unanswered questions below — batched (one message, numbered), not one-by-one. If the answers change the picture, follow up once more. No verdict until every pillar is answered or the user explicitly says "unknown" (unknowns lower confidence and are named in the report).

**A. The business itself**
1. Describe it in detail: what exactly do you sell, to whom, and how does money come in? List EVERY revenue stream (sales, subscriptions, ads, affiliate commissions, fees, float).
2. Is the product/service itself connected to anything ruled on in `rulings.md` — alcohol, pork, gambling, riba products, adult content, weapons, tobacco?

**B. Ownership & possession (qabd)**
3. Do you own and possess what you sell before you sell it? (Dropshipping, pre-orders, and reselling before delivery each have specific rulings — Tirmidhi 1232.)
4. Physical goods, digital goods, or services?

**C. Riba**
5. How is it funded — own savings, equity partners, VC, or an interest-bearing loan / credit line / BNPL?
6. Will the business earn or pay interest anywhere: bank accounts, customer float, late fees, financing you offer customers?

**D. Gharar & maysir**
7. At the moment of sale, are price, product, and delivery terms fully defined? Any element of chance — mystery boxes, raffles, lotteries, speculative assets?
8. Any conventional insurance products sold or embedded? Derivatives, leverage, interest-bearing DeFi?

**E. Honesty (ghish) & harm**
9. Anything in the marketing that exaggerates, conceals defects, manufactures fake scarcity/reviews? (Bukhari 2079, Tirmidhi 1315)
10. Could the product harm users or serve oppression (check watchlists if B2B customers include flagged entities)?

**F. Partners, platforms, customers**
11. Key partners, platforms, and anchor customers — any with a haram core business your revenue depends on?
12. Will any employee or contractor be required to perform a haram task?

In Claude Code, use the AskUserQuestion tool for the batch where it fits (≤4 questions per call); otherwise a numbered list in chat.

## Step 2 — Decompose

Break the business into ruled components; each gets its own verdict line:

| Component | What to rule on |
|-----------|-----------------|
| Product/service | Permissibility of the thing itself |
| Each revenue stream | Separately — one haram stream doesn't equal a haram business if separable |
| Funding structure | Riba loan vs. equity vs. musharakah/mudarabah; investor terms with guaranteed returns = riba in disguise |
| Contract structure | Ownership timing (qabd), gharar tests, salam/istisna' fit for pre-orders |
| Partners/customers | Assisting sin (Quran 5:2), watchlist flags |
| Marketing practices | Ghish tests |

## Step 3 — Apply rulings

**Check `business-catalog.md` first** — if the model is listed, it names the axes that fire and which intake answers decide the outcome (a catalog lean is a starting point, never a verdict). Unlisted model → decompose onto the catalog's axes yourself, and append a row to the catalog after ruling.

Load `rulings.md` § Business Ownership & Trade plus any axis section that matches (riba, insurance, gambling, alcohol, defense, music & entertainment, gender interaction, bribery, worker rights, compound contracts). Citations ONLY from `citations.md` or live-verified per `verification.md`. Source hierarchy when authorities differ:

1. **Ledger scripture** (Quran/hadith, verified)
2. **Fiqh academies & standards** — OIC International Islamic Fiqh Academy (iifa-aifi.org — fetchable), AAOIFI (aaoifi.com — fetchable), Islamic Fiqh Council/MWL (themwl.org — fetchable), SC Malaysia Shariah Advisory Council (sc.com.my — fetchable), Mufti WP Irsyad al-Fatwa (muftiwp.gov.my — fetchable)
3. **Madhab-attributed fatwas** — IslamQA.info, Askimam.org (fetchable), SeekersGuidance (fetchable); daruliftaa.com and darulifta-deoband.com are LINK-ONLY (bot-blocked/unstable — never assert their contents unfetched)
4. **Contemporary specialist analysis** — Amanah Advisors / Mufti Faraz Adam papers (fetchable), Taqi Usmani's *An Introduction to Islamic Finance* — always labeled "contemporary analysis", never the sole basis of a verdict

Fetch rule: WebFetch before asserting any page's content; fetch fails → present as link labeled "reference — verify content".

## Step 4 — Verdict

Per component, then overall:

- ❌ **HARAM** — a prohibited element is core and inseparable (riba funding already signed, gambling mechanics, haram product).
- 🔧 **CONDITIONAL** — haram/doubtful elements exist but are separable: list the exact restructures (e.g., replace interest loan with musharakah or savings; restructure dropshipping as wakalah agency or salam; drop the mystery-box SKU; replace conventional insurance with takaful) and state the verdict after each fix. This outcome is the business gate's most common and most useful.
- 🟠 **MUKHTALAF** — genuine scholarly split on a core element (e.g., dropshipping models, certain crypto): present each position with its scholars and conditions, user's madhab first, Istikharah reminder.
- 🟡 **MASHBOOH** — doubt remains (unknown answers, unverifiable partner revenue): name the doubts; strict tolerance leans prohibitive and says so.
- ✅ **HALAL** — all components clear.

Quote Bukhari 52 / Muslim 1599 for any non-clear verdict. End with a relevant dua from `duas.md`.

## Step 5 — Report

Save to `evaluations/biz-{slug}-{YYYY-MM-DD}.md`:

```
# Business Gate — {idea name} — {date}
**Verdict:** {✅|🔧|🟠|🟡|❌} ({one line})
**Confidence:** {H/M/L} — unknowns: {list or "none"}

## What was assessed  (the user's answers, restated)
## Component verdicts  (table: component | verdict | basis with citations)
## Required changes    (CONDITIONAL only — each fix + resulting verdict)
## Scholarly positions (user's madhab first; named scholars; linked fatwas)
## Sources             (every citation + direct reader URL + fetch date)
## Dua
```

…followed by the mandatory disclaimer (SKILL.md § Mandatory Disclaimer) — never omitted, never abbreviated.

## Scope limits

- The gate rules on the BUSINESS MODEL, not on execution details it can't see (actual contract wording, actual investor term sheets). Say so when relevant and recommend the user bring the actual contract to a scholar.
- Purification calculations (existing haram income) → out of scope until scholar sign-off (see exit-mode.md; calculator is deferred per project decision).
- This gate NEVER issues fatwas. It reports scholarship. On anything novel (new fintech structure, token model), say plainly that the matter is new, cite the closest analyses, and route to a qualified mufti — Amanah Advisors and the user's local mufti are the project's named candidates.
