---
title: 8. The 2-5 Year Business Cliff
description: Why the constraint shifts from picking two projects to governing all ten.
---

# The 2–5 Year Business Cliff

<div class="hero-banner">
  <img src="../../assets/images/9-horizon.webp"
       alt="A person stands at a fork in a path: a foggy dead-end road on the left signed Dead End, and a sunlit path toward a glowing city skyline on the right, under the heading The 2-5 Year Business Cliff - The path you choose today shapes the future you lead."
       width="1448" height="1086" loading="eager">
  <p class="hero-banner__caption">The 2–5 Year Business Cliff</p>
</div>

<div class="chapter-meta">
  <span class="chapter-meta__tag">Strategy</span>
  <span class="chapter-meta__tag">Platform engineering</span>
  <span class="chapter-meta__tag">Business impact</span>
</div>

## The old constraint: pick two of ten

Every engineering leader has run this exercise: ten good ideas, budget and headcount for two or three of
them this year. The scarce resource was human engineering time, so the discipline was ruthless prioritisation
and the organisations that prioritised well won, because execution capacity was the bottleneck everyone
shared.

## The new constraint: govern all ten, not pick two

Agentic engineering doesn't remove the need for prioritisation, but it does change what the bottleneck is.
When scoped, low-ambiguity implementation work can be parallelised across a Fleet (see [Chapter 5](05-fleet-squad.md)),
the limiting factor stops being "how many engineers do we have to write code" and starts being "how much
governed, reviewed capacity do we have to safely merge and operate the result." Teams that only optimise for
generation speed and don't invest in the review, security, and observability side hit a different wall: not
too little code, but too much unreviewed or ungoverned code.

The window this creates is real but time-bound. Organisations that build the governance muscle - the
required reviews, the CODEOWNERS routing, the audit trail, the risk-tiered backlog triage from earlier
chapters - early, are positioned to run more of their ten projects concurrently with the same team, rather
than picking two. Organisations that only adopt the generation speed without the governance either stall on
review backlog, or worse, ship the unreviewed kind of mistake described in [Chapter 2](02-rule-zero.md)'s
anecdote.

## What "doing all ten" actually requires

- **A backlog triage discipline** (Chapter 6) so agent capacity is spent on the right things, not just more
  things.
- **A review pipeline that scales with volume** (Chapters 3 and 5) - agent-assisted first-pass review plus
  a human accountable for the final call, not a human trying to read every line of exponentially more diffs
  alone.
- **A control plane view across the whole portfolio** ([Chapter 9](09-control-plane.md)) so leadership can
  see agent activity, policy compliance, and risk concentration across all ten projects, not just the one
  someone happens to be looking at.
- **Token and cost discipline** (Chapter 5) so running more concurrent work doesn't quietly become
  unsustainably expensive.

## Exercise: re-run your prioritisation exercise

Take your team's current "pick two of ten" list. For each of the ten, estimate honestly: how much of the
implementation work is scoped and low-ambiguity enough to parallelise across agents today, and how much
requires judgement-heavy human work regardless of tooling? Projects that are mostly the former are strong
candidates to run *alongside* your chosen two, provided your review and governance capacity can absorb the
extra volume - which is the real test of whether you're ready for this shift.

## Further reading

- [Agentic DevOps: evolving software development with GitHub Copilot and Microsoft Azure](https://azure.microsoft.com/en-us/blog/agentic-devops-evolving-software-development-with-github-copilot-and-microsoft-azure/) - Microsoft Azure Blog
- [Optimize DevOps with AI agents on Azure](https://learn.microsoft.com/en-us/training/paths/optimize-devops-ai-agents-azure/) - Microsoft Learn
