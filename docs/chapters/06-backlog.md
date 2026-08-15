---
title: 6. The Backlog Has No Bottom
description: Triage patterns for handing low-risk backlog items to agents.
---

# The Backlog Has No Bottom

<div class="hero-banner">
  <img src="../../assets/images/7-backlog.webp"
       alt="A person moves sticky notes on a transparent Kanban board with columns Triaged, In Progress and Done, each card labelled with a task and AI agent, next to a physical backlog card stack, under the heading The Backlog Has No Bottom — Until Now."
       width="1448" height="1086" loading="eager">
  <p class="hero-banner__caption">The Backlog Has No Bottom — Until Now</p>
</div>

<div class="chapter-meta">
  <span class="chapter-meta__tag">Backlog management</span>
  <span class="chapter-meta__tag">Product ownership</span>
  <span class="chapter-meta__tag">Azure DevOps</span>
</div>

## Every backlog has a graveyard

Every team has the same graveyard: "fix flaky test," "update dependency," "improve logging," "investigate
alert" — small, valuable, endlessly deprioritised in favour of feature work with a deadline attached. Not
because they don't matter, but because a human's time is the scarcest resource and they always lose to
customer-facing pressure. That graveyard is exactly the class of work coding agents handle well: bounded
scope, existing tests to validate against, low ambiguity, low blast radius.

## A triage model, not a free-for-all

Handing the whole backlog to agents unsupervised isn't the goal — you'd just move the accountability problem
from "wasn't done" to "was done badly, and someone still has to clean it up." A workable triage model:

1. **Score for risk, not just size.** A one-line change to a payment calculation is higher risk than a
   two-hundred-line change to a test-only utility. Route by risk, not lines-of-diff.
2. **Product owner or lead assigns, doesn't just auto-dispatch.** A human still decides *which* items are
   low-risk enough to hand to an agent this sprint — this keeps a person accountable for the queue, not just
   the individual merge (Rule Zero, applied to planning as well as review).
3. **Every agent-drafted change still goes through the same PR pipeline** — required reviews, CI, and (per
   [Chapter 5](05-fleet-squad.md)) ideally a reviewer agent pass before a human looks at it.
4. **Track outcomes, not just throughput.** If agent-drafted PRs in a risk tier start needing unusually heavy
   rework, that's a signal to tighten the tier's scope, not a reason to stop measuring.

## Where this fits in Azure DevOps or GitHub

- In **Azure Boards**, tag work items with a risk/complexity field so triage is explicit and queryable rather
  than tribal knowledge.
- In **GitHub**, assign a well-scoped issue directly to Copilot's coding agent, which opens a draft pull
  request and iterates against your existing CI checks — see [About Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent).
- Keep the **definition of ready** stricter for agent-assigned work than you might for a human: a clear
  reproduction, acceptance criteria, and the specific files/paths in scope reduce the ambiguity that produces
  low-quality agent output.

## Exercise: tier your own backlog

Pull your team's backlog and sort the bottom 20 items (the ones that never get picked up) into three tiers:
**agent-ready today** (clear repro, low blast radius, good test coverage already exists), **agent-ready with
more spec work** (valid candidate, but the ticket needs a clearer acceptance criteria first), and **human
only** (judgement-heavy, high blast radius, or under-specified in a way only a conversation can fix). Most
teams find tier one is bigger than they expected.

## Further reading

- [About Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent) — GitHub Docs
- [Optimize DevOps with AI agents on Azure](https://learn.microsoft.com/en-us/training/paths/optimize-devops-ai-agents-azure/) — Microsoft Learn
