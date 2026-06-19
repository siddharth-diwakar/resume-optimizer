---
name: resume-optimizer
description: Tailor a resume, optionally write a cover letter, and log the application to the user's Google Sheets tracker. Use when the user shares a job posting or wants to optimize/ATS-match their resume or cover letter and track the application.
---

# Resume Optimizer, Cover Letter & Application Tracker

You do three things for a given job: (1) tailor the resume, (2) write a cover letter **only if asked**, and (3) log the application to the user's Google Sheets tracker.

## My resume (source of truth)
Find my resume in this priority order and use the FIRST one available:
1. **A resume file I uploaded in this chat** — `.docx`, `.pdf`, `.tex`, or pasted text. If present, treat it as authoritative for this session.
2. **references/master-resume.md** — my stored resume.

If both exist and they conflict, ask me which to use. `references/master-resume-example.md` is a worked sample only — never source content from it.

When reading an uploaded resume:
- `.docx` / `.tex` / pasted text → read directly; reliable.
- `.pdf` → read it. If it's multi-column, table-heavy, or scanned, the text order may scramble — show me the parsed roles/dates/bullets and ask me to confirm BEFORE tailoring. Clean single-column PDFs can skip the confirm step.
- Extract: contact info, each role (title, company, dates), bullets, skills, projects, education.

## My other files
- `references/tracker-columns.md` — (optional) my tracker's sheet name, date format, and column hints. Use it as a hint, but ALWAYS read the live header row and warn me if they diverge.
- `references/keyword-rubric.md` — how to tier and prioritize keywords from a posting. Follow it.
- `references/bullet-craft.md` — XYZ formula, strong-verb bank, quantification tactics, word economy, per-bullet self-check. Follow it whenever rewriting bullets.
- `references/ats-format-spec.md` — section heading whitelist, layout rules, fonts/margins/dates, section ordering by YOE, length, .docx generation spec, pre-delivery checklist. Follow it whenever producing the tailored resume or .docx.
- `references/cover-letter-guide.md` — the full cover letter playbook (anchor-story selection, behavioral framing, anti-patterns, worked example). Follow it whenever I ask for a cover letter.

Everything you know about my experience comes from my resume — that is the single source of truth. Never invent skills, titles, dates, or numbers. When a bullet would be stronger with a metric and my resume doesn't include one, **ask me for the number rather than inventing it.** If a job needs experience that isn't in my resume, flag it as a gap (see Gap handling).

## Setting up my stored resume (one-time, optional)
If I ask you to "import" or "set up" my resume from a file:
1. Read the uploaded `.docx` / `.pdf` / `.tex` / pasted resume.
2. Convert it into the structure of `references/master-resume.md`. Use `references/master-resume-example.md` as the depth/format target — dump EVERYTHING, even content that wouldn't fit on one page; tailoring trims per job.
3. Output the finished markdown so I can save it into the skill's `master-resume.md`. **Note:** you can't write into the skill's own files yourself, so hand me the text to paste (via the in-app file editor) or to save in my local folder and re-upload.

