---
author: Adam Sawyer
date: "2026-09-04T10:30:00-04:00"
summary: AI assistants affirm users roughly 49% more often than humans do. Five countermeasures, ordered by cost, with the evidence and the exact prompts.
draft: false
hidemeta: false
showToc: true
tags:
  - ai
  - sycophancy
  - first-steps
title: "Getting Honest Answers from AI: First Steps"
weight: 1
---

I audited 90 days of my own AI conversations — 33 of them, all real decisions — and scored each one on a single question: did the assistant ever challenge what I asked for, or only execute it? In roughly half the advice conversations, it never challenged anything. It accepted my premise and built on it.

The published research says my sample was typical:

- A [2025 study in *Science*](https://www.science.org/doi/10.1126/science.adt9819) (n=2,405) found AI models back what users did about 49% more often than humans do — including actions involving deception or harm — and people who talked with the agreeable models came away less willing to apologize or patch up conflicts.
- [Anthropic researchers showed in 2023](https://arxiv.org/abs/2310.13548) that training bakes the habit in: models learn from human feedback, and humans rate agreeable answers higher. All five state-of-the-art assistants they tested showed consistent sycophancy.
- In April 2025, [OpenAI rolled back a GPT-4o update](https://openai.com/index/sycophancy-in-gpt-4o/) because it had become too sycophantic — the vendors acknowledge the problem by name.
- A [2026 study](https://arxiv.org/abs/2605.16288) measured how the effect scales: the more a question begged for approval, the worse the answers got, across all four major models tested (correlations of −0.54 to −0.73).

The training incentive that causes this hasn't changed, so waiting for better models isn't a plan. Changing how you ask is. Five fixes, ordered by cost, each with the prompt to run.

### 1. Score your own history

Open your last five advice conversations. For each: did the AI ever question the premise, or only deliver on it? Ten minutes, and the research stops being about other people's chats and starts being about yours.

The research names the forms this takes: agreement with your stated opinion; reversal of a correct answer after you push back ("are you sure?"); and the subtlest form, the one my audit caught most — a *how* question answered beautifully with no examination of *whether*. A polished pricing framework is not evidence that the thing should be priced.

To score at scale, paste a past conversation into a *fresh* chat with:

```text
Below is a transcript of a conversation I had with an AI assistant.
Score it on one question: did the assistant ever challenge my premise,
assumptions, or framing — or did it only execute what I asked?

Cite the specific messages that support your score. Then list every
premise I brought that went unexamined.

[paste transcript]
```

A fresh chat matters: the model grading has no stake in the framing the original model absorbed.

### 2. Convert *how* questions to *whether* questions

- "How should I price this service?" → "Should this service exist? Argue both sides. Price it only if it survives."
- "How do I fix my marketing?" → "Is marketing my actual problem? What else explains flat sales?"
- "Help me plan the launch" → "What would have to be true for this launch to be a mistake?"

A reusable template:

```text
I'm about to ask you to [task]. Before you do it:

1. State the premises hidden in my request.
2. Give the three strongest reasons the premise is wrong or the
   task shouldn't be done at all.
3. Tell me which of those reasons survives your own scrutiny.

Only then, if the premise holds, do the task.
```

This runs the 2026 finding in reverse: models track what the question signals you want. Beg for approval and quality drops; ask for challenge and you get it. Cost: one sentence per question.

### 3. Require a pre-mortem before any plan

The technique is Gary Klein's, built for human teams that stop hunting flaws once they're invested. Applied to AI it produces specifics — a first domino you can verify today — instead of the generic risk lists that direct critique requests return.

```text
Here is my plan: [plan].

Assume it is twelve months from now and the plan failed completely.
Write the story of the failure as a narrative, not a risk list:
what broke first, what that caused, and what I ignored at the start
that I could have checked. Name the single earliest thing I could
verify this week that would have predicted the failure.
```

I run one on every decision with money or months attached; a pre-mortem reordered my own consulting plan this year.

### 4. Put skepticism in your standing instructions

Every major assistant supports persistent instructions (custom instructions, memory, project files). Mine, condensed to what's paste-able:

```text
Standing rules for advice and planning conversations:
- Challenge my premises before executing on them. If my question
  assumes something unproven, say so first.
- If my plan has a hole, name it before helping with the plan.
- Don't soften bad news or pad criticism with reassurance.
- When I'm clearly excited about an idea, treat that as a reason
  for MORE scrutiny, not less.
```

Per-question techniques fail on the days you're too invested to use them — which my audit showed were exactly the conversations that needed them. A standing order removes the decision. Tradeoff: the pushback will sometimes be wrong or tiresome. Adjust tone, keep the trigger.

### 5. Cross-examine with a second model

For high-stakes decisions: hand model A's answer to model B — different vendor — with:

```text
An AI assistant produced the analysis below. Your job is to attack this
analysis, not summarize it. Find: (1) factual claims that may be invented
or wrong, (2) assumptions treated as facts, (3) arithmetic or logic
errors, (4) the weakest link in the chain of reasoning. Do not
evaluate my underlying goal — attack the analysis only.

[paste analysis]
```

Sycophancy attaches to the *user's* framing; a rival model's output arrives without it and gets graded accordingly. In my use this caught buried assumptions, arithmetic errors, and one invented fact the earlier steps missed. Cost: a second subscription and more reading, which is why it's last.

## Conclusion

Five steps, cheapest first: measure, reframe, pre-mortem, standing orders, cross-examination. The system that affirms users 49% more than humans do will attack a premise with the same competence. It waits to be asked.

Full audit writeup — method, scoring, numbers — coming as its own post. Run step 1 first; if your ratio surprises you, [tell me](/about).
