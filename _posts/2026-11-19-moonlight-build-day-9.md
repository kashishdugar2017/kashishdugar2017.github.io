---
layout: post
title: "Moonlight Build Day 9 - Machine Note, Hand Check"
date: 2026-11-19
category: moonlight
description: "The last sprint before the Buildathon. Five agents, five pull requests, and a new rule: a machine may add a note, but only a hand check may remove a card."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## We got selected
Moonlight is in the Kochi round of the Buildathon tomorrow. So today was the last sprint. After today nothing changes until it is over.

## The night check
Last night an agent checked 50 diseases. Every card says a medicine turns a protein up or down, like a volume knob. The agent checked if the knob words are right.

Moonlight reads the words correctly. But about 1 clue in 8 turns a protein the opposite way to the medicines that are already approved. It is like one swimmer going the wrong way down the lane. The card did not say so.

## What testers told us
Doctors and testers are not named.

**A tester** looked at a disease where the body makes too little of a hormone called cortisol. The top clues were medicines that make cortisol go even lower.
- **Why:** Moonlight checks if a medicine touches the right protein. It did not check which way it pushes.
- **Fix:** I removed those four clues from that page. The page now says "4 medicines left out because they push the wrong way for this disease."

**A builder** saw the words "A short explanation of this clue in plain words." on every clue card. He said nobody checked what the AI built.
- **Why:** it was a label the designer left behind, like a sticky note that says "photo goes here". He was right.
- **Fix:** the sentence is gone. The box shows only its button.

**Testers** found medicines that were taken off the market but still show as approved, and approved medicines that the database says are still in trials.
- **Not fixed yet.** The missing approvals are going in my second report to Open Targets.

## My new rule
I wanted to remove the wrong-way clues on every disease. Then I learned that a machine rule found them, and nobody had checked them one by one. In a few diseases doctors really do use medicines that push both ways.

So I made a rule:

**A machine may add a note. Only a hand check may remove a card.**

- The machine rule adds a quiet grey line: "Opposite way to the approved medicines for this disease." The card stays in its place.
- The four clues I removed were checked by hand against the medicines' official labels. No doctor has confirmed it yet. Papa is asking one.

## A second red warning
Three approved cards had a real official label, but for a different disease. The database filed it on the wrong shelf. My grey line could not catch them, because they do have a regulator record. It is just the wrong one.

They now have a red warning: "This looks like a mistake in the database. The official label is for a different disease." The warning also shows inside the folded boxes on four bigger pages.

## Print this page
There is a new button, "Print this page". It makes a plain black and white register, like a class register. Every approved medicine is on it, and the first 10 new clues. The safety line is at the top and at the bottom of every page.

The warnings are written in words, not only in red. Our printer is coloured, but a doctor's might not be.

## The new heading
The old heading was "Disease → protein → medicine. One search." I did not like it. Papa said my first new one made it sound like every medicine on the page belongs to the disease. The new clues do not. So now it says:

"Research a disease: approved medicines, trials and new clues."

## Five agents
I ran five agents today. Four of them changed the same page file, so I merged them one at a time and each one lined up behind the last.

Two agents never saw each other's work. The print agent finished before the opposite-way line existed, so the paper did not show the line. I found that on the live site and sent a fifth ticket.

## My errors
- I pasted a ticket into the wrong window, twice. The agents noticed and did not do the work twice. Now I read the ticket number at the top of the window before I paste.
- I first chose to let a red-warning medicine decide the "one way". That would have put a line on nine cards because of a medicine a doctor says is a mistake. I changed my answer.
- I wanted to remove the four clues on five pages. Only one page had been checked by hand. That broke my own rule, so only one page changed.
- I said a card with the opposite-way line moves to the bottom. It does not move.
- I said the dot was gone everywhere. It is only gone on a phone.
- I said Moonlight gets facts from Open Targets, PMDA and TTD. Moonlight only reads Open Targets. Open Targets copies from the others.

## The commits
- `e543e27` Merge [pull request #39](https://github.com/kashishdugar2017/moonlight/pull/39): Print this page
- `612e21c` Merge [pull request #40](https://github.com/kashishdugar2017/moonlight/pull/40): the opposite-way line
- `59edb86` Merge [pull request #41](https://github.com/kashishdugar2017/moonlight/pull/41): leftover words, new heading, stray dot
- `ede43f1` Merge [pull request #42](https://github.com/kashishdugar2017/moonlight/pull/42): the second red warning and four clues left out
- `089733e` Merge [pull request #43](https://github.com/kashishdugar2017/moonlight/pull/43): the opposite-way line on paper

The tests went from 1,036 to 1,232, and they all pass.

## Next
The Buildathon. Nothing in Moonlight changes until it is over.
