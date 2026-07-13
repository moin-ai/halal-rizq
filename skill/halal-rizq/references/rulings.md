# Rulings Reference (Condensed, Verified)

Portable snapshot for standalone use. When running inside the Halal-Rizq repo, prefer the fuller files in `knowledge/rulings/`. All citations below are in `citations.md` (verified 2026-06-16).

## Riba / Conventional Banking

**Basis:** Quran 2:275, 2:278–279. Hadith: Muslim 1598 (Abd al-Baqi) / CDN#4093 — curses consumer, payer, **recorder, and the two witnesses**; also Tirmidhi 1206 (Al-Albani: Sahih), Abu Dawud 3333 (Al-Albani: Sahih), Ibn Majah 2277 (Al-Albani: Sahih).

| Position | Ruling | Held by |
|----------|--------|---------|
| Majority/cautious | Any employment at a riba institution is haram — the hadith reaches the recorder and witness; salary derives from haram | Ibn Uthaymeen, Ibn Baz, IslamQA (22905), Deoband, AAOIFI |
| Minority (necessity only) | Role fully unrelated to riba may be permitted temporarily under darurah, while seeking halal work | Al-Qaradawi (with strict conditions) |

Fully Islamic bank / takaful → generally halal. Fintech → judge the product (interest-bearing = haram; neutral payments = halal).

## Conventional Insurance

