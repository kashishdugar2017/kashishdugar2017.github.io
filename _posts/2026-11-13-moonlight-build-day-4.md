---
layout: post
title: "Moonlight Build Day 4 - Moonlight Opens in a Browser and I Try to Break It"
date: 2026-11-13
category: moonlight
description: "Moonlight ran on my own laptop as a real page, it got faster, and I found four bugs by testing it myself."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## Only 90 minutes
Today I had 90 minutes, because we had to drive to Pala for my swim meet. Three agents had worked in the night, so I started with reviews.

## The waiter and the kitchen
Pull request #14 is the page. The agent explained it like this. My engine is the kitchen. Mumma's page is the table. The API is the waiter who carries my ranked clues to the table. The waiter never changes the recipe. The recipe is my ranking rule.

The medicines I leave out only show as numbers, like marbles in a closed bag. A test checks that no hidden name slips out.

## Faster
Pull request #15 is speed.

- Before: about 14 seconds.
- After: about 3 seconds the first time.
- After that: under 1 second, because the answer is saved in a notebook.

Moonlight asks about 5 proteins at the same time, like 5 swimmers in 5 lanes. They do not finish together. So each result is written by its **lane number**, and the order never changes. I got this wrong first. I said "as it comes".

## The librarian who forgets a shelf
The agent found something odd. It asked Open Targets the same question many times. Sometimes it got 36 reports and sometimes only 1. It is like a librarian who sometimes forgets a shelf.

My rule: ask twice. If the answers differ, ask a third time and keep the fullest.

But my rule has a blind spot. Sometimes both librarians forget the same shelf. They agree, so Moonlight believes them. So I added a use-by date, like milk. A saved answer is thrown away after one day.

## Moonlight on my laptop
I typed three commands and opened `localhost:8000`. Moonlight was a real page for the first time, with Mumma's design and my safety line at the top.

- Dibotermin Alfa was number 1, like my answer key.
- Sildenafil was not there.
- The first search took 8 seconds. The second took 1 second.

<!-- Photo idea: Moonlight open on my laptop
![Moonlight on my laptop](/assets/images/moonlight-laptop-day4.jpg)
-->

## I tried to break it
Agastya is supposed to be the tester, but I started. I found four things.

1. I typed **flu**. The first answer was "Orthomyxoviridae infectious disease". That is the flu, but nobody knows that word. The rest were blood cancers.
2. I typed **high blood pressure**. The list had "Diastolic blood pressure" in it. That is a measurement, not a disease. A 50 m time is not a swimmer.
3. I typed **Diabaties** with a spelling slip. It said no match. But the page still showed the medicines from my last search! Someone could think they were for diabetes.
4. On another disease, one medicine showed twice, and one card listed 23 proteins. Some names looked like medicines that were taken off the shelves. That needs checking.

## My decisions today
- When someone types everyday words, Moonlight asks "Did you mean?" and the person taps. Moonlight never picks for them.
- Measurements are hidden from the list.
- No ticket for the lite Gemini model. The normal one passed my rules 5 out of 5.
- Papa had an idea: show the medicines already approved for the disease, because people want to find the medicine they take. I said yes to **three tabs**: Approved, In trials, New clues. This changes my Day 2 rule.

## My errors
- I said results go in "as they come". They go in by lane number.
- I thought the waiter's recipe was about links. It is my ranking rule.
- We tried to put Moonlight on Google's computers. I signed in ten times and it kept sending me back. I stopped. Stopping halfway did not break anything.

## The commits
- `9d90167` Merge [pull request #14](https://github.com/kashishdugar2017/moonlight/pull/14): the web page and API
- `1a846fb` Merge [pull request #15](https://github.com/kashishdugar2017/moonlight/pull/15): speed
- `3433767` Ticket 8.1: container for Cloud Run
- `cc03723` Merge [pull request #16](https://github.com/kashishdugar2017/moonlight/pull/16)
- `2c00bfb` Replace pitch deck with the 13 Nov version
- `835e890` Merge [pull request #19](https://github.com/kashishdugar2017/moonlight/pull/19)

Four merges today. Two more pull requests are waiting for me: the search fix and the use-by date.

## Next
No Moonlight tomorrow. It is race day. On Sunday I review, build the tabs, and try Google again.
