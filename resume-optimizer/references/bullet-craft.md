# Bullet Craft

The single highest-leverage thing in a resume is bullet quality. A great bullet does three things in one line:

1. Opens with a strong action verb (specific, not generic).
2. States WHAT was done, with enough scope/context to be unambiguous.
3. Quantifies the IMPACT — number, %, before/after, scale, time saved, dollars, adoption.

If a bullet is missing any of the three, tighten it before keeping it.

## The XYZ formula

> "Accomplished X, as measured by Y, by doing Z."

(Canonical framing from Google's internal resume guide. It's still the standard because it works.)

❌ Weak: "Improved system performance using caching."
✅ XYZ: "Cut checkout p99 latency 38% (820ms → 510ms) by replacing per-request DB lookups with a Redis-backed cache."

Bones: X = cut latency. Y = 38%, 820 → 510ms. Z = Redis cache replacing DB lookups.

You don't need to land the parts in this exact order — `Z → X → Y` is also fine ("Replaced per-request DB lookups with a Redis-backed cache, cutting p99 latency 38%"). The test is whether all three are present, not the order.

## Strong verb bank (by behavior)

Don't repeat a verb inside a single role. Don't use "handled" or "did" anywhere.

- **Built / shipped**: built, shipped, launched, deployed, released, delivered, prototyped, productionized
- **Improved**: cut, reduced, improved, increased, accelerated, optimized, doubled, halved, streamlined
- **Led / owned**: led, owned, drove, headed, directed, spearheaded, orchestrated
- **Designed**: designed, architected, modeled, structured, mapped, proposed
- **Collaborated**: partnered, paired, coordinated, aligned, negotiated, championed
- **Mentored**: mentored, coached, trained, onboarded, upleveled
- **Saved / removed**: saved, eliminated, removed, deprecated, retired, consolidated
- **Analyzed**: analyzed, evaluated, audited, profiled, benchmarked, measured, investigated

Verbs to avoid (vague or weak): handled, managed (unless people), did, worked on, helped, supported, assisted, participated in, was responsible for, was involved in, contributed to (use only if literally a contributor, not an owner).

## Quantifying when the raw metric doesn't exist

Not every win has a clean number. Substitutes that count as quantification:

- **Percent change**: "reduced support tickets 22%"
- **Time saved**: "shaved 2 days off new-service setup"
- **Scope of users / engineers / locations**: "used by 40+ engineers", "across 12 store locations"
- **Money**: "flagged $180K of mispriced SKUs"
- **Volume / throughput**: "handling 2M messages/month"
- **Reach**: "1.2K GitHub stars", "6K monthly users"
- **Before / after**: "p99 820ms → 510ms"
- **Rate or ratio**: "failure rate from 4.1% to 0.3%"
- **Adoption signal**: "adopted as team standard", "used as default by 3 squads"
- **Comparison to baseline**: "passed third-party security audit on first review"

If none of these apply, ASK the user — don't invent. A non-quantified bullet that's specific ("Designed HIPAA-compliant patient messaging service") is better than an invented number ("Improved messaging throughput by 50%").

## Word economy (cut every one of these)

- **"Responsible for"** → just say what was done. ("Responsible for migrating services" → "Migrated 14 services").
- **"Successfully"** → if it shipped, success is implied. Cut.
- **"Helped" / "assisted"** → if you really helped (not owned), frame the help concretely: "supported X by contributing Y". Otherwise just claim it.
- **"Various" / "multiple"** → replace with a number or be specific.
- **"Utilize"** → "use".
- **"In order to"** → "to".
- **"That" / "which"** → often droppable.
- **Leading articles** ("A", "The") at the start of bullets — usually cuttable.

## Bullet shape and length

- One line per bullet ideally; two lines max. If a bullet wraps past two lines, it's cramming two ideas — split or trim.
- **Past tense** for past roles. **Present tense** for the current role.
- **No first person.** No "I", no "my". (Cover letter is different.)
- **Punctuation**: period at end of every bullet OR no period at end of any bullet. Be consistent across the whole document.
- No semicolons inside bullets — keep them simple, single-clause where possible. Em-dash or full stop instead if you need a break.

## How many bullets per role

Scale by recency and JD relevance, not seniority. Budget for a 1-page tailored output:

- **Most recent / most JD-relevant role**: 4–6 bullets
- **Mid roles**: 3–4 bullets
- **Older / less relevant roles**: 2–3 bullets
- **Internships > 3 years ago**: cut entirely unless relevant; 1–2 bullets if kept
- **Roles > 10 years old or in an unrelated field**: usually compress to one summary line

For a 2-page resume (10+ YOE), add ~1 bullet per band.

## Within a role: order bullets by JD relevance

Order bullets from most-relevant-to-this-JD to least, NOT chronologically within the role. The first bullet of the most recent role is the most-read line of the entire resume — make it the strongest one for this specific job.

## Before-and-after examples

❌ "Responsible for improving system performance and working with the team to deploy various optimizations."
✅ "Cut p99 checkout latency 38% by replacing per-request DB lookups with a Redis cache; partnered with security to design a redaction shape and rolled out behind a feature flag with zero incidents."

❌ "Helped onboard new engineers and provided mentorship."
✅ "Mentored 3 junior engineers; ran weekly design-review office hours adopted as team standard."

❌ "Worked on the migration from monolith to microservices."
✅ "Owned migration from monolith to 6 microservices; documented runbooks adopted by 3 squads."

❌ "Used various technologies to build admin dashboards."
✅ "Shipped a React admin dashboard used by store managers across 12 locations."

❌ "Successfully launched new feature that customers liked."
✅ "Launched in-app referral flow that drove 18% of new signups within 60 days."

## Mirroring keywords inside bullets

When a bullet's natural verb / noun would be a synonym of a Tier-1 keyword from the JD, swap to the exact word the JD uses — but only if it stays truthful.

- JD says "Docker" → write "Docker", not "containers".
- JD says "Kubernetes" → write "Kubernetes", not "K8s" or "container orchestration".
- JD says "TypeScript" → write "TypeScript", not "TS" or "JavaScript".
- JD says "SQL" → write "SQL" alongside "Postgres" — both can land.

Don't pad bullets with keywords. One natural mention beats three forced ones; modern ATS weighs by context, and recruiters can spot stuffing.

## Self-check per bullet

Before keeping a bullet, every one must pass:

- [ ] **"So what?" test** — does the reader know why this mattered?
- [ ] **Specificity test** — could this bullet apply to anyone with this title? If yes, it's too generic.
- [ ] **Truthfulness test** — is every claim supported by the master resume? If you added a fact, ask the user before keeping it.
- [ ] **Verb test** — strong action verb at the start, not on the avoid list?
- [ ] **Quantification test** — is there a number, scope, ratio, or before/after? If no, can one be added? If no metric is possible, is the bullet still specific?
- [ ] **Length test** — one line, max two?
- [ ] **Tense test** — past for past roles, present for current?
