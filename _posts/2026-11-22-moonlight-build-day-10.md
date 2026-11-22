---
layout: post
title: "Moonlight Build Day 10 - One Red Warning, 33 Clues Left Out"
date: 2026-11-22
category: moonlight
description: "The first of nine days where nothing new gets built. A red warning a doctor asked for, 33 wrong-way clues taken out by hand, and a rule I had to repair the same day I wrote it."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## Nine days of fixing
The Buildathon is over. We were not shortlisted. For the next nine days I am not building new features. Every sprint is for making Moonlight more correct.

There is one exception, and it is also about being correct. We want Moonlight to read two more sources: the US clinical trials register and UniProt, a database about proteins. More about that below.

## What testers told us
Doctors and testers are not named.

**A doctor** saw deferoxamine under Approved for a disease where the body keeps too much iron.
- **Why:** the database put a real official label on the wrong shelf. The label is for a different kind of iron problem, and it says it is not for this one.
- **Fix:** the card stays, but it now has the red warning: "This looks like a mistake in the database. The official label is for a different disease."

**A doctor** searched for anaphylaxis, which is a very dangerous allergic reaction. The top clues were medicines that work against the one medicine that treats it.
- **Why:** Moonlight checks if a medicine touches the right protein. These ones touch it, but they push the wrong way.
- **Fix:** I took 33 clues out by hand, after they were checked against the medicines' official labels. No doctor has confirmed it yet. The page now says "33 medicines left out because they push the wrong way for this disease." One medicine pushes the right way, so it stays.
- **Not fixed yet:** the search also offers a page that is empty.

**Doctors** named trials that Moonlight does not show.
- **Not fixed yet.** Some of it is today's new box. Some of it needs a new source.

## What I decided, not built yet
- **A box for more medicines in trials.** My old rule only showed trial medicines that act on one of the top 25 proteins. Lots of real trials were hidden. They will go in a folded box. An agent started on it today.
- **Withdrawals.** If the database records a withdrawal for a medicine, Moonlight will not show it. The page will say how many are not shown.
- **Two new sources.** I said yes to the US clinical trials register and to UniProt. Doctors keep telling us about trials Moonlight does not show, and about old trials with no end date. The trials register can answer both. Nothing is built yet. Agents study each source first, starting tonight, and I decide what goes on a card after I see what they find.

## How we use Grok
Moonlight has two kinds of AI helpers. Claude agents write the code and run the night studies. Grok is the fact checker.

- Grok reads the regulators' own pages, like the official label for a medicine, and copies the exact sentence with a link.
- Grok opens Moonlight's live pages the way a careful reader would, and reports what it sees.
- It checks in six times a day and picks up the jobs waiting for it.

Today Grok found the label sentence behind the deferoxamine warning, and the label sentences behind the 33 clues.

Grok gathers and reports. It does not decide. What it finds is checked again before I use it, and I decide what Moonlight changes.

## My rule, and repairing it
In the morning I wrote: "Moonlight reads three sources and no more. If a fact has no source link, it does not go on the page."

Then I learned that some cards have no source link in the database at all. My rule would have removed them without a hand check, and that breaks my rule from Day 9. So I repaired it:

**Moonlight reads three sources and no more. If a fact has no source link, the card says so.**

## My worry
A red warning tells people the card might be wrong. But they can still walk into a shop and buy the medicine. A warning on a screen is not a lock on a door. I do not have a fix for this yet. It goes on my list for later.

## My errors
- I said no to a change in an old test before I understood it. A test edited to hide a problem is wrong. This test changed because the fact changed: there are 23 warnings now, not 22. So I said yes.
- The merge button spun for half an hour and I kept waiting at it, like pressing a lift button again and again. Next time I stop sooner and ask.
- I mixed two finished pull requests into one. It worked, but it meant a third pull request and another full check. Two clicks would have been less work.
- I wrote a rule in the morning and had to repair it before lunch. I should have asked what the rule would remove before I wrote it.
- I picked one wording for the withdrawal line, then changed my mind straight away.

## The commits
- `7734f6f` Merge [pull request #48](https://github.com/kashishdugar2017/moonlight/pull/48): the deferoxamine warning and 33 anaphylaxis clues left out by hand

The tests went from 1,245 to 1,261, and they all pass.

## Next
The box for more medicines in trials. Then the withdrawal line.
