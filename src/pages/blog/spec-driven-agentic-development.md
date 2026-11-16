---
layout: '@/templates/BasePost.astro'
title: The Spec Is the Job Now
description: Agentic development does not remove engineering discipline. It moves it earlier. A new paper formalizes what a lot of us have been learning the hard way.
pubDate: 2026-11-15T12:00:00.000Z
---

There is a paper on arXiv I found this week that said out loud what I have been trying to explain to people for the past year.

[SDAD: Spec-Driven Agentic Development for the AI-Native SDLC](https://arxiv.org/abs/2608.20341) is not a long read, but the central claim really validates a lot for me: as frontier coding agents gain larger context windows, the quality of the specification becomes the primary constraint on autonomous delivery. Not the model. Not the tooling. The spec.

They are right. I have watched this play out enough times to stop being surprised by it.

## The Bottleneck Did Not Disappear. It Moved.

The old bottleneck was writing code. You had an idea, you handed it to engineers, and what came back was more or less a function of how good they were and how clearly they were told what to build.

Agentic development does not remove that constraint. It compresses it. An agent can synthesize a full implementation from a large context in minutes. What it cannot do is want the right thing on your behalf. If your spec is fuzzy, the agent picks an interpretation. If it is contradictory, the agent picks one side. If it is missing a constraint, the agent ignores it, and you will not find out until the thing is running.

The discipline is still there. It just moved to the beginning of the loop instead of the middle.

## What SDAD Actually Proposes

The paper formalizes a workflow: capture intent, write machine-readable specs, agent synthesis, independent multi-agent verification, human sign-off. It frames this as the fourth major paradigm in software development after Waterfall, Agile, and XP — which is a big claim, but the comparison holds up. Each shift in the history of this industry was essentially a shift in where the hard thinking lives. SDAD argues that the right place for it now is the spec.

They also introduce governance metrics worth sitting with: Ambiguity Tax, Spec Fidelity, and something called TCI_agentic that includes a repair multiplier. The names are a bit academic but the idea behind Ambiguity Tax is something I have been trying to quantify informally. Vague specs do not just slow you down in the moment — they generate repair work downstream that compounds.

## Writing for Agents Is a Skill

This is the part most teams are not ready for.

We got reasonably good over the last decade at writing tickets. Not great, but functional. A well-structured story with acceptance criteria is a known form. People know roughly what it needs and how to argue about whether it is done.

A machine-readable spec for an agent is different. The ambiguity tolerance is lower. Edge cases that a person would catch by noticing something felt wrong have to be explicit, because the agent will not feel anything.

That is a new skill, and right now almost nobody has it. Teams are importing their existing ticket habits into agent workflows and wondering why the output is inconsistent. The process is not broken. The input is.

## The Sign-Off Still Belongs to a Person

One thing the paper gets right that I want to underline: they are explicit that synthesis authority and release authority should be separated. The agent builds. A person signs off — not as a rubber stamp, but as the person who is actually accountable for what gets shipped.

I wrote about this last week in a [different context](/blog/surrender-the-busywork). The agent can open the pull request. It cannot merge it. That accountability does not transfer just because the implementation was automated.

## What to Actually Do About This

If you are on a team building with agents, three things worth doing now:

- **Treat spec review as engineering work.** It deserves the same rigor as code review. Someone needs to own it and push back when it is not clear enough to hand off.
- **Track your repair rate.** How often does something the agent built need correction because the spec was wrong? That number tells you more about process health than velocity does.
- **Write the edge cases down.** Not the happy path — the cases the agent will get wrong if you do not tell it. If you cannot name them, you are not ready to hand the work off.

The model is good enough. The agents are good enough. What is usually not good enough is what we tell them to build.

Write it down first.
