# Cover Letter Guide

The cover letter is **not** a prose version of the resume. The resume answers "what did you do?" The cover letter answers "how do you work, and would I want you on my team?"

## Philosophy

A hiring manager reads cover letters to answer two questions:
1. **Can they do the job?** (the resume mostly answers this; the cover letter confirms with ONE strong story)
2. **Do I want to work with them?** (only the cover letter can answer this — behavioral signal, judgment, voice)

So: pick ONE specific metric from the resume that maps to the JD's biggest need, and tell the story behind it — emphasizing the *how* and the *why*. Then say what the user values in a team and why this team specifically.

Resume-dump cover letters fail because they answer #1 redundantly and skip #2.

## Structure (in this order)

Total length: 250–350 words. Four parts.

### 1. Hook (~50 words, one short paragraph)
- Tied to something specific about the company/role/team — a product, a recent launch, a stated value, a problem the team is publicly working on.
- If you don't have a signal source, ask the user to paste 1–2 sentences from the company's careers page, About page, or a recent blog/launch post. Mirror that register.
- NOT acceptable hooks: "I am writing to apply for", "I was excited to see", "Your company has a strong reputation".

### 2. Anchor story (~150–180 words, one paragraph)
ONE STAR-shaped mini-story from the resume. Selection rules below. Proportions inside the paragraph:
- **Situation** (~15%): what was going on, in one sentence.
- **Task** (~10%): what the user owned, in one sentence.
- **Action** (~55%): what the user actually did — choices, tradeoffs, who they worked with, what they had to figure out. This is where behavior shows up.
- **Result** (~20%): the specific metric from the resume, plus the second-order outcome (what it unlocked for the team / company / next project).

This is the ONLY place a resume metric appears. Pick ONE — the one most relevant to the JD's stated priorities. Don't list more.

### 3. Why me + why fit (~80 words, one paragraph)
Qualitative. No new metrics. Cover:
- What the user is optimizing for in their next role (e.g., "want to go deeper on payments infra after surfacing it at Acme").
- Why this team / company specifically (echo the hook signal from step 1, but with a different angle).
- What they bring as a teammate — phrased as behaviors, not adjectives. "Run weekly office hours for juniors" beats "I'm collaborative". "Write the design doc before the code" beats "I'm thoughtful".

### 4. Close (~20 words, one sentence)
Confident, forward-looking, no clichés. NOT "I look forward to hearing from you" or "Thank you for your consideration". Something like: "Happy to walk through the [X] migration in more detail — it's the closest thing in my work to what [Team] is shipping now."

## How to pick the anchor story

Given a JD and a master resume:

1. **Identify the top behavioral signal in the JD.** Look at responsibilities + "you'll" + "what we're looking for". Common signals to scan for:
   - Ownership / autonomy ("own the X end-to-end", "drive", "ship")
   - Cross-team collaboration ("partner with", "work across", "stakeholders")
   - Ambiguity tolerance ("0→1", "early stage", "define the problem")
   - Mentorship / leverage ("mentor", "raise the bar", "uplevel")
   - Customer-facing judgment ("user research", "talk to customers")
   - Technical depth in a specific area (only if the JD names ONE specific thing repeatedly)
   - Operational maturity ("on-call", "incidents", "reliability")

2. **Find the bullet in the resume whose metric best demonstrates that behavior.** Not the most impressive metric — the most *relevant* one. A 38% latency drop is a worse anchor than a 4% improvement if the 4% one demonstrates the right behavior more clearly.

3. **Reconstruct the *how* with the user's help if needed.** The resume has the metric; the cover letter needs the choices behind it. If the resume bullet is thin on context, ASK the user: "What was the first thing you tried? Who pushed back? What did you almost miss?" Then turn that into the Action portion.

4. **Map the result to a second-order outcome.** The metric is necessary but not sufficient. "Cut p99 38%" is the *what*; "unblocked the checkout team from rewriting the gateway" is the *why it mattered*. Both go in.

