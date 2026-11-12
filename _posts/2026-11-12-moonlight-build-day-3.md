---
layout: post
title: "Moonlight Build Day 3 - My Ranking Rule and the Relay Team Bug"
date: 2026-11-12
category: moonlight
description: "Moonlight ran for the first time, I made a ranking rule, I changed it when real data surprised me, and I wrote the rules for explanations."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## Moonlight ran for the first time
Today an agent built the terminal runner. You type one command and a disease, and Moonlight prints the clues.

```
python cli.py "pulmonary arterial hypertension"
```

The first line it prints is the safety line, so nobody can read a clue without seeing it. Sildenafil is not in the list. It is already approved for our disease, so it is not a clue. That is the golden test from my paper graph.

## My ranking rule
Moonlight found 16 new clues for my five proteins. Which one goes first? I wrote my rule in my notebook before any code.

1. Highest protein score first.
2. If tied, more reports first.
3. If still tied, alphabetical order.

A medicine shows once, even if it grabs more than one protein. Then its scores are added.

The protein score is about our disease. The reports only break ties. So a famous medicine cannot jump the queue.

My six test medicines came out in this order: Dibotermin Alfa, Eptotermin Alfa, Sevoflurane, Halothane, Sparsentan, Avanafil. The code got the same order.

<!-- Photo idea: my notebook page with the ranking rule
![My ranking rule](/assets/images/ranking-rule-moonlight-day3.jpg)
-->

## The relay team bug
With all 25 proteins, the first clue was Isosorbide Mononitrate with a score of 1.76. That was odd, because the biggest score on my graph is 0.85.

It grabs three proteins: GUCY1A1, GUCY1B1 and GUCY1A2. But they are three pieces of **one machine**. My rule added them, 0.60 + 0.58 + 0.58. That is like counting one relay win as three wins.

So I changed my rule. Pieces of the same machine count once, using the strongest piece. Different machines still add. Now its score is 0.60.

My rule was not wrong on paper. Real data showed me something my paper did not have.

## When an agent asks to change a test
My rulebook says an agent must never change a test to make it pass. Today agents asked me three times. Each time they showed me the line before and after.

- My ranking rule is now printed under "New clues", so a line count changed from 17 to 18.
- I changed my rule, so the sentence in two tests had to change.
- Three new saved files added 8 hidden medicines, so a count went from 20 to 28.

I said yes, because I had asked for those changes. My answer key (16, 2, 6, 12) did not change. It is like changing the sign on a swim lane after the lane rule changes.

## Rules for explanations
Gemini will write a few sentences for each clue. I wrote one myself first, for Sevoflurane, so Gemini has an example.

My errors in it:
- I wrote that Sevoflurane is linked to PAH. It is not. The protein KCNK3 is linked to PAH.
- I wrote "just like Dolo or paracetamol". That is not in the facts, and a reader might think it is safe to try.
- One sentence was four lines long.

My rules now:
- Explanations are for everyone, written simply enough for a five-year-old who can read.
- **Must:** explain big words, say only true things, say the catch, say not to try it.
- **Must never:** add made-up things, say where to get medicines, say it will work.
- No sentence longer than 20 words.
- Scores are also shown as points out of 100, because a five-year-old does not know decimals.

The ending is added by the code, not by Gemini, so it is always the same:

> But there is a catch. Nobody knows from our information if the disease needs this protein turned up or down. So this is a clue to read about. It is not a treatment. Do not try it.

If Gemini is busy, the code writes a plain explanation itself. It is like a reserve swimmer in a relay.

## New words
- **Activator:** a medicine that switches a protein on harder. I decided it means "up".
- **Binding agent:** a medicine that sticks to a protein. It does not say which way, so it stays "unknown".
- There is a protein called PAH. It has nothing to do with my disease PAH. So Moonlight uses the full name of the disease.

## The commits
- `73c9db1` Ticket 2.6 + 4.1: engine, terminal runner and golden test
- `5b161aa` Merge [pull request #8](https://github.com/kashishdugar2017/moonlight/pull/8)
- `d393641` Ticket 2.5: ranking
- `5bf177a` Merge [pull request #9](https://github.com/kashishdugar2017/moonlight/pull/9)
- `418dd1c` Ticket 2.7: runner uses the ranking
- `2cc8352` Merge [pull request #10](https://github.com/kashishdugar2017/moonlight/pull/10)
- `4795314` Ticket 3.2-3.4: explainer
- `3f09cc0` Merge [pull request #11](https://github.com/kashishdugar2017/moonlight/pull/11)
- `10bcf99` Ticket 2.8: pieces of one machine count once
- `73e6aae` Merge [pull request #12](https://github.com/kashishdugar2017/moonlight/pull/12)

Five merges today. There are 197 tests and they all pass. [Pull request #13](https://github.com/kashishdugar2017/moonlight/pull/13) is waiting for my review.

## Designing the page
Mumma is the designer. We are sketching the web page on paper: the name, the disease, a card for each clue, and the disclaimer at the bottom. It is not finished yet.

<!-- Photo idea: our page sketch
![Our page sketch](/assets/images/page-sketch-moonlight-day3.jpg)
-->

## Next
Finish the design, build the page, and let Agastya try to break it.