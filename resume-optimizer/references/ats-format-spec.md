# ATS Safety & Format Spec

The tailored resume must pass two readers: an ATS (Applicant Tracking System) and a human recruiter. Both have specific demands. This file is the mechanical spec.

## ATS rules (non-negotiable)

### Section headings — use these exact names
ATS parsers look for known heading text. Use:
- **Experience** (NOT "Work History", "Professional Journey", "Where I've Been")
- **Education** (NOT "Academic Background")
- **Skills** (NOT "Toolbelt", "What I Use", "Tech Stack")
- **Projects** (NOT "Side Projects", "Things I've Built")
- **Summary** (NOT "About Me"; use "Objective" only if changing careers)
- **Certifications** (if applicable)
- **Publications** (if applicable, research roles)

Custom heading names break parsing. Don't be clever here.

### Layout
- **Single column only.** Two-column layouts get parsed left-column-then-right-column instead of in reading order, scrambling content.
- **No tables.** Flattened unpredictably.
- **No text boxes.** Same reason.
- **No graphics, icons, or photos.** Some ATS skip them; some choke. Zero value, real risk.
- **No content in the document header or footer.** Many ATS skip those regions entirely. Contact info goes in the body.

### Fonts
Safe list: Arial, Calibri, Helvetica, Times New Roman, Georgia, Cambria. Body 10–11pt, subheadings 11–12pt, name 14–16pt. One font family for the whole document.

### Margins
0.5"–1" all sides. Don't go below 0.5". 0.7" is a good balance.

### Dates
- Pick ONE format and use it everywhere: `Aug 2023 – Present` OR `08/2023 – Present` OR `2023 – Present`.
- Use en-dash or hyphen consistently.
- Months either abbreviated (Aug) or spelled out (August) — pick one.
- "Present" for current role; never blank.

### Hyperlinks
- **Plain text** for ATS safety: `linkedin.com/in/janedoe` not Markdown link form.
- In the .docx, the URL text is fine to also carry a real hyperlink underneath, but the visible text must be the URL itself, not "LinkedIn" or "Click here".
- Some ATS strip hyperlinks entirely — plain text is the failsafe.

### Filename
- Pattern: `Resume_{Company}_{Role}_{YYYY-MM-DD}.docx`
- Strip spaces, slashes, ampersands, and special characters from company/role tokens; replace with underscores. Example: `Resume_StripeInc_SeniorBackendEngineer_2026-06-18.docx`.
- Stick to `.docx` (not `.doc`, not `.pages`, not `.odt`).

### File format priority
- **.docx** parses best in nearly all ATS — default.
- **.pdf** is fine for human readers, but some older ATS still mangle PDFs (especially custom fonts or PDF/A variants). Only use if the JD asks for PDF.
- Never `.doc`, `.pages`, `.odt`, or image-based PDFs.

## Human-reader rules

A recruiter spends ~7 seconds on first pass. Engineer the document for those seconds:

- **Top third matters most.** Name, contact, summary, and the first bullet of the most recent role need to land in the top third of page one. The most-JD-relevant bullet goes first inside the most-recent role.
- **Scannable visual hierarchy.** Section headings stand out clearly. Role / company / dates follow a consistent visual pattern down the page.
- **Bold strategically.** Bold the role title (consistent choice — title OR company, pick one). Don't bold inside bullet text.
- **Whitespace.** Don't pack bullets tight. A breathing resume reads as confident, not padded.

## Section ordering by seniority

**Early career (0–3 YOE, recent grad):**
1. Contact
2. Summary (optional — skip if it'd just be filler; objective only for career change)
3. Education
4. Experience
5. Projects (if strong)
6. Skills

**Mid-career (3–10 YOE):**
1. Contact
2. Summary
3. Experience
4. Skills
5. Projects (only if relevant to the JD)
6. Education

**Senior (10+ YOE):**
1. Contact
2. Summary
3. Experience
4. Skills
5. Education (compressed — degree, school, year)

Drop Projects entirely once your work experience is the strongest signal — they're a junior/mid signal.

## Length

- **1 page** if <10 YOE.
- **2 pages** if 10+ YOE OR substantive research/publications/patents.
- **Never 1.5 pages.** Either fill the bottom half of page 2 cleanly or trim to 1.

## What NOT to include

- Photo (US convention; varies internationally — only if local norm requires)
- Date of birth, marital status, nationality, religion, citizenship (unless the role legally requires)
- Street address (city, state only)
- Phone country code if applying domestically
- "References available upon request" (assumed; wastes a line)
- High school (once you have a college degree)
- GPA below 3.5 (or after your first job, regardless)
- Soft-skill self-claims without evidence ("team player", "hard worker")
- Personal interests unless directly relevant to the role
- Salary expectations / desired comp
- A career objective unless changing careers (use Summary instead)

## .docx generation spec

When generating the `.docx`:

1. **Linear single-column layout.** No two-column tricks.
2. **Standard section headings** from the whitelist above.
3. **Fonts**: Calibri or Arial. Body 11pt, subheadings 12pt, name 15pt. One font family throughout.
4. **Margins**: 0.7" all sides.
5. **Bullet character**: `•` (filled bullet). Hanging indent so wrapped lines align under the first character of the bullet text, not under the bullet itself.
6. **Section headings**: bold, slightly larger, optional thin bottom border line — but no text box for the heading.
7. **Role line**: role title bold; company, city, dates on the same line in regular weight. Dates can be right-aligned via a right tab stop if it renders cleanly across the page.
8. **Line spacing**: 1.0–1.15 in body, with a slightly larger space before section headings.
9. **No headers, no footers.** Page number is OK only on a 2-page resume — and only in the body, not in the page footer region.
10. **Contact info** as a single line directly under the name OR as a small block — plain text, in the body, not in the document header.
11. **Hyphens and en-dashes**: en-dash (–) for date ranges; hyphen (-) for compound words.
12. **No smart quotes** for technical terms (some ATS swap them oddly). Plain quotes for code/tool names.
13. **No track changes, no comments, no metadata.** Save a clean copy.

## Pre-delivery self-check

Before declaring the resume done, verify every item. Revise on any failure:

- [ ] All Tier-1 keywords from the rubric appear at least once IF the user has them
- [ ] No invented metrics, skills, titles, dates, or scope
- [ ] Verb tense consistent: past for past roles, present for current
- [ ] Date format consistent throughout (one format, used everywhere)
- [ ] Bullet punctuation consistent (all periods or all none)
- [ ] No vague verbs ("handled", "did", "worked on", "helped")
- [ ] No "Responsible for", no "Successfully", no "Utilize"
- [ ] No first-person pronouns
- [ ] Section headings on the whitelist
- [ ] Single column, no tables / text boxes / images / icons
- [ ] No contact info in document header or footer
- [ ] Length matches target (1 page or 2 pages, never 1.5)
- [ ] Top third of page 1 = name, contact, summary, first bullet of most recent role
- [ ] Most-JD-relevant bullet is the first bullet of the most recent role
- [ ] Skills section ordered with JD-relevant skills first
- [ ] Filename follows the `Resume_{Company}_{Role}_{YYYY-MM-DD}.docx` pattern with stripped specials
- [ ] No track-changes or comments left in the file
