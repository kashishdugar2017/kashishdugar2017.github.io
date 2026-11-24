---
layout: post
title: "Moonlight Build Day 11, Sprint #2 - The Card Stays"
date: 2026-11-23
category: moonlight
description: "Boy, that was a sprint. Seven merges in one evening. Eight medicines added from their official labels, a folded box for clues that push the opposite way, and a rule from Sunday that I changed because it was hiding medicines doctors use."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## Two sprints in one day
Boy, that was a sprint.

This morning's sprint is in the first Day 11 post. In the evening we started six agents at once, each on one ticket. This post is about the evening, Sprint #2. It ended with seven merges.

Before that, Papa and I went through my decisions on paper. For each one I circled keep or change. We both signed it.

## A rule I changed
On Sunday I decided that if the database records a withdrawal for a medicine, Moonlight hides the card and says how many are hidden.

The agent built exactly that. Then the pages were checked, and I saw what came off the shelf.

On the haemophilia A page, octocog alfa was gone. As far as we know, doctors still use it. No doctor has told us that yet. On the same page, the one medicine a doctor told us was withdrawn was still there, because the database has no withdrawal for it.

A withdrawal in the database often means one brand stopped being sold in one place. It does not mean the medicine is gone everywhere. So my rule was hiding the wrong cards.

I changed it. The card stays, and it gets a quiet grey line:

"The database records a withdrawal for this medicine in some country or region."

I first wrote "in some jurisdiction". That is a big word, and my own rule says Moonlight explains big words. I asked for a simpler one. I picked "country or region" because the European Union is not a country. There are groups of countries that decide together.

This fits a rule I made on Day 8: when the proof is weak, the card says so. We do not hide it.

There is an older switch that still hides a medicine when the database marks the medicine itself as withdrawn. I did not change that one today. It is on my paper for tomorrow.

## Missing approvals, added by hand
Yesterday this was decided but not built. Today it is built.

Some medicines are approved for a disease, and the official label says so, but the database did not record it. Moonlight now has a hand-written list for these. Each label is opened and read first. The card says:

"This approval is missing from the database. We added it from the official label."

Eight medicines are on the list now:
- propranolol, for a disease where the hands shake
- methimazole, for a thyroid disease
- daratumumab, for AL amyloidosis
- atrasentan and sibeprenlimab, for a kidney disease
- ravulizumab, for a disease of the nerves of the eye and spine
- avapritinib, for a disease with too many mast cells
- valbenazine, for the movements in Huntington disease

One medicine did not go on the list. The agent found that the database already had deutetrabenazine under Approved, inside the tetrabenazine card. My sentence says "missing from the database". That would have been untrue, so the agent stopped and asked. That is what I want an agent to do.

There is also a new rule. If I left a medicine out by hand for a disease, the approvals list cannot bring it back for that disease. It is like two lists at a pool gate. If a name is on "stay out of this lane" and also on "come in", the gatekeeper keeps them out and writes it down, so a person can look and fix the list that is wrong. Today there is no clash.

## A drawer for opposite-way clues
Some new clues push a protein the opposite way to the approved medicines. Before, they stayed in the list with a line on them, and sometimes they were at the very top.

Now they sit together in a folded box at the bottom of the New clues tab:

"These push the opposite way to the approved medicines for this disease."

Nobody is removed. Every card is still there and says the same words. On the kidney disease page I used as my example, four clues are in the box, and the tab still says 42.

## One sign, not 26
Yesterday I wrote that every card in the two trial boxes ends with "Never start, stop or change any medicine without a doctor."

One box has 26 cards. Reading the same sentence 26 times turns it into wallpaper. Now the sentence is said once, at the top of each box, like one sign on the wall at the start of the lanes. The words did not change.

## A longer name tag
A card with no source link used to say "No source link in the data". Now it says my sentence:

"The database gives no source link for this medicine."

The card stays where it is. A card that has a link never shows the sentence. On a phone, a card in the In trials tab now puts the trial stage on its own line under the sentence. I looked at the picture and accepted it.

## What testers told us
Doctors and testers are not named.

**Doctors** said medicines they use every day were not under Approved.
- **Why:** the database did not record the approval.
- **Fix:** the hand-written list, above. Five of the medicines they named are on it now. A sixth was already on the page, inside another medicine's card.
- **Not fixed yet:** two more. Their labels only cover some people with the disease, so they need one more line first. An agent is building that tonight.

**Doctors** found clues at the top of a list that push the wrong way for the disease.
- **Why:** Moonlight checks that a medicine touches the right protein. It cannot always tell which way the disease needs it pushed.
- **Fix:** the folded box, above. This is a machine moving cards, not removing them. Only a hand check may remove a card.

## What I decided, not built yet
Two medicines are approved, but their labels are only for some people with the disease. They will go under Approved with one extra line, the same on both:

"The label covers only some people with this disease."

The label link under it says which people. Moonlight does not write its own version of that.

## My errors
- My Sunday rule about withdrawals hid medicines that doctors use. I only saw it when I looked at a real page. This is the second day in a row that one of my rules hid the wrong cards.
- I answered one of my two questions wrong. I said a medicine on both lists would show under Approved. The code keeps it out. I asked which was better, heard the reason, and kept it that way.
- I chose a big word, "jurisdiction", for a line that everyone has to read.
- I merged three pull requests tonight without answering my two questions first. The tests had been run and the changes had been read, but the two questions are my own rule.
- The wrong comment in my own code is still wrong.

## The commits
- `7eb4cd4` Merge [pull request #54](https://github.com/kashishdugar2017/moonlight/pull/54): the hand-written list of missing approvals
- `8f7fac5` Merge [pull request #56](https://github.com/kashishdugar2017/moonlight/pull/56): three more approvals by hand, and left-out wins
- `659653e` Merge [pull request #58](https://github.com/kashishdugar2017/moonlight/pull/58): the folded box for opposite-way clues
- `710bf89` Merge [pull request #57](https://github.com/kashishdugar2017/moonlight/pull/57): the caution sentence once per box
- `efaf2a8` Merge [pull request #55](https://github.com/kashishdugar2017/moonlight/pull/55): the rulebook, with my decisions from 17 to 23 Nov
- `ceb5fa2` Merge [pull request #60](https://github.com/kashishdugar2017/moonlight/pull/60): the withdrawal line on the card
- `0aeda8f` Merge [pull request #61](https://github.com/kashishdugar2017/moonlight/pull/61): the sentence for a card with no source link
- `ecf85ed` Merge [pull request #62](https://github.com/kashishdugar2017/moonlight/pull/62): three more approvals by hand

The tests went from 1,455 to 1,711, and they all pass.

Pull request 59 was closed and not merged. It was the first way of doing withdrawals, the one that hid the cards.

## Next
The code moves to a new home on GitHub. Then the line for labels that cover only some people, and my decision about the older withdrawn switch.
