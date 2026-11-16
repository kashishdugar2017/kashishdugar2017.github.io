---
layout: post
title: "Moonlight Build Day 6 - Doctors Found Bugs and I Fixed Them"
date: 2026-11-16
category: moonlight
description: "Two doctors tested Moonlight and found real mistakes. I made about 45 decisions, merged ten pull requests, and Moonlight V1 is done."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## V1 is done
Today I merged ten pull requests. Moonlight has a short name now:

[moonlightclues.com](https://moonlightclues.com)

This morning there were 572 tests. Tonight there are 899, and they all pass.

## What testers told us
From now on every post has this part. Doctors are not named.

**A paediatrician in Sydney** searched a childhood leukaemia. The Approved tab said 0. That worried her, because medicines do exist.
- **Why:** the medicines were filed under the bigger disease, on the sheet above.
- **Fix:** Moonlight now looks one sheet up and one sheet down. The tab says 15.

**A doctor in Kochi** searched amyloidosis and said approved medicines were missing.
- **Fix:** six more now show, each with a label saying where the database files it.
- **Not fixed:** one medicine he named is still missing. The database only says "phase 3 trial" for it. Moonlight never creates an approval, even when a doctor is probably right. Papa is telling the database people.

**Papa asked another AI to test the doctors' cases again.** It found three more things.
- Searching "multiple sclerosis" did not find multiple sclerosis.
- Medicines for a different leukaemia were mixed into one main list.
- The "Source record" link sometimes opened a trial page.

All three are fixed and I checked each one on the real site.

## The lifeguard
Every explanation costs Papa a little Gemini money. So Moonlight has a lifeguard now. One visitor gets 10 searches a minute and 30 explanations a minute.

I chose 10 for explanations first. Then the agent measured it. Opening one tab asks for 5 explanations by itself, so a doctor looking at three diseases would get blocked. I changed it to 30.

The agent could not test the real site. So I did. I searched 11 times on the laptop and got "Too many requests. Please wait a minute." Then I searched on a phone with Wi-Fi off, and it worked. The lifeguard can tell two swimmers apart.

<!-- Photo idea: the laptop saying "Too many requests" next to the phone working
![The lifeguard test](/assets/images/lifeguard-test-moonlight-day6.jpg)
-->

## Sheets above and sheets below
Open Targets files diseases like swim results. There is a big sheet, and smaller sheets inside it.

My rules now:
- The main Approved list is only for this exact disease.
- Medicines from a sheet below go in a folded box called "Approved for a narrower disease".
- Medicines from a sheet above go in a folded box called "Approved for a wider group".
- Each card has a label. It only says what the database does, like "which the database lists under this disease".

I changed the label after an agent found that the database files a dandruff-like disease under a skin disease. A doctor would not agree that it is "a type of" that disease. So the label does not say that.

The boxes are closed. So I had an idea. The top of the tab says "6 more approved medicines are in the folded boxes below", and each box says "Tap to open".

## The AD/HD mystery
Four attention medicines were showing as approved for Alzheimer's disease. An agent found out why. A list in Japan wrote the disease as "ad" and "hd". The database guessed Alzheimer disease and Huntington disease. The agent thinks the list really said "AD/HD". That is a guess, but it fits.

My decisions:
- If the only proof is Japan's general list, the card stays and says so.
- A trial link is not proof of approval. A ticket to the try-outs does not prove you made the team.
- If a doctor confirms a card is wrong, it stays and gets a bright red warning. Red is not one of Mumma's colours. A warning should stand out.

## A sick blood
Gemini wrote that one disease was "a kind of sick blood". Nobody knows what that is. So Gemini does not describe diseases any more. Moonlight shows Open Targets' own description, with its source. Gemini only gets the disease's name.

## The book on the wrong shelf
Multiple sclerosis was hidden by my own rule. On Friday I decided to hide measurements. But the database put multiple sclerosis on the measurements shelf and on a disease shelf, with a strange title.

New rule: a match is hidden only if "measurement" is its only shelf.

## Counting visitors
On Sunday I said no to a visitor counter. Today I changed my mind and wrote that in my logbook.

Moonlight uses Umami. It is like a turnstile at a pool gate. It clicks once for each person. It never knows the disease or what anyone typed. An agent proved it with a mail trap. It opened my page with a disease in the address and caught the letter before it left. The letter only said "/".

I got one question wrong here. I said Umami gets the full address. It does not. A guard tears up the note and writes a new one.

## The guide got shorter
The guide had about 1,440 words. Papa said nobody would read it. Now it has about 510 and every picture is still there. The part for doctors is in a drawer that opens with one tap.

An agent checked my sentences against the code and stopped four times, because a sentence was not true in every case. Short sentences are where "always" sneaks in.

<!-- Photo idea: the new guide on a phone
![The new guide](/assets/images/guide-moonlight-day6.jpg)
-->

## Mumma's design look
We misunderstood Mumma. We thought she wanted every word in the middle of the page. An agent built it and it read like a poem. She wanted the same space on the left and the right. Nothing had been merged, so nothing broke.

Two lines are gone from the page: "Old medicines. New questions." and the handwriting line. The page is half as heavy now.

## My hand checks
I checked five diseases and ten explanations on the real site.

- The order was right every time. For asthma, 73 + 61 = 134 beat 68 + 61 = 129.
- No explanation said a medicine will work.
- One medicine turns a protein up and another turns the same protein down. Both are clues. That is why the catch is on every card.

Things I found for the bug list:
- Some explanations say the same sentence eight times.
- One explanation talked about 1 protein out of 12.
- "Pre-B ALL" does not reach the exact disease.

## My errors
- I said a medicine in trials and approved for the wider group shows in one place. It shows in both.
- I said an empty description should say "coming soon". Nobody is writing one, so it stays blank.
- I pasted a message into the wrong agent. The agent noticed and did nothing.
- I wanted to skip the last check. I did it. It took 30 seconds.

## The commits
- `6a8393b` Merge [pull request #25](https://github.com/kashishdugar2017/moonlight/pull/25): the lifeguard
- `b7cc34a` Merge [pull request #27](https://github.com/kashishdugar2017/moonlight/pull/27): the disease in Open Targets' words
- `6ad3435` Merge [pull request #26](https://github.com/kashishdugar2017/moonlight/pull/26): sheets above and below
- `5e12e9b` Merge [pull request #28](https://github.com/kashishdugar2017/moonlight/pull/28): small words
- `f5188bf` Merge [pull request #29](https://github.com/kashishdugar2017/moonlight/pull/29): honest proof on Approved cards
- `5f1899a` Merge [pull request #30](https://github.com/kashishdugar2017/moonlight/pull/30): Umami
- `56e92e1` Merge [pull request #31](https://github.com/kashishdugar2017/moonlight/pull/31): the guide and the front page
- `022a7e4` Merge [pull request #32](https://github.com/kashishdugar2017/moonlight/pull/32): Mumma's design pass and the short guide
- `f9d1e58` Merge [pull request #33](https://github.com/kashishdugar2017/moonlight/pull/33): the narrower box
- `57155fd` Merge [pull request #34](https://github.com/kashishdugar2017/moonlight/pull/34): the search

Ten merges today. The tests went from 572 to 899, and they all pass.

## Next
Agastya was sick today. When he is better, he tries to break it. After the Buildathon, the short name will stay in the address bar. I said no risks before Friday.
