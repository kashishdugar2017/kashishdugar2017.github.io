---
layout: post
title: "Moonlight Build Day 2 - My Paper Graph Is the Answer Key"
date: 2026-11-11
description: "I drew the real data on paper, sorted 40 medicines by my own rules, and merged three pull requests."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## My paper graph
Today I drew the real data on paper before any code. PAH is the disease in the middle. Around it are five proteins: BMPR2, KCNK3, ACVRL1, EDNRA and PDE5A. Around each protein are its medicines.

- An arrow up means the medicine turns the protein up. An arrow down means it turns it down.
- A medicine and its tablet form go in **one bubble**, like Doxapram and Doxapram Hydrochloride.
- EDNRA has 16 medicines, so I made a tally grid for it.

![My paper graph](https://raw.githubusercontent.com/kashishdugar2017/moonlight/main/docs/paper-graph-answer-key.jpg)

## Sorting the medicines
I ask two questions, in this order:

1. Is it approved for at least one disease? If not, cross it out and stop.
2. What is its link to our disease? No link is a **new clue**. A phase means it is **being studied**. Approval means it is **already approved**, so it is not a clue.

My numbers for the whole page:

- 16 new clues
- 2 being studied
- 6 already approved for our disease
- 12 crossed out
- 36 in total (40 rows on the sheet, but 4 pairs are one bubble each)

Claude counted too, and we got the same. So my drawing is now the answer key. The code has to get my numbers.

## New words
- **Inhibitor, antagonist, blocker:** three ways of turning a protein down. An inhibitor is like a hand on a spinning wheel.
- **Agonist, opener:** two ways of turning it up. An agonist rings the protein's doorbell.
- **Phase 1, 2, 3:** tests in people, from the first to the last. Approval comes after phase 3.

## My errors
- I drew Doxapram in two bubbles first. My own rule says one.
- I missed Nebentan in my grid.
- I gave the Sitaxentan pair two ticks. A pair gets one, the stronger one.
- I put Sparsentan under "approved". "Best stage anywhere" and "Link to our disease" are two different columns, and I mixed them up.
- I crossed out two PDE5A medicines that were approved.

If it is easy for me to mix up, it is easy for an agent. So these are now tests.

## My new merge rule
Nothing gets merged until the agent explains it in five plain sentences and I answer questions about it. One agent said the filter used to be a bin and now it is a sorting tray with labelled slots.

## My decisions today
- Medicines already approved for the disease are removed. They are not clues.
- WITHDRAWAL stays at the bottom of the stage ladder. A medicine taken off the shelves does not count as approved.
- If Moonlight meets an action word it does not know, it says "unknown". It never guesses.

## The commits
- `32372c8` Merge [pull request #2](https://github.com/kashishdugar2017/moonlight/pull/2): the saved data from Open Targets
- `970007d` Ticket 1.3b: rulebook and logbook update
- `af4dc72` Merge [pull request #3](https://github.com/kashishdugar2017/moonlight/pull/3)
- `49369d2` Ticket 1.3: record types. 23 tests pass, and my six examples are in them.
- `9cb2f8b` Merge [pull request #4](https://github.com/kashishdugar2017/moonlight/pull/4)
- `ec0e15d` Add files via upload: my drawing, in the docs folder

Three agents are working tonight: the fetch module (pull request #6), housekeeping (pull request #5) and the filter.

## Tomorrow
I review the fetch and the filter. The filter has to sort the medicines the same way I did on paper.