# Keyword Tiering Rubric

Use this when extracting keywords from a job posting. Tiers drive what gets mirrored verbatim, what gets paraphrased, and what gets skipped.

## Tier 1 — Must-Have (mirror verbatim)
A keyword belongs in Tier 1 if ANY of these are true:
- Listed under "Requirements", "Must have", "Qualifications", or "You have"
- Repeated 2+ times across the posting
- Named in the job title

Treatment:
- Use the posting's EXACT wording. If the JD says "Docker", don't write "containers". If it says "TypeScript", don't write "TS" or "JavaScript".
- Land Tier-1 keywords in the resume Summary and the bullets of the most recent role.
- Every Tier-1 keyword should appear at least once in the tailored resume IF the user actually has it.

## Tier 2 — Should-Have (paraphrase OK)
- Listed under "Responsibilities", "You will", or "Day to day"
- Listed once in qualifications without "required" framing

Treatment:
- Hit these where they fit; light paraphrasing fine.
- Group related Tier-2 items into a single bullet rather than padding.

## Tier 3 — Bonus (only if truthful AND space allows)
- Listed under "Nice to have", "Bonus", "Pluses", "Preferred"
- Inferred from the company's stack, domain, or recent posts

Treatment:
- Include only if the user has it AND there's still room within target length.
- Never crowd out a Tier-1 or Tier-2 keyword for a Tier-3 one.

## Output format
Before showing the tailored resume, produce a table:

| Tier | Keyword | In my resume? | Notes |
|------|---------|---------------|-------|
| 1 | Docker | yes | Acme role |
| 1 | Kubernetes | gap | recommend reframe → "container orchestration via ECS" |
| 2 | observability | yes | already in Skills |
| 3 | gRPC | yes | covered in Summary |

Then list each gap with the recommended action (see SKILL.md → "Gap handling").

## Anti-patterns (don't do)
- **Keyword stuffing.** Cramming every Tier-1 word into one bullet to game ATS. Modern ATS weighs by context; recruiters spot it instantly.
- **Inventing experience** to close a gap. Flag it; don't fake it.
- **Burying Tier-1 keywords on page 2.** They go up top — Summary and most-recent-role bullets.
- **Generic synonyms.** "Cloud" instead of "AWS". "Scripting" instead of "Python". Be specific when the posting is specific.