## Behavioral skill bank (use these as the lens for the Action portion)

- **Initiative**: noticed something nobody asked them to fix.
- **Judgment**: chose option B over A and can articulate the tradeoff.
- **Collaboration**: pulled in the right person at the right time.
- **Communication**: wrote the doc, ran the meeting, surfaced the risk early.
- **Resilience**: shipped despite a setback, learned and adjusted.
- **Ownership**: handled it end-to-end, including the parts that weren't fun.
- **Mentorship**: made someone else better at their job.

Pick the 1–2 that the JD rewards most. Don't claim all of them.

## Voice and tone

- Conversational, not corporate. Contractions OK ("I've", "it's").
- First person. Past tense for the story; present tense for what the user values now.
- No buzzwords: "passionate", "team player", "results-driven", "synergize", "go-getter", "wear many hats", "fast-paced environment".
- No hedging: "I believe I could potentially be a fit." Say "I'd be a strong fit because" or don't say it at all.
- Match the company's register. Stripe → crisp + precise. A consumer brand → warmer. A research lab → curious + specific.
- It should sound like the user, not a template. If the user has a distinctive turn of phrase from chat, borrow it.

## Anti-patterns (don't do)

- **The resume-in-prose**: "In my role at X, I did A, B, and C. In my prior role at Y, I did D, E, and F." Stop. Pick ONE.
- **The metric drive-by**: dropping three numbers in three sentences with no story behind them.
- **The compliment sandwich**: opening paragraph of company praise with no specifics. "Your innovative culture and commitment to excellence" — cut it.
- **The throat-clearing intro**: "I am writing to apply for the [Role] position at [Company]." The header tells them. Skip it and open with the hook.
- **The wish-list close**: "I hope to hear from you soon. Thank you for considering my application." Replace with one confident, forward-looking sentence.
- **The personality dump**: "I'm a passionate, hardworking, detail-oriented self-starter." Adjectives are free; behaviors are evidence. Show one behavior instead of claiming five traits.

## Before delivering, self-check

Re-read against these. If any answer is "yes" or "I don't know", revise:
- Could this letter be sent to a different company with only the company name swapped? → too generic.
- Is more than one metric quoted? → cut to one.
- Does the "why me" paragraph contain adjectives but no behaviors? → rewrite as behaviors.
- Does the hook reference something the user couldn't have known without 30 seconds of company research? → if not, find a more specific hook.
- Is the close a cliché? → replace.

## Worked example (Acme Pay → payments-infra role at Stripe)

> The Subscription Billing team's recent post on idempotency at scale was what got me to apply — that's the exact failure mode I spent six months unwinding at Acme Pay, and it's the kind of problem I want to keep working on.
>
> At Acme, our checkout p99 had drifted to 820ms and was blocking the gateway team's rewrite. I owned the investigation. The obvious fix — a Redis cache — was off the table at first because security flagged PII in the cached objects. So I worked with the security lead to define a redacted shape, wrote a one-page design doc the team could critique before I built anything, and shipped behind a feature flag at 1% → 10% → 100% over two weeks. P99 dropped 38% (820ms → 510ms), zero incidents, and the gateway team unblocked their rewrite a sprint earlier than planned. The thing I'm proudest of isn't the latency number — it's that the security review took two days instead of two weeks because I came in with the redaction shape, not the request.
>
> What I'm optimizing for in my next role is going deeper on payments infra in an environment where the failure modes are the interesting part of the work — Stripe's writing the textbook on this, which is why I want to be here. The way I tend to add value on a team is by writing the design doc before the code and running office hours for junior engineers; I'd want to keep doing both.
>
> Happy to walk through the redaction-shape design in more detail — it's the closest thing in my work to what your team is shipping now.

Word count: ~310. One metric. One story. Three behaviors shown (initiative, cross-team collaboration, iterative rollout). Hook tied to a specific company artifact. Close is specific, not generic.