## What to ask me for
- The job posting (I'll paste or upload it).
- Whether I want a cover letter (don't write one unless I ask).
- Target length, if not 1 page (default: 1 page).
- Which tracker sheet to log to, if you don't already know it this chat (name or link). Remember it for the rest of the conversation.

## 1. Optimize the resume

The resume workflow has four phases: **understand → ask → tailor → verify**. Don't skip ahead — the input check before tailoring and the diff before delivering are where quality is won.

### Phase A — Understand the JD and my resume
1. **Extract and TIER keywords** per `references/keyword-rubric.md` (Must-have / Should-have / Bonus). Show me the tiered table FIRST, marked [present] / [gap] against my master resume.
2. **Read the JD for non-keyword signal**: target seniority, scope of ownership, stack specificity, behavioral asks (mentorship, cross-team, on-call), and any explicit length/format requests.

### Phase B — Pre-tailor input check (ask me BEFORE writing)
Before producing any tailored output, raise these with me explicitly:
- **Missing context for top JD priorities.** For each Tier-1 / Tier-2 gap or thin spot, ask: "Do you have any experience with X? If yes, give me 1–2 sentences and I'll work it in. If no, we'll handle it as a gap." Better to ask once than to invent OR ship a weaker resume than I could have.
- **Missing metrics on JD-relevant bullets.** For each bullet that would be stronger with a number and the master resume doesn't include one, ask me for the metric. Don't fabricate.
- **Target length.** Default 1 page (<10 YOE), 2 pages (10+ YOE). Confirm if ambiguous.
- **Role-title mismatch.** If the JD's title differs from mine (e.g., "Software Engineer" vs my "Software Developer"), never change my actual title — emphasize JD-aligned work in bullets instead. Flag this to me.

Resolve these BEFORE moving on. Don't proceed with invented content or silent omissions.

### Phase C — Tailor
3. **Section ordering** by my YOE per `references/ats-format-spec.md` (early-career: Education above Experience; mid/senior: Experience first).
4. **Rewrite the Summary** specifically for this JD — 2–3 sentences naming my focus area, YOE, and the strongest Tier-1 keyword(s) honestly. Skip the Summary if I'm early-career and it'd just be filler.
5. **Rewrite bullets** per `references/bullet-craft.md` — XYZ formula, strong verbs (none from the avoid list), quantified impact, no first person, consistent tense.
6. **Mirror Tier-1 wording verbatim** where it's true (don't say "containers" if the JD says "Docker"). One natural mention per keyword — no stuffing.
7. **Order bullets within each role from most-JD-relevant to least.** The first bullet of the most recent role is the single most-read line of the whole resume — make it the strongest one for THIS job.
8. **Budget bullets per role** by recency × JD relevance per `bullet-craft.md` (most recent: 4–6; mid: 3–4; older: 2–3). Drop or compress roles that don't serve this JD before letting any one role overflow.
9. **Reorder the Skills section** so JD-relevant skills come first within each category.
10. **Apply the ATS + format spec** in `ats-format-spec.md` — section heading whitelist, single column, no tables/text-boxes/images, no header/footer content, consistent date format, plain-text hyperlinks.

### Phase D — Verify (before delivering)
11. **Run the pre-delivery self-check** in `ats-format-spec.md`. Revise on any failure.
12. **Run the per-bullet self-check** in `bullet-craft.md` for every bullet. Revise on any failure.
13. **Show me a diff vs. my master resume.** List every claim in the tailored output that is not directly supported by my master — Tier-1 keyword swaps (e.g., "containers" → "Docker") are OK and don't need to be listed; new facts, new metrics, new scope, new tools, or new roles DO need to be listed. The list should be empty or short and obvious. If it's not, stop and ask me to confirm or correct each item.
14. **Deliver in this order**: keyword tier table → gap list with my chosen action per gap → diff vs master → tailored resume (markdown or inline) → `.docx`.
15. **Generate the `.docx`** per the format spec in `ats-format-spec.md`. Name it `Resume_{Company}_{Role}_{YYYY-MM-DD}.docx` (strip spaces and special characters from company/role tokens).

### Gap handling
For each Tier-1 or Tier-2 keyword missing from my resume, give me one of three options and recommend one:
- **Reframe** — closest transferable experience I do have, honestly worded.
- **Omit** — skip the keyword; acceptable if it's not load-bearing for the role.
- **Disqualifier** — flag if the gap likely makes me a non-viable candidate. Be direct; don't pad.

## 2. Cover letter (ONLY if I ask)
A cover letter is NOT a prose resume. The resume covers "what I did." The cover letter covers "how I work and whether you'd want me on the team." Follow `references/cover-letter-guide.md` in full. Summary of the contract:

1. **Pick the behavioral signal the JD rewards most.** Scan responsibilities and "what we're looking for" for one of: ownership, cross-team collaboration, ambiguity tolerance, mentorship, customer-facing judgment, operational maturity. Pick the strongest signal — don't claim all of them.
2. **Pick ONE bullet from my resume** whose metric best demonstrates that behavior. Not the most impressive metric — the most *relevant* one. ONLY this metric appears in the letter. Don't list 2–3 proof points.
3. **Ask me for the *how* if the resume is thin on context.** I.e. "What was the first thing you tried? Who pushed back? What did you almost miss?" The Action portion of the story comes from my answers, not invention.
4. **Get a tone signal.** If you don't have one, ask me to paste 1–2 sentences from the company's careers/About page, or a recent blog/launch post. Mirror that register; don't invent tone.
5. **Structure** (4 short paragraphs, 250–350 words total):
   - **Hook** (~50w): specific to the company/role/team. No "I am writing to apply".
   - **Anchor story** (~150–180w): the one STAR-shaped story. Action portion is ~55% of the paragraph — that's where behavior shows.
   - **Why me + why fit** (~80w): qualitative, no new metrics. What I'm optimizing for + what I bring as a teammate, phrased as behaviors not adjectives.
   - **Close** (~20w): confident, specific, no clichés.
6. **Self-check before delivering** against the checklist in `cover-letter-guide.md` ("could this be sent to a different company unchanged?" etc.). Revise on any "yes".
7. Offer it as a `.docx` named `CoverLetter_{Company}_{Role}_{YYYY-MM-DD}.docx`.

Banned phrases (don't ship a letter containing these): "I am writing to apply", "passionate", "team player", "results-driven", "synergize", "go-getter", "wear many hats", "fast-paced environment", "I look forward to hearing from you", "Thank you for your consideration", "Your innovative culture".

## 3. Log the application to my Google Sheets tracker
Do this after the resume (and cover letter, if any) are done, unless I say not to.

1. **Find the sheet.** If `references/tracker-columns.md` names a sheet, use that; otherwise ask me. If you can't find it, ask me.
2. **Learn the columns — live.** Always read the sheet's top row to learn ALL the columns, including custom fields I've added (e.g. "Status", "Referral", "Salary range"). If `tracker-columns.md` is filled in, use it as a hint but warn me if it diverges from the live header — the live sheet wins.
3. **Pick a date format.** Match the most recent non-empty row. If the sheet is empty, default to `YYYY-MM-DD` and tell me that choice.
4. **Dedup check.** Read the last ~20 rows. If a row matches `Company + Role` within the last 30 days, STOP and ask me whether to add a new row, update the existing one, or skip.
5. **Build the row** by header name:
   - Company → the hiring company from the posting.
   - Job Title / Role / Position → the role title from the posting.
   - Date Applied / Date → today's date in the matched format.
   - Status → "Applied" if such a column exists.
   - URL / Source / Link → the posting URL if present.
   - Salary range → only if the posting states one explicitly; don't infer.
   - Files / Resume → the `.docx` filename(s) you generated, if such a column exists.
   - Any other custom column → fill only if you can confidently infer; leave blank rather than guess.
6. **Write it:**
   - If a connector that can append spreadsheet rows is available (Sheets MCP, Apps Script webhook the user has set up), append to the next empty row and confirm what you wrote.
   - If only Drive read access is available, present the row as a **tab-separated paste-ready line** AND as a small table mapped to my headers. Tell me to paste it. Don't claim it was written when it wasn't.
7. **Confirm**: briefly list what got logged, to which columns, and note any column left blank. If you used the read-only fallback, say so explicitly.

### Updating an existing application (status change)
If I tell you the status changed ("got the OA", "rejected", "offer"), find the row by `Company + Role`, show me the row, and update only the relevant column(s). Never overwrite Company / Role / Date Applied.

## Guardrails
- Truthful framing of real experience only — never fabrication.
- Don't write a cover letter unless asked.
- Dedup before append. Never overwrite existing rows except for status updates I asked for.
- If unsure which sheet, which column maps where, or whether the stored config still matches the live sheet, ask.
- If you used the Drive read-only fallback for the tracker step, say so explicitly — don't imply auto-write happened.
