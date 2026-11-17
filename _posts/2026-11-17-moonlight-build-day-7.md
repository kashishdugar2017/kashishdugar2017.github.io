---
layout: post
title: "Moonlight Build Day 7 - Twelve Red Warnings"
date: 2026-11-17
category: moonlight
description: "My first 90-minute sprint. A doctor said twelve cards were wrong, so they got red warnings. I merged one pull request and practised answers for the judges."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/kashishdugar2017/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

## Sprints
V1 is done. So now I work on Moonlight in sprints. A sprint is 90 minutes with a plan written before I start. It ends with this blog post.

Today's sprint finished early.

## What testers told us
Doctors are not named.

**A paediatrician in Sydney** said four attention medicines are not approved for Alzheimer's disease, Huntington's disease or eczema.
- **Why:** this is the AD/HD mix-up from Day 6. Now a doctor has said it too.
- **Fix:** those twelve cards have a bright red warning. 4 medicines x 3 diseases = 12.

**A surgeon in Lucknow** said Moonlight works very well, but the order of the medicines did not match how good they are.
- **Why:** the Approved tab is A to Z, like a class register. He read it like a podium.
- **Fix:** the top line now ends with "Listed A to Z."

**A doctor in Kochi** said a medicine for one cause of a heart problem shows under the heart problem in general.
- **Not fixed:** the database files one approval on three shelves. There is no quick fix. It is on the bug list.

**Someone in a family group for a muscle disease** said two medicines were missing.
- **Not fixed yet:** one is a new brand name of a medicine Moonlight already shows. Moonlight shows each medicine once and hides brand names. The other one still needs checking.

**Someone wrote "This is not something you can vibecode."** That means building with AI and not checking. I asked if we vibe coded. The answer is no. The agents wrote the code. I wrote the rules and checked the work.

## My two decisions
1. One doctor's word is enough for the red warning. A warning on a good card makes people careful for no reason. A missing warning on a wrong card is worse.
2. I kept my caution sentence exactly and added three words. Papa's line was shorter. I picked mine.

## Sticky notes
The corrections file is a list of sticky notes. Each note has a medicine and a disease on it. A note only works for the disease written on it.

I checked on the real site. On the Huntington's page the four medicines have the red warning and they are still in A to Z order. Tetrabenazine has no warning, because no note names it.

<!-- Photo idea: the red warning on the Huntington's page
![The red warning](/assets/images/red-warning-moonlight-day7.jpg)
-->

## Practising for the judges
While the agent worked, I practised four answers.

- What is Moonlight? A person types a disease. Moonlight links disease → protein → medicine. We get three lists: Approved, In trials and New clues. But none of them are medical advice.
- Did you write the code? No. The agent wrote the code. I decided what Moonlight must do, and I checked that the code does it.
- How did you check? On the live website, and by hand.
- What happens when Moonlight is wrong? A doctor found a tab that said 0. I made Moonlight look at the parent and daughter diseases. Now it says 15.

## My errors
- I said a sticky note warns the medicine everywhere. It does not. Methylphenidate is really approved for ADHD, so a warning there would be a lie.
- I said I decided how the code is written. I did not. I decided what it must do.

## The commit
- `825bbd3` Merge [pull request #35](https://github.com/kashishdugar2017/moonlight/pull/35): twelve red warnings and "Listed A to Z"

The tests went from 899 to 912, and they all pass.

## Next
I do not like the heading on the front page. I want no heading at all. Mumma and Papa will see a before and after, and then I decide.
