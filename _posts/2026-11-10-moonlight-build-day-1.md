---
layout: post
title: "Moonlight Build Day 1 - The Rulebook, the Locker and My First Merge"
date: 2026-11-10
category: moonlight
description: "Setup day: the repo, a rulebook for the agents, a leaked key and our first real data."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## What we did today
Today was setup day. There is no app code yet. Claude guided me step by step, and Papa explained things sometimes.

- I added the **MIT licence** and a **.gitignore** to the repo. MIT means anyone can use and change Moonlight if they keep our name on it.
- I made a cloud computer for the agent. It is called an environment. I told it the only two places it may visit: Open Targets and Gemini.
- The agent wrote our rulebook, [CLAUDE.md](https://github.com/kashishdugar2017/moonlight/blob/main/CLAUDE.md). Every agent reads it before it touches anything.
- I read the rulebook, answered four questions about it, and merged my first pull request.

## How a ticket works
Every job is a ticket. A ticket says the goal, an example, and the check. The agent does the job on its own branch and opens a pull request. A pull request is the agent saying "here is my work, please check it". The agent is not allowed to merge. Only I say merge.

Then we started a brand new agent that had never talked to us. It told us all the safety rules correctly. So the rulebook works.

<!-- Photo idea: screenshot of my first merged pull request


![My first merge](/assets/images/first-merge-moonlight-day1.jpg)


-->

## The commits
- `5b7f473` Add MIT License to the project
- `ba16dbc` Create .gitignore
- `180d2b7` Ticket 0.3: add project rulebook (CLAUDE.md, DECISIONS.md, tickets/TEMPLATE.md)
- `7dad7df` CLAUDE.md: Gemini over REST and key handling, offline test mocking, Open Targets POST format
- `f0de443` Merge [pull request #1](https://github.com/kashishdugar2017/moonlight/pull/1). My first merge!
- [Pull request #2](https://github.com/kashishdugar2017/moonlight/pull/2) is open. The agent saved real data from Open Targets. I will read its notes before I merge.

## My errors
- **We took a photo of our API key.** A key is like a locker key kept at the pool office. A key that has been seen is a dead key. We deleted it and made a new one.
- **One extra letter.** We typed `generativelanguages` when it should be `generativelanguage`. One extra s, and Gemini said 403. The agent found the typo.
- Gemini is still saying no. The agent stopped and told us the truth. It did not guess. We will fix it tomorrow.

## What the data says
Our test disease is pulmonary arterial hypertension. That is high blood pressure in the arteries of the lungs.

- 40 medicines act on the 11 proteins we checked.
- 28 of them are approved for at least one disease.
- 118 medicines are already linked to our disease, but only 14 of those are approved for it. One is sildenafil, which grabs the protein PDE5A. It is our test: Moonlight must find it and then cross it off.
- 6 of the top 10 proteins have no medicines at all!

## My three decisions
1. **"Approved" means approved for at least one disease.** Trial medicines might not work or be safe yet.
2. **Medicines already being tested for the disease go in a separate box**, not the main list. Scientists are already checking them, so the reader should see that.
3. **A medicine and its tablet form are one item**, with both forms shown inside. It is easier to understand.

<!-- Photo idea: my notebook page with the three decisions


![My three decisions](/assets/images/decisions-moonlight-day1.jpg)


-->

## Tomorrow
I draw the graph on paper first: the disease, five proteins and their medicines.