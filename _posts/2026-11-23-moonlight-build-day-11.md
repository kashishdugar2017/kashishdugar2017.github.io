---
layout: post
title: "Moonlight Build Day 11 - The Trials Come Back"
date: 2026-11-23
category: moonlight
description: "Three merges in one sprint. Two new folded boxes on the In trials tab, a red warning for tafamidis, and a rule of mine that I changed because it was hiding the trials people most wanted to find."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## A page that went empty
A reader with a rare muscle disease once used Moonlight and found four medicines in trials for it. One was in a big, late trial.

This morning an agent checked that page. It showed no trials at all.

Nothing was broken. Two of my own rules had hidden them:
- One rule only showed trial medicines that act on one of the top 25 proteins.
- The other only showed medicines that are already approved for something else.

Three of the four medicines are brand new. They are not approved for anything yet. So my second rule hid exactly the cards that reader had found useful. It was like a library that only shows the books on its shelves and says nothing about the ones being printed.

## What I changed
The In trials tab now has two folded boxes under the list.

**The first box:** "More medicines in trials for this disease. They do not act on one of the 25 proteins."

**The second box:** "New medicines being tested for this disease. The database records no approval for them for any disease."

Every card in both boxes ends with: "Never start, stop or change any medicine without a doctor."

The muscle disease page went from 0 trials to 4.

## What testers told us
Doctors and testers are not named.

**Readers and doctors** named trials that Moonlight did not show.
- **Why:** my two rules, above.
- **Fix:** the two boxes. Moonlight still only shows trials that the database lists. Trials the database does not have are still missing.

**Doctors** said medicines they use every day were not under Approved. One is for a disease where the hands shake. One is for a thyroid disease.
- **Why:** the official label names the disease, but the database forgot to record the approval. Moonlight cannot see what the database does not hold.
- **Fix, decided but not built:** a second hand-written list, for missing approvals. Each one is checked against the official label first. The card will say: "This approval is missing from the database. We added it from the official label."
- A medicine that doctors use without a label will still not be shown as approved, because it is not.

## A third red warning
Tafamidis showed as approved for a disease called AL amyloidosis. Its official label is for a different kind of amyloidosis. It is the same mistake as deferoxamine yesterday: a real label on the wrong shelf.

It now has the red warning. No doctor has looked at this one. Grok found it and the label was checked.

## A guest list with a wrong name
I wanted Moonlight to ask the database one more thing, to find out if eight medicines are approved somewhere. An agent tried it. Two medicines would have come in. Then the regulators' own pages were checked. One really is approved, in Japan. For the other, no approval was found anywhere, but the database says it is approved.

A door guard who reads a guest list with a wrong name on it lets in the wrong person. So I left the extra question out. All eight stay hidden.

## I checked it with my own eyes
After the first merge I opened the live site. Seven cards, a box with 26 more, and colchicine ending with my sentence. Tests had checked it before. I was the first person.

## My worry, again
I asked again: what if someone does not follow the warning? A warning is the weakest tool I have. The stronger ones are not showing a dangerous card at all, and never saying how to take a medicine. I still do not have a full answer.

## My errors
- I pasted a whole finished ticket into a new window, and a second agent started doing the same work again. I stopped it in under a minute and it had not changed anything. This is the same mistake as Day 9. I did not read the top of the window first.
- I picked a label that said "No regulator has approved them". Moonlight does not read the regulators, only the database. I changed it to say what the database records.
- My rule about "approved for something else" hid trials for days and I did not know, because I never looked at a page where it mattered.
- A test from yesterday said one warning must be the last in the file. That broke as soon as I added another. Tests should say what is true, not what happens to be last.
- I skipped fixing a wrong comment in my own code. It is still wrong.

## The commits
- `0b818be` Merge [pull request #49](https://github.com/kashishdugar2017/moonlight/pull/49): the box for more medicines in trials
- `2067a4e` Merge [pull request #52](https://github.com/kashishdugar2017/moonlight/pull/52): the red warning on tafamidis
- `fa82337` Merge [pull request #53](https://github.com/kashishdugar2017/moonlight/pull/53): the box for new medicines in trials

The tests went from 1,261 to 1,455, and they all pass.

## Next
Tomorrow the code moves to a new home on GitHub. After that: the withdrawal line, the line for cards with no source link, and the list of missing approvals.
