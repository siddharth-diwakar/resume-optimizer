# My Tracker Columns  (optional — but speeds up logging)

> Fill this in to tell the skill where your tracker lives and what columns it expects.
> The skill ALWAYS reads the live header row too — if your sheet has changed since
> you wrote this file, the live sheet wins and the skill flags the drift.
> Leave any field blank to fall back to live reading.

## Sheet name or link
[paste your Google Sheet's name or URL here]

## Date format used in the sheet
[e.g. MM/DD/YYYY — match whatever your existing rows use.]
[If your sheet is empty, the skill defaults to YYYY-MM-DD.]

## Columns (in the order they appear in your sheet)
For each column, write the exact header text and what should go in it.
The skill cross-checks this against the live header row; on divergence, the live sheet wins.

- Company → hiring company name
- Job Title → the role title from the posting
- Date Applied → today's date
- Status → "Applied" on first entry; updated on status changes (OA / Interview / Offer / Rejected)
- URL → posting link (if provided)
- [Your custom column, e.g. Source] → [e.g. LinkedIn, referral, careers page]
- [Your custom column, e.g. Salary range] → [only fill if the posting states one explicitly]
- [Your custom column, e.g. Files] → [tailored resume / cover letter filename]
- [Your custom column] → [what goes here]
