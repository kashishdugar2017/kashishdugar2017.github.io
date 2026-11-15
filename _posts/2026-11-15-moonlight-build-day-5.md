---
layout: post
title: "Moonlight Build Day 5 - Moonlight Is on the Internet"
date: 2026-11-15
category: moonlight
description: "I put Moonlight on the internet, built three tabs, took withdrawn medicines out, and merged seven pull requests before breakfast."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## Moonlight is live
Anyone can open Moonlight now:

[moonlight-1038733794937.asia-south1.run.app](https://moonlight-1038733794937.asia-south1.run.app)

It runs on Google's computers in Mumbai. It is built but not checked yet. Tomorrow is checking day.

## The Google walk
On Friday the Google screens beat me. Today I did it alone.

- The Gemini key lives in a locker called Secret Manager. It is not in my code.
- I told Google where my repo is, and to build from my Dockerfile. The agent calls that file the lunchbox.
- The first build failed. The red message said **"Permission denied on secret"**. Moonlight's helper went to the locker and the locker said "you are not on my list".
- I added the helper to the list and pressed **Retry build**. Three green ticks.

I chose "continuously deploy". Now every time I merge, Google builds Moonlight again by itself. It is like a scoreboard that changes when a new time is recorded.

<!-- Photo idea: the three green ticks
![Build successful](/assets/images/build-success-moonlight-day5.jpg)
-->

## The friend and the map
The search fix uses Gemini like a friend. You ask the friend, "what might this person mean?" Then Moonlight looks on the Open Targets map.

- If the map has it, the button shows the **map's** name.
- If the map does not have it, the name is thrown away.

If Gemini says "dragon pox", no button is shown. Gemini never creates a disease. I answered this wrong first. I thought the button showed Gemini's word.

## Three tabs
The results are now three tabs: **Approved**, **In trials**, **New clues**.

My decisions:
- Approved always opens first, even when it is empty.
- The Approved tab says "Talk to your doctor before changing any medicine."
- Approved cards have no explanation and no "Do not try it" ending.

The last one is important. A grandmother takes a medicine because her doctor said so. If Moonlight says "Do not try it" next to her medicine, she might stop. That could hurt her. So the ending is only for clues.

<!-- Photo idea: the three tabs on the live site
![Three tabs](/assets/images/three-tabs-moonlight-day5.jpg)
-->

## Withdrawn medicines
On Friday I saw odd names on a page. Today an agent checked the real data. It was true. Medicines that were taken off the shelves were showing as new clues.

Think of a swimmer's card. Moonlight only read the line "best race ever", and that line said APPROVAL. Another line said "withdrawn". Moonlight never read that line.

My decision: if **any** country took a medicine off the shelves, Moonlight leaves it out. It is counted, never named.

This changed my paper graph. Sitaxentan was on it as already approved, but it was withdrawn. My answer key was 16, 2, 6, 12. With the real data it is **16, 2, 5, 13**.

The Approved tab has two doors: the proteins, and Open Targets' own list. The first fix only put a guard on one door. Now both doors have a guard.

## Words Moonlight did not know
Asthma and migraine crashed the live site! Open Targets used two stage words Moonlight had never seen.

- **PRECLINICAL:** tested in a lab, never in people.
- **IND:** someone asked permission to test it in people.

They go below phase 1 on my ladder. And if a new word ever comes, Moonlight does not crash. It treats the medicine as not approved and keeps going.

Asking permission is like sending in your entry form. Being in a trial is like being in the pool. The In trials tab is only for swimmers in the pool.

## The guide
Moonlight has a guide now, called "How to use Moonlight". It shows one real card, Doxapram, with gold letters A to H that explain each part.

My page has a rule: before a search, it names no medicine. The guide broke it. So the rule is now more exact. No names outside the guide, and only Doxapram inside it.

The draft had four sentences that were not true any more. The agent caught them and we fixed them.

At the bottom, in handwriting, it says "Made with care by a family in Kochi". That was Papa's idea.

## One no
Papa wanted a visitor counter. I said no. It is not useful right now, and my page loads nothing from outside.

## My errors
- I said the Sildenafil card has "Do not try it" like every other card. It does not.
- I said a left-out medicine disappears without a trace. It is always counted.
- I pressed yes on an agent's question without reading it. Now I know I can type "wait".
- The Google form closed before I finished, because I used the search bar. I filled it in again.

## Practising for the judges
A judge might ask, "Did you write this code yourself?" My answer: No. AI agents wrote it. But I decide how Moonlight behaves, and I do not merge anything until I understand it.

## The commits
- `7edffbf` Merge [pull request #17](https://github.com/kashishdugar2017/moonlight/pull/17): use-by date
- `4f81ab7` Merge [pull request #18](https://github.com/kashishdugar2017/moonlight/pull/18): search that understands people
- `36ee3c6` Ticket 5.3: three tabs, and approved medicines shown
- `94ed454` Merge [pull request #20](https://github.com/kashishdugar2017/moonlight/pull/20)
- `93b75c5` Ticket 2.9: withdrawn medicines are left out
- `067a636` Merge [pull request #21](https://github.com/kashishdugar2017/moonlight/pull/21)
- `9b2abb2` Ticket 2.10: unclear link for IND, PRECLINICAL and unknown link words
- `e655bd8` Merge [pull request #23](https://github.com/kashishdugar2017/moonlight/pull/23)
- `2dde798` Ticket 2.11: the list's withdrawn medicines are left out and counted
- `1a3111e` Merge [pull request #22](https://github.com/kashishdugar2017/moonlight/pull/22)
- `0371929` Ticket 5.4: the How to use Moonlight guide inside the page
- `6149b38` Merge [pull request #24](https://github.com/kashishdugar2017/moonlight/pull/24)

Seven merges today. The tests went from 397 to 572, and they all pass.

## Tomorrow
Today I learned how to swim. Tomorrow I compete. I check five results and ten explanations by hand, Agastya tries to break it, and Mumma looks at the design.