**Basis:** gharar (Muslim 1513 / CDN#3808), unjust consumption (Quran 4:29), riba in float investment. OIC Fiqh Academy Resolution 9/2 (1985): conventional insurance haram; takaful is the alternative. Strong majority: employment there is haram (same logic as riba). Takaful → halal.

## Defense / Weapons

**Basis:** Quran 5:2 (no help in sin/aggression), 4:75 (side with the oppressed). Weapons in principle are not haram; supplying **oppressors** is.
- Supplier to forces killing civilians/Muslims (see watchlists) → haram, near-consensus — any role.
- Defense exclusively for legitimate/defensive use → mukhtalaf; judge client base.
- Military AI/targeting for oppressive forces → haram, no dispute worth noting.

## Alcohol / Tobacco

**Basis:** Quran 5:90; Ibn Majah 3381 (Al-Albani: Sahih — "cursed ten with regard to wine", entire supply chain incl. transporter and the one who profits) = Tirmidhi 1295 (parallel, Hasan Sahih); Abu Dawud 3674 (separate parallel narration via Ibn Umar, Al-Albani: Sahih).
- Any role at alcohol producer/distributor → haram (consensus).
- Restaurant serving alcohol, non-serving role → mashbooh (some permit).
- Tobacco → haram per contemporary majority (harm principle); IslamQA 10922, Saudi Permanent Committee.

## Gambling / Maysir

**Basis:** Quran 5:90–91, 2:219. Casino/betting/lottery platforms → haram, any role (consensus). Crypto: spot-only exchange → mukhtalaf; derivatives/leverage/DeFi-interest → haram (riba+gharar+maysir combined).

## Indirect Tech Work for a Haram Business

The recorder-and-witnesses clause of Muslim 1598 is the pivot: majority extend it to all roles sustaining the institution (IslamQA 9987, 22905; Deoband). Minority (Al-Qaradawi): permissible under necessity if the role is fully separated, temporarily, while seeking halal work.

**Default under `mashbooh_tolerance: strict`:** treat as haram, present the minority view with its conditions.

Mixed-revenue employers: haram share <5% and role unrelated → many scholars tolerate (AAOIFI investment threshold used as analogy); 5–33% → mashbooh; core-haram → haram. State the analogy honestly: AAOIFI thresholds were written for share ownership, not employment — flag this distinction.

## Oppression Complicity

**Basis:** Quran 5:2, 4:75; Bukhari 6011 / Muslim 2586 (CDN#6586) — the ummah as one body.
Flag tiers (from watchlists): High confidence (direct weapons/surveillance to oppressors) → haram. Medium (enabling tech contracts) → haram per majority reading of 5:2 / mashbooh at minimum. Financial/indirect ties → mashbooh, disclose and let the user weigh.

## Business Ownership & Trade (muamalat — Business Gate)

**Basis:** Quran 4:29 (only trade by mutual consent), 2:188 (no unjust/bribed wealth), 2:275 ("Allah has permitted trade and forbidden riba"). Bukhari 2079 (truthful disclosure → blessed transaction), Tirmidhi 1315 (Al-Albani: Sahih — "whoever cheats is not one of us"), Tirmidhi 1232 (Al-Albani: Sahih — "do not sell what is not with you"), Muslim 1513 / CDN#3808 (gharar).

### Selling without possession (dropshipping, pre-orders, reselling)
Tirmidhi 1232 is the pivot. Classical majority: selling what you don't own/possess is invalid — EXCEPT salam (full payment up front, precisely specified goods, fixed delivery date) and istisna' (commissioned manufacture).
- Dropshipping as commonly practiced (list → sell → then buy) → impermissible per most contemporary Hanafi muftis; permissible restructured as **wakalah** (you act as the buyer's purchasing agent for a fee) or under salam conditions. Present both positions with links (Askimam, Amanah Advisors analyses — fetch before asserting).
- Digital goods/services you produce → qabd issue doesn't arise.

### Funding
- Interest-bearing loan / credit line / conventional BNPL → haram (Quran 2:275; Muslim 1598 curses the payer too).
- Own savings, straight equity, **musharakah/mudarabah** → structurally halal. Screen investor terms: guaranteed return or guaranteed capital to the "investor" = riba in disguise; reference AAOIFI standards. Preference shares/liquidation preferences → mukhtalaf, flag for scholar review of the actual term sheet.
- Conventional business insurance → haram per OIC Fiqh Academy Res. 9/2 (1985); takaful where available; legally mandated insurance → necessity discussions exist, present positions.

### Revenue streams — decompose, rule each separately
- Interest on balances/customer float → riba, haram at any percentage.
- Advertising/affiliate for haram products → assisting sin (Quran 5:2) → that stream haram.
- Mixed: haram stream <5% and incidental → many tolerate with purification of that share; 5–33% → mashbooh; core-haram → haram. Same AAOIFI-analogy caveat as employment: those thresholds were written for share screening — say so.

### Gharar & maysir in the model
- Price, product, or delivery materially undefined at contract time → gharar (Muslim 1513). Minor operational uncertainty ≠ gharar; the test is whether the uncertainty is in the CONTRACT ESSENTIALS and likely to cause dispute.
- Mystery boxes, loot boxes, raffle-based sales, pay-to-spin mechanics → maysir (Quran 5:90–91) → haram.
- Crypto/tokens: spot utility → mukhtalaf; interest-bearing, leveraged, or lottery-like tokenomics → haram (riba+gharar+maysir).

### Marketing honesty (ghish)
Concealing defects, fabricated reviews/scarcity, deceptive claims → prohibited (Bukhari 2079; Tirmidhi 1315). Structural deception → that practice haram; verdict CONDITIONAL on removing it.

## Music & Entertainment (mukhtalaf — always present both positions)

**Basis:** Bukhari 5590 (ma'azif — ⚠ mu'allaq; Ibn Hajar + majority: sahih; Ibn Hazm contested the chain — this dispute IS the crux, state it).
- Majority of the four madhhabs (incl. Hanafi): musical instruments impermissible; vocals-only nasheed with clean content broadly accepted.
- Minority (Ibn Hazm; contemporary: Al-Qaradawi): permissible when content and context are free of the haram (lewdness, intoxicants, distraction from obligations).
- Business application: music-CORE businesses (label, streaming playlists, DJ/club services, music-driven channels) → 🟠 mukhtalaf at best under the minority view, haram per majority — present both, user's madhab first. Music-INCIDENTAL (background in produced ads) → same khilaf at smaller scale; offer the instrument-free alternative. Vocal-only / sound-design work → generally clear.

## Gender Interaction — khalwa, ikhtilat, awrah (business models)

**Basis:** Bukhari 5233 (no khalwa with a non-mahram), Quran 24:30–31 (gaze + adornment), 33:33 (tabarruj — ⚠ addressed to the Prophet's ﷺ wives; scholars extend the principle, say so).
- **Dating apps / hookup platforms** → facilitate khalwa and zina-adjacent contact → haram, near-consensus — building, marketing, or managing them included (Quran 5:2).
- **Matrimonial platforms with safeguards** (wali involvement, meeting protocols, no free chat) → accepted by many contemporary scholars with conditions → 🟡/✅ depending on implementation.
- **Services involving non-mahram touch/awrah** (mixed massage/spa/salon) → haram per majority; gender-segregated equivalents → halal. Mixed gyms → mukhtalaf/mashbooh; segregated or women-only → clear.
- **Modeling, influencer, and talent agencies** trading on tabarruj/display → prohibited per majority (24:31, 33:33 principle); modest-fashion or product-only content → judge the actual content.
- One-on-one home services to a lone non-mahram client (tutoring, coaching, massage) → khalwa issue; third-person presence or public/recorded setting removes it → CONDITIONAL territory.

## Bribery & Corruption

**Basis:** Quran 2:188 (wealth sent to rulers to consume unjustly), Tirmidhi 1337 (Ahmad Shakir: Sahih — curse on briber and taker).
Businesses whose market access depends on bribes (import "facilitation", tender kickbacks, buying regulators) → that channel haram; whole business haram if inseparable. Paying under extortion to recover one's own established right → scholars differ, sin falls on the taker per many — present positions, flag for scholar.

## Worker Rights (running the business, not just starting it)

**Basis:** Ibn Majah 2443 (Al-Albani: Sahih — "give the worker his wages before his sweat dries"); Quran 4:29 mutual consent.
Delayed/withheld wages, dark-pattern gig compensation, requiring employees to perform haram tasks (serve alcohol, deceptive sales scripts) → zulm; a model PREMISED on wage abuse (systematic unpaid "trials", fake commission traps) → haram as practiced. Standard employment with fair, timely pay → clear; this axis usually produces CONDITIONAL fixes, not whole-business verdicts.

## Compound & Conditional Contracts

**Basis:** Tirmidhi 1231 (Al-Albani: Sahih — "two sales in one"), plus gharar (Muslim 1513).
Price-contingent bundles ("$X cash / $Y credit" left unresolved at contract), sale conditional on a second sale, hidden financing folded into price → classical prohibition territory; modern equivalents (some BNPL structures, tying arrangements, "free" bundles with obligatory paid continuation) → decompose the actual contract; where the structure resolves to a single defined price and obligation → clear.

## Freelance & Client Work (i'anah ladder — Client Gate)

**Basis:** Quran 5:2 ("cooperate in righteousness… do not cooperate in sin and aggression"); Muslim 1598 / CDN#4093 (riba curse reaches the **recorder and the two witnesses** — the scribe is the paradigm of the hired hand who produces the instrument of the sin); Ibn Majah 3381 = Tirmidhi 1295, Abu Dawud 3674 parallel (khamr chain — ten cursed including presser, carrier, server: assistance roles, not just the drinker).

### The assistance ladder — rule the DELIVERABLE by its rung

1. **The deliverable IS the haram thing** (betting engine, riba loan calculator, alcohol-brand campaign asset, dating-app build) → haram; the scribe/presser texts apply directly. Near-consensus.
2. **The deliverable directly promotes the haram** (ads, funnels, SEO, content marketing whose subject is the haram product) → haram per majority — promotion is the "carrier/server" rung of the chain.
3. **Neutral deliverable sustaining an essentially-haram operation** (back-office tooling, internal dashboards, general IT for a casino/riba institution) → the employment khilaf transfers: majority prohibit (Muslim 1598 extension — IslamQA 22905, 9987; Deoband); minority (Al-Qaradawi) permit temporarily under necessity with full separation. A freelancer's one-off tie is *lighter* than employment (no ongoing loyalty/salary dependence) — some contemporary muftis ease accordingly for one-offs; retainers approach employment. Present both; strict tolerance leans prohibitive.
4. **Neutral deliverable serving the CLEAN part of a mixed business** (menu design for a restaurant that also serves alcohol; logo for a bank's charitable foundation) → judge separability + the mixed-revenue thresholds analogy (<5% incidental / 5–33% mashbooh / core-haram) with the same honesty caveat: those thresholds were written for share screening, not services — say so.
5. **Neutral deliverable for a halal business** → halal; contract soundness is the only remaining check.

Retainer vs one-off: an ongoing retainer with a rung-3 client accumulates the very dependence that drives the majority employment position — treat a retainer one rung stricter than the identical one-off.

### Contract soundness (ijarah)
Scope and fee defined before work starts (undefined scope/fee = gharar — Muslim 1513); no compound traps ("free" work bound to obligatory paid continuation — Tirmidhi 1231); timely payment cuts both ways (Ibn Majah 2443 — and the freelancer's own delivery obligations are the mirror duty, Quran 4:29 mutual consent).

### The freelancer's own conduct — absolute red lines regardless of client
Fake reviews/testimonials, deceptive ad claims, plagiarized deliverables, academic work submitted as the buyer's own → ghish (Bukhari 2079; Tirmidhi 1315 "whoever cheats is not one of us") — the engagement is haram even for a fully halal client.

### Payment from a client whose income is predominantly haram
Distinct question from the deliverable. Fiqh judges the outward (the fee is owed for lawful work under a lawful contract); Muslim 1015 grounds the caution (Allah accepts only the good). Contemporary fatwa positions differ on accepting payment from predominantly-haram wealth — present with links fetched at answer time (IslamQA and Askimam both carry rulings on wages from a person of haram income — fetch before asserting specifics; unfetched → link-only). Mostly-halal income client → no issue per the zahir principle `[analysis of the classical principle — positions linked at runtime]`.

### Freelance platforms (Upwork, Fiverr, Toptal, Malt…)
Decompose the platform mechanics rather than ruling the platform:
- **Brokerage/service fee** (platform % of the contract) → fee for a real intermediation service; classically the samsarah (brokerage) discussion — permissible per the well-known majority when the fee is known; verify specifics via AAOIFI standards / linked fatwas at answer time.
- **Escrow** (client funds held until milestone approval) → custody/agency arrangement reducing gharar for both sides — structurally sound `[analysis — no source]`; flag only if the platform pays or charges interest on held funds (riba — check the platform's terms if determinable, else name it as an unknown).
- **Paid bidding tokens** (e.g., "Connects" purchased to submit proposals) → payment for a chance at consideration; contemporary analyses differ on whether this is a fee-for-service or gharar-tainted — mukhtalaf territory, present positions with links, `[analysis — no source]` where none fetchable.
- **Mandatory arbitration/dispute terms** → judge by fairness of the actual terms; not inherently problematic.
- Working THROUGH a platform never changes the deliverable's ladder rung — the platform layer is additive, not substitutive.

## Verdict Synthesis

Red line triggered OR core business haram OR High-confidence oppression flag → ❌ HARAM.
Genuine scholarly split, no majority → 🟠 MUKHTALAF. Doubt/medium flags → 🟡 MASHBOOH (strict tolerance: lean prohibitive, say so). All clear → ✅ HALAL.
Always: user's madhab position first; named scholars; linked fatwas; Bukhari 52 / Muslim 1599 (doubtful matters) quoted for any non-clear verdict.
