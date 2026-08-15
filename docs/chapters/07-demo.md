---
title: 7. The Demo — A Squad Clears a Backlog Item
description: Walking through an assign to code to review to merge loop.
---

# The Demo: A Squad Clears a Backlog Item

<div class="hero-banner">
  <img src="../../assets/images/8-demo.webp"
       alt="A tablet on a marble table shows an approved GitHub pull request titled Rule Zero, next to a Vietnamese drip coffee set labelled Saigon Coffee, with a city skyline at dusk in the background."
       width="1448" height="1086" loading="eager">
  <p class="hero-banner__caption">Demo: Watch a Squad Clear a Backlog Item</p>
</div>

<div class="chapter-meta">
  <span class="chapter-meta__tag">Demo</span>
  <span class="chapter-meta__tag">Coding agent</span>
  <span class="chapter-meta__tag">Rubber Duck</span>
</div>

## What the live demo showed

The talk's demo was deliberately unscripted: a real backlog issue, assigned live to GitHub Copilot's coding
agent, with a second agent reviewing the resulting pull request before a human made the final call. The
point wasn't to show a trick — it was to show the ordinary, repeatable loop that Chapters 5 and 6 describe
in the abstract, running end to end.

## The loop, step by step

1. **Assign** — a scoped issue with clear acceptance criteria is assigned to the coding agent, the same way
   you'd assign it to a teammate. See [About Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent).
2. **Code** — the agent works in its own environment, makes the change, runs the existing test suite, and
   opens a draft pull request describing what it did and why.
3. **Review (agent)** — a second agent — the Rubber Duck from [Chapter 5](05-fleet-squad.md) — reviews the
   diff against the repository's conventions and the linked issue, flagging anything inconsistent before a
   human's attention is spent. [Copilot code review](https://docs.github.com/copilot/how-tos/copilot-on-github/use-copilot-agents/copilot-code-review)
   can run exactly this pass automatically on pull requests.
4. **Review (human)** — a person reads the diff, checks the flagged points, confirms CI is green against
   required status checks, and decides whether it's actually correct — not just plausible.
5. **Merge** — the human approves. As the demo put it: *"I checked the diff. I own this merge."* That
   sentence is Rule Zero, said out loud, at the exact moment it matters.

## Why the sequence matters, not just the tools

The value isn't "an agent wrote code" — that's table stakes now. The value is the **sequence**: scoped
assignment → agent execution → automated + agent review → human accountability, all inside the same pull
request workflow your team already uses for human-authored changes. Nothing about branch protection, required
reviews, or CI changes. The unit of work changed; the governance around it didn't have to be reinvented.

## Exercise: run this loop on one real ticket

Pick one item from your "agent-ready today" tier (from [Chapter 6](06-backlog.md)'s exercise). Assign it to
a coding agent, turn on an automated code review pass, and time the full loop from assignment to your own
merge decision. Write down what you actually checked before merging — compare it against your team's Rule
Zero statement from [Chapter 2](02-rule-zero.md) and see if they match.

## Further reading

- [About Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent) — GitHub Docs
- [Using GitHub Copilot code review](https://docs.github.com/copilot/how-tos/copilot-on-github/use-copilot-agents/copilot-code-review) — GitHub Docs
- [GitHub Copilot coding agent 101: getting started with agentic workflows on GitHub](https://github.blog/ai-and-ml/github-copilot/github-copilot-coding-agent-101-getting-started-with-agentic-workflows-on-github/) — The GitHub Blog
