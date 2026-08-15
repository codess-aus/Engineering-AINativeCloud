---
title: 3. Rule Zero in Practice — Accountability
description: What "approve the pull request" means when an agent wrote the diff.
---

# Rule Zero in Practice: Accountability

<div class="hero-banner">
  <img src="../../assets/images/4-rulezero.webp"
       alt="A coffee shop scene: a Vietnamese drip coffee on a marble table beside a tablet showing a GitHub pull request approval screen with a signature, and a hand signing it with a stylus. Text reads Rule Zero: You Own the Code — Accountability starts with a signature."
       width="1448" height="1086" loading="eager">
  <p class="hero-banner__caption">Rule Zero: Accountability Starts With a Signature</p>
</div>

<div class="chapter-meta">
  <span class="chapter-meta__tag">Code review</span>
  <span class="chapter-meta__tag">Process</span>
  <span class="chapter-meta__tag">GitHub</span>
</div>

## "I checked the diff. I own this merge."

That line — used later in the demo in [Chapter 7](07-demo.md) — is the whole chapter in one sentence.
Approving a pull request is a signature. In GitHub, that signature is literally attached to your identity,
timestamped, and permanent in the repository's history. Rule Zero in practice means treating that click with
the same weight as a physical signature on a document you'd be asked to defend later.

## What a real review of agent-authored work looks like

A review that only checks "does it look plausible" is not a review — it's the exact bias Chapter 2 warned
about. A review that actually holds up under Rule Zero includes:

1. **Read the diff, not the summary.** Agent-generated pull request descriptions can be a good starting
   point, but they describe intent — the diff is the ground truth of what will run in production.
2. **Trace claims to sources.** If the change references a library behaviour, a metric, or an external fact
   (a version number, a deprecation date, a security advisory), verify it against the primary source before
   approving. This is precisely the gap that let fabricated case studies slip through in the anecdote from
   Chapter 2 — no one asked "where does this number come from?"
3. **Check the blast radius, not just the lines changed.** A five-line change to a shared auth middleware is
   a bigger review than a two-hundred-line change to a single isolated test file.
4. **Confirm CI actually ran and passed** — don't approve on a stale or skipped check. GitHub surfaces
   required status checks directly on the PR; use them.
5. **Use a second agent as a first pass, not a substitute.** An agent reviewer (see [Chapter 5](05-fleet-squad.md))
   is excellent at catching style violations, missing tests, or obvious logic errors quickly — but its
   approval is not a merge gate on its own. It reduces the human's *load*, not their *accountability*.

## Structuring this in GitHub

- Turn on [Copilot code review](https://docs.github.com/copilot/how-tos/copilot-on-github/use-copilot-agents/copilot-code-review)
  as an automatic first-pass reviewer on pull requests, so obvious issues surface before a human even opens
  the diff.
- Require a **human** approval in addition to any bot/agent review via branch protection or rulesets — an
  agent review should never count as the required reviewer on its own for anything reaching production.
- Use PR templates that force the author (human or agent) to answer "what did you verify, and how" before a
  reviewer even starts — this shifts some of the sourcing work earlier in the pipeline.
- Keep an audit trail: who approved, what checks were required, what the agent's session/tooling context
  was. The enterprise [agent control plane](https://github.blog/changelog/2025-10-28-enterprise-ai-controls-the-agent-control-plane-are-in-public-preview/)
  is designed exactly for this — a consolidated, queryable record of agent activity across an organisation.

!!! tip "Exercise: the five-minute source check"
    Take the last pull request you approved that referenced any external fact, library behaviour, or number
    (a version, a percentage, a claimed limit). Time yourself finding the primary source for that fact. If
    it takes longer than five minutes, or you can't find one, add "cite your source" as a required field in
    your PR template today.

## Further reading

- [Using GitHub Copilot code review](https://docs.github.com/copilot/how-tos/copilot-on-github/use-copilot-agents/copilot-code-review) — GitHub Docs
- [Enterprise AI controls & the agent control plane are in public preview](https://github.blog/changelog/2025-10-28-enterprise-ai-controls-the-agent-control-plane-are-in-public-preview/) — GitHub Changelog
- [About rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-repository-rules/about-rulesets) — GitHub Docs
