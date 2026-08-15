---
title: 5. Agentic Workflows - The Fleet and The Squad
description: Two operating models for orchestrating multiple agents.
---

# Agentic Workflows: The Fleet and The Squad

<div class="hero-banner">
  <img src="../../assets/images/6-agentic.webp"
       alt="A person orchestrates a row of glowing agent figures labelled Coder Agent, Test Agent, Docs Agent and Deploy Agent on the left (The Fleet), and Architect Agent, Reviewer Agent and Security Agent on the right (The Squad), under the heading Agentic Workflows: The Fleet / The Squad - You orchestrate. Agents execute."
       width="1448" height="1086" loading="eager">
  <p class="hero-banner__caption">Agentic Workflows: The Fleet / The Squad</p>
</div>

<div class="chapter-meta">
  <span class="chapter-meta__tag">Operating model</span>
  <span class="chapter-meta__tag">Multi-agent</span>
  <span class="chapter-meta__tag">Fleet</span>
  <span class="chapter-meta__tag">Squad</span>
  <span class="chapter-meta__tag">Rubber Duck</span>
</div>

## Two patterns, one principle: you orchestrate, agents execute

Agentic engineering doesn't mean one assistant in one editor tab. In practice it splits into two
complementary operating models, and most mature teams end up using both depending on the shape of the work.

### The Fleet - parallel execution at scale

The Fleet pattern runs multiple specialised agents **in parallel**, each responsible for a distinct concern:
a coder agent, a test agent, a docs agent, a deploy agent. Each works its own lane concurrently against the
same task, and the human orchestrator merges their outputs into a coherent change. This is the right pattern
when the work decomposes cleanly into independent tracks - implementation, tests, and documentation for the
same feature can genuinely proceed in parallel once the interface is agreed.

The failure mode to design against: parallel agents drifting out of sync with each other (the docs agent
describing behaviour the coder agent hasn't implemented yet, or vice versa). Keep the shared contract - the
issue, the interface, the acceptance criteria - as the single source of truth all fleet members read from.

### The Squad - collaborative, goal-driven, reviewed

The Squad pattern is sequential and layered: an architect agent proposes an approach, a coder or coding
agent implements it, a reviewer agent checks the implementation, and a security agent screens for risk
before it ever reaches a human. This is the **Rubber Duck** pattern in its explicit form - one agent's
output is reviewed by a second agent before a human sees it, catching the class of error a rushed human
reviewer might miss on a first pass, without removing the human from the loop entirely.

Squads suit work with real risk of subtle error: anything touching authentication, data migrations,
financial calculations, or anything where "looks right" and "is right" diverge easily.

## Why "Rubber Duck" is the right name for it

Rubber duck debugging is the practice of explaining your code out loud to an inanimate object to force
yourself to notice gaps in your own reasoning. The agentic version formalises that: instead of a human
narrating to a toy, a second agent is given the first agent's diff and asked to find problems with it,
*before* a human's attention - the scarcest resource in the pipeline - is spent. It doesn't replace human
review (see [Chapter 3](03-accountability.md)); it raises the quality of what reaches the human, so their
review time is spent on judgement calls rather than catching typos and obvious omissions.

## Token optimisation: why architecture here isn't free

Every agent in a Fleet or Squad consumes tokens, and cost/latency scale with how much context each agent is
re-fed. Practical patterns that keep multi-agent workflows efficient:

- **Scope context tightly per agent.** A docs agent doesn't need the full test suite in its context window;
  a reviewer agent needs the diff and the relevant surrounding code, not the entire repository history.
- **Cache and reuse shared context** (the issue, the architecture decision, the style guide) rather than
  re-sending it to every agent in the chain.
- **Prefer smaller, faster models for narrow, well-defined sub-tasks** (linting, formatting checks, doc
  generation) and reserve larger models for the steps that need genuine reasoning (architecture proposals,
  security review).
- **Set explicit turn/step budgets** per agent so a stuck agent fails fast and hands back to a human instead
  of looping expensively.

## Exercise: map your next feature to Fleet or Squad

Take a feature currently in your backlog. Sketch which parts decompose into independent, parallel tracks
(Fleet) and which parts have a strict dependency chain with real risk of subtle error (Squad). Most features
are a mix - identify the boundary where your Fleet's outputs need to pass through a Squad-style review gate
before merge.

## Further reading

- [About Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent) - GitHub Docs
- [Using GitHub Copilot code review](https://docs.github.com/copilot/how-tos/copilot-on-github/use-copilot-agents/copilot-code-review) - GitHub Docs
- [Agentic DevOps in action: reimagining every phase of the developer lifecycle](https://devblogs.microsoft.com/blog/reimagining-every-phase-of-the-developer-lifecycle/) - Microsoft Developer Blog
