---
author: Adam Sawyer
date: "2026-09-04T10:00:00-04:00"
summary: 76% of small businesses report using AI; 14% have it embedded in operations. Five steps that close the gap, with the numbers and the exact prompts.
draft: false
hidemeta: false
showToc: true
tags:
  - ai
  - small-business
  - first-steps
title: "AI First Steps for a Small Business"
weight: 2
---

The state of small-business AI in 2026, in four numbers:

- **76%** of small businesses report using AI ([Goldman Sachs 10,000 Small Businesses survey](https://www.goldmansachs.com/citizenship/10000-small-businesses/US/voices), n=1,256, early 2026)
- **14%** have it embedded in core operations (same survey)
- **Under 20%** pass the Census Bureau's stricter test — AI doing real production work ([BTOS](https://www.census.gov/data/experimental-data-products/business-trends-and-outlook-survey.html))
- **50%+** name "not knowing where to start" as their top barrier ([2026 adoption survey](https://stateofaiforsmallbusiness.com/statistics/))

Translation: most businesses have tried AI; few have put it to work. The gap is sequencing, not software. Here's the order that closes it, with the tradeoffs stated and the prompts to copy — I'm not selling any of the tools named below.

### 1. Pick one boring task

A task, not a tool. Qualifying tasks have three traits: repetitive (same shape weekly), text-based, and cheap to get wrong (you review the output anyway).

The trait list isn't a guess — it describes what AI-using small businesses report succeeding with. [NFIB's 2026 survey](https://www.nfib.com/) puts marketing content (68%), customer communication (52%), and administrative tasks (47%) at the top: all repetitive text work. Ruled out for a first task: anything that reaches a customer without review, anything with legal or medical weight.

Three qualifying tasks, with the prompt for each:

```text
MONTHLY REVIEW SUMMARY
Here are this month's customer reviews from Google and Yelp.
Summarize: (1) what got praised most, (2) what got complained
about most, (3) whether complaints cluster by day, shift, or
item, (4) anything mentioned this month that wasn't mentioned
last month. Quote the reviews you're drawing from.

[paste reviews]
```

```text
BOOKING REPLY DRAFT
You draft replies for [business name]. Facts you may use, and the
only facts you may use: [hours, prices, policies, what to bring,
weather/cancellation policy]. Draft a reply to the email below in
a friendly, plain tone, under 120 words. If the email asks
anything not covered by the facts above, write [OWNER: ...] where
my answer goes instead of guessing.

[paste customer email]
```

```text
VOICE NOTE TO SERVICE RECORD
Below is a transcribed voice note from a technician after a job.
Convert it to a service record with fields: date, address, system
type, work performed, parts used, follow-up needed, quote given.
Mark any field the note doesn't cover as MISSING — do not fill
gaps with guesses.

[paste transcription]
```

Note what two of those prompts do explicitly: they forbid guessing and force gaps to be flagged. That's not style — it's the guard against the failure documented in step 3. The 76/14 gap above is the tool-first failure measured at national scale; task first inverts it.

### 2. Pay for one general assistant

Start with a general assistant, not a specialized product — the AI receptionist and AI bookkeeper are largely general models resold at markup. Spending data says this is what businesses do anyway: the [JPMorgan Chase Institute](https://www.jpmorganchase.com/institute) measured median small-business AI spend at **$28/month** in 2025, down from $80 in 2022. One subscription.

The three real options, each ~$20/month at the individual tier:

- **ChatGPT** — largest user base, most tutorials, most capable all-arounder. Flaw: states errors with the same confidence as facts.
- **Claude** — strongest on long documents and natural prose. Same category flaw: errs, and errs politely.
- **Gemini** — the pick if you already run on Gmail/Google Docs, because it's embedded there.

Free tiers are demos. Paid tier, one month, one task from step 1 — your whole bet is about the national median spend.

### 3. Put a person between the AI and anything that matters

Rule, stated once to your team: *the AI drafts, you decide, your name is on it.* Every output reaching a customer, a book of record, or a legal document gets a responsible human.

Why you can't skip this step: every current model states falsehoods with full confidence — the industry calls it hallucination — and no vendor's model is free of it. Legal record: in *Mata v. Avianca* (S.D.N.Y. 2023), lawyers filed a brief containing six AI-invented cases with fabricated quotes; the court fined them $5,000. Courts have sanctioned dozens of similar filings since. The failure in every case was the same: no human check between the model and the consequence.

The review itself can be a 30-second checklist rather than a re-read:

```text
Before sending any AI draft, check three things:
1. FACTS  — every price, date, name, and promise: is it ours?
2. GAPS   — any [OWNER: ...] or MISSING flags left unresolved?
3. VOICE  — would I say this sentence to this customer out loud?
Fix or delete. Never send on autopilot.
```

If a task can't get a reviewer, it isn't ready for AI. Return to step 1.

### 4. Write down what you'll never feed it

One page, before staff adopt the habit unsupervised. Two lists:

**Never:** customer payment data, anything medical, employee records, passwords, anything covered by a confidentiality clause.
**Fine:** anything you'd hand a temp on day one — public prices, FAQ answers, marketing drafts.

Then verify one setting: whether your account tier uses your conversations for model training. Business tiers generally exclude training by default; consumer tiers vary by vendor and change over time. Check the provider's current data-controls page — five minutes — rather than relying on any blog post, including this one.

### 5. Expand only after a month of review

One task, one month, every output reviewed. Then decide with data: time saved versus review time spent.

The numbers side with patience: **93%** of small-business AI users report positive impact (Goldman Sachs, above), yet only 14% reach embedded use, and an [SBA Office of Advocacy review](https://advocacy.sba.gov/) found about half of AI-using small firms invested nothing in training or integration. Liking the tool is common; putting it to work is rare, and the review month is what separates them.

Run the month-end verdict as its own prompt:

```text
For the past month I used AI for this task: [task]. Here's what
happened: [outputs kept vs. rewritten, roughly minutes saved or
lost per use, mistakes caught in review].

Give me a verdict: keep, kill, or adjust — and argue against
keeping it before you argue for it. If keep: what's the next task
with the same traits (repetitive, text, cheap to get wrong)?
```

If the task survived: add one more with the same three traits. If not: cancel, out ~$28 and one month. This is also when you can judge the specialized tools — you now know what the general assistant does for a tenth of their price.

## Conclusion

Task, tool, review rule, data rule, expansion — ordered so mistakes stay cheap. Total cost to run the sequence: about the national median spend and a month of attention. The 14% didn't buy more software than the other 62 points of the gap; they picked tasks and kept what worked.

Where the order breaks for your business, [tell me](/about) — revisions to this guide come from those reports.
