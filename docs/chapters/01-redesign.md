---
title: 1. A Redesign, Not a Bolt-On
description: Why cloud-native principles need re-deriving for an AI-native SDLC.
---

# A Redesign, Not a Bolt-On

<div class="hero-banner">
  <img src="../../assets/images/3-redesign.webp"
       alt="Split image: a sepia photo of a historic cathedral labelled 'The Old Blueprint' on the left, transforming into a glowing blue wireframe version beside a modern skyscraper labelled 'The Redesign' on the right, under the heading Cloud-Native to AI-Native: A Redesign, Not a Bolt-On."
       width="1448" height="1086" loading="eager">
  <p class="hero-banner__caption">Cloud-Native → AI-Native: A Redesign, Not a Bolt-On</p>
</div>

<div class="chapter-meta">
  <span class="chapter-meta__tag">Foundations</span>
  <span class="chapter-meta__tag">SDLC design</span>
  <span class="chapter-meta__tag">Architecture</span>
</div>

## The analogy: running Docker on a mainframe

Cloud-native didn't happen because someone put a container runtime on top of a data centre built for
monoliths. It happened because teams rethought deployment, scaling, and failure handling from first
principles — twelve-factor apps, immutable infrastructure, declarative config, and a control loop that
reconciles desired state against actual state.

AI-native is the same kind of shift, one layer up the stack. Bolting a chat assistant onto an unchanged
SDLC is the equivalent of running a single container on a mainframe: technically possible, but it captures
none of the benefit and inherits all of the old constraints — manual gatekeeping at every step, review
processes designed for a world where every line of a diff was typed by a human who could explain their own
reasoning without being asked.

An AI-native SDLC redesigns the *unit of work*, not just the *tool*. The unit of work stops being "a
developer opens an IDE" and becomes "a scoped, reviewable task is assigned to an agent, with a human
accountable for the outcome."

## What actually needs to change

| Cloud-native SDLC | AI-native SDLC |
|---|---|
| CI runs on human-authored commits | CI runs on agent-authored commits, at higher frequency and volume |
| Code review is a single human gate | Code review becomes multi-stage: agent self-check → agent reviewer → human approver |
| Backlog grooming assumes human capacity is the constraint | Backlog grooming assumes *governance and review* capacity is the constraint |
| Branch protection exists to catch human mistakes | Branch protection and required reviews exist to catch agent hallucination *and* human rubber-stamping |
| Observability tracks deploys and incidents | Observability also tracks agent sessions, prompts, tool calls, and policy decisions |

None of this throws away cloud-native discipline — GitOps, trunk-based development, automated testing, and
policy-as-code all still apply. It adds a layer: **treat every agent as a contributor with its own identity,
permissions, and audit trail**, exactly the way you'd onboard a new engineer, except the onboarding is
config instead of a laptop.

## Where GitHub already gives you the primitives

You do not need to invent this from scratch. The redesign leans on primitives that already exist in GitHub
and Azure DevOps:

- **Repository rulesets and branch protection** — enforce required reviews and status checks on every branch,
  regardless of whether the author is human or agent. See [About rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-repository-rules/about-rulesets).
- **CODEOWNERS** — route agent-authored changes in sensitive paths (auth, infra, payments) to the humans who
  must sign off. See [About code owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners).
- **GitHub Copilot coding agent** — an agent that works from an assigned issue, opens a draft pull request,
  and iterates against your existing CI. See [About Copilot coding agent](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-coding-agent).
- **Agent control plane (enterprise)** — a consolidated, auditable view of agent activity across an
  organisation. See the [GitHub Changelog: Enterprise AI controls & the agent control plane](https://github.blog/changelog/2025-10-28-enterprise-ai-controls-the-agent-control-plane-are-in-public-preview/).

## Exercise: audit your SDLC for bolt-on thinking

Pick one recent pull request in your team's main repository and answer honestly:

1. Would your current branch protection rules stop a plausible-looking but factually wrong change from
   merging, if a human reviewer was tired and skimmed it?
2. If an agent had authored that PR instead of a person, is there anything in your process today that
   would treat it differently — more scrutiny, a different reviewer, a narrower set of allowed paths?
3. Do you have a CODEOWNERS entry for every path where a wrong change would be expensive to undo
   (migrations, IAM policy, deployment manifests)?

If the answer to (2) is "no, nothing would change," that's a signal your SDLC is still bolt-on: the tooling
changed, the guardrails didn't.

## Further reading

- [About rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-repository-rules/about-rulesets) — GitHub Docs
- [About code owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) — GitHub Docs
- [Agentic DevOps: evolving software development with GitHub Copilot and Microsoft Azure](https://azure.microsoft.com/en-us/blog/agentic-devops-evolving-software-development-with-github-copilot-and-microsoft-azure/) — Microsoft Azure Blog
- [Foundations of Agentic AI in GitHub](https://learn.microsoft.com/en-us/training/modules/foundations-agentic-ai/) — Microsoft Learn
