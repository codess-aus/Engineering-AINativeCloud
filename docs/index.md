---
title: Engineering the AI-Native Cloud
description: Cloud Native AI in the SDLC — a DevOps Asia Conference companion site on agentic workflows, GitHub Copilot, and owning the code in an AI-native world.
hide:
  - navigation
---

# Engineering the AI-Native Cloud

<div class="home-hero">
  <img src="assets/images/Title.webp"
       alt="Title card: Engineering the AI-Native Cloud, over a night skyline of Ho Chi Minh City, for a DevOps Asia Conference talk."
       width="1536" height="1024" loading="eager">
</div>

**Cloud Native AI in the SDLC.** This is the companion site for a DevOps Asia Conference talk about what
changes — and what doesn't — when AI agents join the software delivery lifecycle. It is built for engineers,
tech leads and platform teams who already run cloud-native pipelines and now need to fold agentic AI,
GitHub Copilot, and multi-agent review into that same discipline: version control, code review, CI/CD,
governance and audit.

The talk's core argument is simple: **AI-native is a redesign of your SDLC, not a plugin bolted onto it.**
Every chapter below expands one beat of the talk into something you can actually apply on Monday morning —
with links back to primary GitHub and Microsoft documentation so you can go deeper than the slide.

!!! note "How this site is organised"
    Each chapter opens with the original hero slide from the talk, followed by the expanded technical
    content. Use the **Next**/**Previous** links at the bottom of each page to move through the talk in
    order, or jump straight to a topic from the grid below. A [Resources](resources.md) page collects every
    external link in one place.

## Chapters

<ul class="chapter-grid">
  <li class="chapter-card">
    <a class="chapter-card__link" href="chapters/01-redesign/" style="display:contents;">
      <img src="assets/images/3-redesign.webp" alt="" loading="lazy">
      <span class="chapter-card__body">
        <span class="chapter-card__num">Chapter 1</span>
        <span class="chapter-card__title">A Redesign, Not a Bolt-On</span>
        <span class="chapter-card__desc">Why "cloud-native" principles need re-deriving for an AI-native SDLC, not just an AI feature bolted on top.</span>
        <span class="chapter-card__link">Read chapter →</span>
      </span>
    </a>
  </li>
  <li class="chapter-card">
    <a class="chapter-card__link" href="chapters/02-rule-zero/" style="display:contents;">
      <img src="assets/images/2-youownthecode.webp" alt="" loading="lazy">
      <span class="chapter-card__body">
        <span class="chapter-card__num">Chapter 2</span>
        <span class="chapter-card__title">Rule Zero: You Own the Code</span>
        <span class="chapter-card__desc">The one non-negotiable rule of agentic engineering — and why it doesn't change no matter how autonomous the tooling gets.</span>
        <span class="chapter-card__link">Read chapter →</span>
      </span>
    </a>
  </li>
  <li class="chapter-card">
    <a class="chapter-card__link" href="chapters/03-accountability/" style="display:contents;">
      <img src="assets/images/4-rulezero.webp" alt="" loading="lazy">
      <span class="chapter-card__body">
        <span class="chapter-card__num">Chapter 3</span>
        <span class="chapter-card__title">Rule Zero in Practice: Accountability</span>
        <span class="chapter-card__desc">What "approve the pull request" actually means when the diff was written by an agent — and how to design that gate.</span>
        <span class="chapter-card__link">Read chapter →</span>
      </span>
    </a>
  </li>
  <li class="chapter-card">
    <a class="chapter-card__link" href="chapters/04-replaceable/" style="display:contents;">
      <img src="assets/images/5-replaceable.webp" alt="" loading="lazy">
      <span class="chapter-card__body">
        <span class="chapter-card__num">Chapter 4</span>
        <span class="chapter-card__title">Who Gets Replaced, Who Becomes Irreplaceable</span>
        <span class="chapter-card__desc">The tasks agents absorb, and the judgement skills that compound in value once they do.</span>
        <span class="chapter-card__link">Read chapter →</span>
      </span>
    </a>
  </li>
  <li class="chapter-card">
    <a class="chapter-card__link" href="chapters/05-fleet-squad/" style="display:contents;">
      <img src="assets/images/6-agentic.webp" alt="" loading="lazy">
      <span class="chapter-card__body">
        <span class="chapter-card__num">Chapter 5</span>
        <span class="chapter-card__title">Agentic Workflows: The Fleet and The Squad</span>
        <span class="chapter-card__desc">Two operating models for orchestrating multiple agents — parallel fleets and reviewed squads — and when to use each.</span>
        <span class="chapter-card__link">Read chapter →</span>
      </span>
    </a>
  </li>
  <li class="chapter-card">
    <a class="chapter-card__link" href="chapters/06-backlog/" style="display:contents;">
      <img src="assets/images/7-backlog.webp" alt="" loading="lazy">
      <span class="chapter-card__body">
        <span class="chapter-card__num">Chapter 6</span>
        <span class="chapter-card__title">The Backlog Has No Bottom</span>
        <span class="chapter-card__desc">Triage patterns for handing low-risk backlog items to agents, and keeping a human accountable for the queue.</span>
        <span class="chapter-card__link">Read chapter →</span>
      </span>
    </a>
  </li>
  <li class="chapter-card">
    <a class="chapter-card__link" href="chapters/07-demo/" style="display:contents;">
      <img src="assets/images/8-demo.webp" alt="" loading="lazy">
      <span class="chapter-card__body">
        <span class="chapter-card__num">Chapter 7</span>
        <span class="chapter-card__title">The Demo: A Squad Clears a Backlog Item</span>
        <span class="chapter-card__desc">Walking through an assign → code → review → merge loop using GitHub Copilot's coding agent and a reviewer agent.</span>
        <span class="chapter-card__link">Read chapter →</span>
      </span>
    </a>
  </li>
  <li class="chapter-card">
    <a class="chapter-card__link" href="chapters/08-business-cliff/" style="display:contents;">
      <img src="assets/images/9-horizon.webp" alt="" loading="lazy">
      <span class="chapter-card__body">
        <span class="chapter-card__num">Chapter 8</span>
        <span class="chapter-card__title">The 2–5 Year Business Cliff</span>
        <span class="chapter-card__desc">Why the constraint shifts from "which two projects do we fund" to "can we govern all ten at once."</span>
        <span class="chapter-card__link">Read chapter →</span>
      </span>
    </a>
  </li>
  <li class="chapter-card">
    <a class="chapter-card__link" href="chapters/09-control-plane/" style="display:contents;">
      <img src="assets/images/10-controlplane.webp" alt="" loading="lazy">
      <span class="chapter-card__body">
        <span class="chapter-card__num">Chapter 9</span>
        <span class="chapter-card__title">GitHub as the Holistic Control Plane</span>
        <span class="chapter-card__desc">Model-agnostic governance: identity, policy, audit and observability for every agent, regardless of which model powers it.</span>
        <span class="chapter-card__link">Read chapter →</span>
      </span>
    </a>
  </li>
  <li class="chapter-card">
    <a class="chapter-card__link" href="chapters/10-recap/" style="display:contents;">
      <img src="assets/images/11-recap.webp" alt="" loading="lazy">
      <span class="chapter-card__body">
        <span class="chapter-card__num">Chapter 10</span>
        <span class="chapter-card__title">Recap: Rule Zero, Scaled</span>
        <span class="chapter-card__desc">Bringing it together — judgement as the multiplier, governance as the guardrail, at fleet scale.</span>
        <span class="chapter-card__link">Read chapter →</span>
      </span>
    </a>
  </li>
  <li class="chapter-card">
    <a class="chapter-card__link" href="resources/" style="display:contents;">
      <img src="assets/images/Close.webp" alt="" loading="lazy">
      <span class="chapter-card__body">
        <span class="chapter-card__num">Resources</span>
        <span class="chapter-card__title">Go Further</span>
        <span class="chapter-card__desc">Awesome Copilot, agentic workflows on GitHub, Git-Ape, and every reference used across this site.</span>
        <span class="chapter-card__link">Open resources →</span>
      </span>
    </a>
  </li>
</ul>

## About this talk

"Engineering the AI-Native Cloud" looks at cloud native AI in the SDLC through a DevOps lens: Azure DevOps
and GitHub as the system of record, agentic workflows and multi-agent review as the new unit of work, and
GitHub Copilot as the control plane that keeps all of it governed, auditable, and accountable to a human.
No case studies or statistics on this site are invented — where a number or example is used, it links to
its primary source on Microsoft Learn, GitHub Docs, or the GitHub Blog.
