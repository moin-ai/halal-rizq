# Rulings Reference (Condensed, Verified)

Portable snapshot for standalone use. When running inside the Halal-Career repo, prefer the fuller files in `knowledge/rulings/`. All citations below are in `citations.md` (verified 2026-06-16).

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

## Verdict Synthesis

Red line triggered OR core business haram OR High-confidence oppression flag → ❌ HARAM.
Genuine scholarly split, no majority → 🟠 MUKHTALAF. Doubt/medium flags → 🟡 MASHBOOH (strict tolerance: lean prohibitive, say so). All clear → ✅ HALAL.
Always: user's madhab position first; named scholars; linked fatwas; Bukhari 52 / Muslim 1599 (doubtful matters) quoted for any non-clear verdict.
