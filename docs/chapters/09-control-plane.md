---
title: 9. GitHub as the Holistic Control Plane
description: Model-agnostic governance for every agent, regardless of which model powers it.
---

# GitHub as the Holistic Control Plane

<div class="hero-banner">
  <img src="../../assets/images/10-controlplane.webp"
       alt="A GitHub logo icon at the centre of a night skyline connects with glowing lines to labelled nodes for OpenAI labs, Anthropic labs, Microsoft Foundry, open source models, custom models and partner models, under the heading GitHub as the Holistic Control Plane - one unified control plane to connect, secure, govern and scale every AI capability across your organisation."
       width="1448" height="1086" loading="eager">
  <p class="hero-banner__caption">GitHub as the Holistic Control Plane</p>
</div>

<div class="chapter-meta">
  <span class="chapter-meta__tag">Governance</span>
  <span class="chapter-meta__tag">Security</span>
  <span class="chapter-meta__tag">Reliability</span>
  <span class="chapter-meta__tag">Model-agnostic</span>
</div>

## Frontier labs innovate; you need one place that governs all of it

Model providers - OpenAI, Anthropic, Microsoft Foundry, the open-source ecosystem, and specialised partner
models - are innovating fast and independently. That's good for capability, but it's a governance problem if
every team picks a different model with its own access pattern, its own audit trail (or lack of one), and
its own security posture. The answer isn't picking a single model and freezing it - it's putting a
consistent **control plane** underneath all of them.

## What "control plane" means in practice

GitHub already holds the primitives that make it a natural control plane for agentic work, independent of
which model is doing the reasoning underneath:

- **Secure by design** - identity, authentication and secret handling are already centralised in GitHub;
  agents authenticate the same way any other automation does, through scoped tokens and app permissions,
  not shared credentials.
- **Policy everywhere** - organisation-level rulesets, required reviewers, and CODEOWNERS apply uniformly
  whether the diff came from a human, a Copilot coding agent, or a custom agent built on a different model.
- **Observable by default** - pull requests, checks, and (for enterprise customers) the [agent control
  plane](https://github.blog/changelog/2025-10-28-enterprise-ai-controls-the-agent-control-plane-are-in-public-preview/)
  give a single place to see what agents did, when, and under whose approval.
- **Identity and access** - GitHub Apps and fine-grained permissions mean an agent's blast radius can be
  scoped precisely (read this repo, open PRs here, never touch that path) rather than granted broad access
  by default.
- **Built for scale** - the same platform that runs CI for thousands of repositories is the one coordinating
  agent-authored changes across all of them.
- **Audit and compliance** - every approval, every required check, every merge is already logged as part of
  the normal Git and pull request history; agentic work inherits that trail rather than needing a parallel
  system.

## Why model-agnostic governance matters more than model choice

Teams change models. New frontier models will keep shipping, and different tasks suit different models -
a fast, cheap model for a docs agent; a stronger reasoning model for an architect or security agent (see
[Chapter 5](05-fleet-squad.md)). If your governance is wired to a specific vendor's dashboard rather than
your own platform, every model change becomes a governance re-implementation project. Anchoring policy,
review, and audit in GitHub (or your existing Azure DevOps environment, applying the same principle) means
the control plane stays constant even as the agents running on top of it evolve.

## Exercise: map your current agent footprint against the control plane

List every AI tool or agent currently touching your codebase - IDE assistants, coding agents, custom bots,
CI-integrated tools. For each, answer: is its access scoped with least privilege? Does its activity show up
in your existing audit trail? Would a required-reviewer rule catch a bad change from it today? Any "no" is a
governance gap to close before adding more agents to the mix.

## Further reading

- [Enterprise AI controls & the agent control plane are in public preview](https://github.blog/changelog/2025-10-28-enterprise-ai-controls-the-agent-control-plane-are-in-public-preview/) - GitHub Changelog
- [About rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-repository-rules/about-rulesets) - GitHub Docs
- [Foundations of Agentic AI in GitHub](https://learn.microsoft.com/en-us/training/modules/foundations-agentic-ai/) - Microsoft Learn
