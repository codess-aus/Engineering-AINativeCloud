---
title: 2. Rule Zero — You Own the Code
description: The one non-negotiable rule of agentic engineering.
---

# Rule Zero: You Own the Code

<div class="hero-banner">
  <img src="../../assets/images/2-youownthecode.webp"
       alt="Slide titled Rule Zero: Owning the Code in an AI-Native World, over a night photo of the Ho Chi Minh City Central Post Office with skyscrapers behind it."
       width="1448" height="1086" loading="eager">
  <p class="hero-banner__caption">Rule Zero: Owning the Code in an AI-Native World</p>
</div>

<div class="chapter-meta">
  <span class="chapter-meta__tag">Governance</span>
  <span class="chapter-meta__tag">Culture</span>
  <span class="chapter-meta__tag">Code review</span>
</div>

## The rule

**Rule Zero: no matter which agent, model, or workflow produced a change, the human who merges it owns
it.** Not the agent. Not the vendor. Not "the AI." The person whose approval put it on the required-reviewer
line owns the consequences of that diff in production, exactly as if they had typed every character
themselves.

This isn't a new legal theory. It's the same rule that has always applied to copy-pasted Stack Overflow
answers, generated boilerplate, and code written by a junior teammate and merged by a senior one. Agentic AI
doesn't change *who* is accountable — it changes *how much volume* one accountable human now has to
supervise, which is precisely why the supporting process has to get stricter, not looser.

## Why this has to be said out loud

Autonomous-sounding tools invite a specific failure mode: diffusion of responsibility. When output looks
polished and confident, reviewers unconsciously downgrade their scrutiny — the same bias that makes spell-checked
emails feel more trustworthy regardless of content. Multi-agent pipelines make this worse by adding an
extra layer that *looks* like independent verification (an agent reviewed by another agent) but still ends
in one place: a human clicking "Approve".

Rule Zero is the explicit counter to that diffusion. It has to be stated, taught, and enforced structurally
— not left as an assumption — because the entire economic case for agentic engineering depends on trust
holding at scale. One merged hallucination that reaches customers, and the argument "the agent did it" will
not survive a post-incident review, nor should it.

## Designing the merge gate for Rule Zero

- **Required reviews on every branch**, including ones an agent pushed to directly. No exceptions carved out
  for "the agent already checked its own work." See [About rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-repository-rules/about-rulesets).
- **CODEOWNERS on high-blast-radius paths** so the *right* human is accountable, not just *any* available
  reviewer. See [About code owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners).
- **Signed, attributable approvals.** GitHub's pull request approval is already a signature tied to an
  identity — treat it that way in your team norms, not as a rubber stamp.
- **A written definition of "reviewed."** Teams that survive an incident well are the ones that can point to
  a documented review bar (did you read the diff? did you check the tests? did you understand *why*, not
  just *what*) rather than relying on individual judgement calibrated differently across the team.

!!! danger "The failure this rule exists to prevent"
    An agent asked to strengthen a conference companion site once fabricated three case studies and a set
    of statistics that were never verified against a source. Nothing caught it before merge. The lesson
    wasn't "don't use agents" — it was that the humans who approved it were accountable for the fabrication
    reaching an audience, and that no review step had actually asked "where does this number come from?"
    Chapter 3 walks through what changed after that.

## Exercise: write your team's Rule Zero statement

In one paragraph, write down what "owning the code" means for your team when an agent authored it. Include:
who is named on the approval, what they are expected to have actually checked (not just glanced at), and
what happens if a merged agent-authored change causes an incident. If your team can't agree on the answer
in under ten minutes, that's the gap to close before scaling agent usage further.

## Further reading

- [About rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-repository-rules/about-rulesets) — GitHub Docs
- [About code owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) — GitHub Docs
- [Using GitHub Copilot code review](https://docs.github.com/copilot/how-tos/copilot-on-github/use-copilot-agents/copilot-code-review) — GitHub Docs
