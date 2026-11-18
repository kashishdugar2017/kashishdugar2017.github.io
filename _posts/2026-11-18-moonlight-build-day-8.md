---
layout: post
title: "Moonlight Build Day 8 - A Warning That Could Hurt"
date: 2026-11-18
category: moonlight
description: "A tester found that my own safety sentence could make someone stop their medicine. I changed it, ran three agents at once and merged three pull requests."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## Open Targets wrote back
On Day 7 I posted a report to Open Targets. That is the big database Moonlight reads from. I said seven medicines were shown as approved for diseases they are not approved for.

A scientist there answered the same day. He wrote, "You are right about all seven." They had found the same problem themselves and they are fixing it in their next release.

The mistake was not in Moonlight. Open Targets copies some facts from another database called TTD. TTD said "approved" when the medicine had only been tested.

## What testers told us
Doctors and testers are not named.

**A tester in a patient group** found the most important thing this week. Every clue card ended with "It is not a treatment. Do not try it."
- **Why it was a problem:** some people are already taking that medicine, because their own doctor gave it to them. The warning might make somebody stop.
- **Fix:** the last sentence is now "Never start, stop or change any medicine without a doctor." It is the same sentence as the safety line at the top of every page.

**Two readers** saw a card in the "wider group" box and thought the medicine was approved for their own disease.
- **Why:** the label started with the word "Approved". Their eyes stopped there.
- **Fix:** the label now starts with "Not listed as approved for this exact disease."

**A tester** looked at a liver disease. The database had 48 medicines in trials. Moonlight showed 5.
- **Why:** Moonlight only shows a trial medicine if it is approved for another disease and acts on one of the proteins most linked to this one.
- **Not fixed yet.** The In trials tab now says "Not every trial is listed." Fixing the list is the first job after the Buildathon.

**Testers** also found more medicines shown as approved that are not.
- **Fix:** see "One in three" below.

## My prediction was wrong
On Tuesday night an agent checked 124 diseases while I slept. Before it ran, I predicted that fewer than 15 diseases would have an approved card with weak proof.

The real number is 100.

About one approved card in three has no record from a regulator. A regulator is the official office that approves medicines, like the referee who signs the result sheet.

Being wrong was useful. A small fix would not work. The rule had to work for a third of the whole site.

## One in three
I had three choices for those cards: hide them, make them red, or keep them with a quiet grey line.

- Hiding them would leave eight diseases with an empty Approved tab.
- Red would turn a third of the site red. Then red would stop meaning "a doctor told us".
- So I chose the quiet grey line. It says: "The database lists this as approved, but gives no regulator record for it."

Open Targets told us how to tell. Every record says who wrote it. That is called its source.

## Three agents at once
Today I ran three agents at the same time. Each one had its own ticket.

Two of them changed the same test file, like two swimmers who both want lane 4. So one went first and the other lined up behind it.

One agent caught a mistake in my sentence. I wanted to say "one of the 25 proteins". It checked and found a disease with only 3. So my sentence has no number in it now.

## My errors
- I predicted fewer than 15. It was 100.
- My first new safety sentence was "Do not try it unless your doctor has asked you to take it." Papa said the warning must be as clear and short as possible. I picked the safety line instead.
- I chose "Not approved for this exact disease." Then I saw that doctors really do use some of those medicines for that disease. So I changed it to "Not listed as approved".
- I said Moonlight uses dynamic programming to match spelling. It does not. Gemini suggests a name and Open Targets confirms it.
- I got the code reading questions wrong. I will read that function again another day.

## The commits
- `c3e52e7` Merge [pull request #36](https://github.com/kashishdugar2017/moonlight/pull/36): the safer ending
- `a0c5b82` Merge [pull request #37](https://github.com/kashishdugar2017/moonlight/pull/37): the quiet grey line
- `1f0f639` Merge [pull request #38](https://github.com/kashishdugar2017/moonlight/pull/38): clearer box labels and the In trials line

The tests went from 912 to 1,036, and they all pass.

## Next
The snapshot page for doctors. I chose Design 1. And the front page heading, which I do not like.
