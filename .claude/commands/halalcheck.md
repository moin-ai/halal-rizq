---
description: Halal-check anything — a job, business idea, freelance client/gig, product, or income source — against verified Quran/Sunnah rulings (halal-rizq skill)
argument-hint: [job posting, company, business idea, client/gig, or question]
---

Load and follow the **halal-rizq** skill (invoke it via the Skill tool if listed; otherwise read `C:\Users\arifu\.claude\skills\halal-rizq\SKILL.md` and follow it exactly).

Input: $ARGUMENTS

Route:
- Job posting / JD / company + role / "can I work at X" → **Stage 1 Halal Gate** (SKILL.md), then career fit only if not haram.
- Business idea / startup / side hustle / "can I sell X" / user is the owner → **Business Gate** (`references/business-gate.md`): ask the batched fiqh intake questions FIRST (ownership/qabd, riba, gharar/maysir, honesty, partners) — never rule on an under-specified idea.
- Freelance client / gig / "should I take this contract" / user would be hired for a defined deliverable, not employed → **Client Gate** (`references/client-gate.md`): check the client index first, then batched intake (client's business, the exact deliverable and what it serves, contract terms, platform) — verdict is per ENGAGEMENT (client × deliverable), never on the client alone.
- Ambiguous or empty input → ask which one it is, or what they want checked.

Job vs client tiebreaker: salaried/ongoing role under their direction = job; defined deliverable for a fee = client gig; retainer = client gig ruled one rung stricter (see rulings.md § Freelance & Client Work).

Non-negotiable rules from the skill: scripture only from the verified ledger (`references/citations.md`) or live-verified per `references/verification.md` — never from memory; user's madhab first, all schools shown; the tool reports scholarship and never issues fatwas; every factual claim carries a source. End with a relevant dua from `references/duas.md`, then the **Mandatory Disclaimer** block from SKILL.md — never omitted.
