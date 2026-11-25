---
layout: post
title: "Moonlight Build Day 12, Sprint #2 - We Marked Our Own Homework"
date: 2026-11-24
category: moonlight
description: "Moonlight got a new home, a new sentence on every clue, and its first report card: 81 in 100 Approved cards match their official label. I am taking a short break to learn Rust, and Papa is doing most of the work."
---

*Moonlight Build Log: Papa and I are building [Moonlight](https://github.com/Moonlight-Clues/moonlight) with AI agents. I am the tech lead. I make the decisions and check the work. The agents write the code.*

Today Moonlight got a new home, a new sentence on every clue, and its first report card.

# Moonlight Build Day 12, Sprint #2 - We Marked Our Own Homework

Today Moonlight got a new home, a new sentence on every clue, and its first report card.

**A short break.** Until 30 November, Kashish is taking a break from Moonlight to focus on learning Rust. She has reached Ownership, the part of Rust that decides who is allowed to hold each piece of data, and what comes after it. Papa is doing most of the Moonlight work this week. Kashish still sits down every evening and makes every decision on paper: she reads the questions, circles her answers and signs the sheet. She will be back in full at the start of Moonlight's second version. So that the record stays in one place, the Moonlight Build carries on here on her blog, one post for each day.

**A new home.** The code moved to a place called Moonlight-Clues on GitHub. Moving a website is like moving house: you carry every box, then you check the lights still turn on. They did. The old address just points to the new one now.

**No more AI paragraph.** Each clue used to have a paragraph written by an AI to explain the protein. It sounded clever and said very little. We took it off. Now each clue has one sentence from UniProt, which is a big library that scientists keep about proteins. We do not rewrite it.

**Wrong medicines get their own box.** Some medicines are listed in the database as approved for a disease when they are not. They used to sit in the main list. Now they sit in a red-warning box at the bottom and are not counted.

**Five missing medicines came back.** Doctors and testers told us about medicines that are approved but were shown as "in trials". We read each official label and added them by hand: five in the day, and seven more at night.

**The report card.** We asked a machine to read the official label behind 691 "Approved" cards across 50 diseases. It had one question: does this label say the medicine is approved for this disease? The answer was yes, fully or for some patients, for 81 in 100. For 15 in 100 it was no. No doctor has checked the machine's work yet, and we picked the 50 diseases ourselves. We published the whole thing anyway, with the question we asked and the code, so anybody can check it: [the benchmark](https://github.com/Moonlight-Clues/moonlight/blob/main/docs/benchmarks/2026-11-24-label-benchmark.md).

Our goal is 99 in 100. A machine cannot get us there. Doctors can. If you are one, search a disease you treat at [moonlightclues.com](https://www.moonlightclues.com) and tell us what is wrong: hello@moonlightclues.com.

**Decisions.** Kashish read seven questions on paper this evening, circled her answers and signed. Some of them became code the same night. Eight medicines that an old sticker had been hiding came back, because a real medicines office had approved them. Fourteen more cards got a red warning, each one after someone read its official label. And blood thinners no longer show up as clues for haemophilia, a disease where the blood already does not clot.

**Everything that went live today.** Fourteen changes were merged, each one checked before it went in.

| Change | What it did |
|---|---|
| 63 | A card can now say "The label covers only some people with this disease." |
| 64 | Medicines that look wrongly approved moved into their own red box, and stopped being counted |
| 65 | The AI paragraph on each clue was replaced by one sentence from UniProt |
| 66 | The "Tap to open" lines were tidied |
| 67 | Five missing approvals added from their labels: eculizumab, secukinumab, bimekizumab, elafibranor and seladelpar |
| 68 | Avatrombopag added for immune thrombocytopenia |
| 69 and 70 | The report card published, with the exact question, the code and how the diseases were picked |
| 71 | The two sentences at the top of the front page rewritten |
| 72 | Fourteen red warnings and six more missing approvals, each with its label saved in the code |
| 73 | Huntington's medicines that only treat chorea now carry the "only some people" line |
| 74 | Blood thinners taken off the haemophilia A clues, one medicine off Addison's, and five scan tracers off prostate cancer |
| 75 | A new folded box for medicines the database calls approved without a proper record. Three real approvals were checked and kept in the main list |
| 76 | Eight medicines an old sticker was hiding came back, each with a note that a withdrawal was recorded somewhere |

**By the numbers.** The checks that run on every change went from 1,711 to 2,262. Red warnings went from 24 to 39. Approvals added by hand went from 10 to 22.

*Moonlight is for learning and research. It is not medical advice.*
