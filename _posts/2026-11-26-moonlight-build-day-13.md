---
title: "Moonlight Build Day 13 - The Night the Robots Did the Reading"
date: 2026-11-26
---

# Moonlight Build Day 13 - The Night the Robots Did the Reading

Day 12 ended at Change 76. This post starts at Change 77 and ends at Change 109. That is thirty-three changes, all listed in the table at the end, in one 36-hour block. I did not write any of them. I am still on my break. But I decided things, and I will tell you how that works.

**Still on a break.** Papa is running the sprint. When a question needs my answer, he asks me, I decide, and I sign a sheet the next evening so there is a record. On Wednesday night there were seventeen such decisions. Nothing with my words on it goes on the site until it has been on my sheet.

**How an agentic sprint works.** Papa does not write the code either. One AI plans the work and writes a ticket. Another AI builds it. The planner then checks the build on its own: it runs every test, reads every changed line of the old tests, and looks at the page at phone width. Only when it writes "you may merge" does the change go in. A third AI helper then opens the live site and reports what it sees. Papa sits in the middle, like a station master with a very long timetable.

**Wednesday, daytime.** Sixty-two medicines got a red warning after an overnight label check. Every card got a "Report" link, so anyone can tell us a card is wrong. Clue cards now show a line about the gene evidence. The printed page now matches the screen. Pages load faster. Twenty-three source links that opened the wrong label now open the right one. And when a maker or a regulator has withdrawn a medicine, the card can now say so in a grey line that we write by hand, from a source we have read.

**Wednesday night.** This was the big one: fourteen changes between dinner and half past one.

- A trial card now opens a study of its own disease. Before, it could open a study of a different disease, which is like a library book with the wrong cover.
- "Source record" on fifty-four cards now opens the medicine's own label, not a combination product's.
- Ninety-one cards came off pages where the "wider group" was too wide to mean anything.
- Medicines that are only sold in a combination say so.
- Diagnostic agents carry a DIAGNOSTIC tag. A scan dye is not a treatment.
- All the red cards on a page now sit together in one red box. On the type 2 diabetes page that box has sixteen cards, each shown once.
- Six blood-pressure medicines got a red warning on type 2 diabetes. Two medicines lost a red warning on asthma, because a UK label showed we had been wrong.
- Aducanumab shows its withdrawal on the Alzheimer page. Two older diabetes medicines say "Its approval was withdrawn in the US. It may still be sold elsewhere."
- Typing "multiple sclerosis" now lands on a page headed the way you typed it.

**Thursday morning.** The helper checked the live site at seven. Then it read all ninety main-list cards on our ten audited diseases against their own labels. One opened the wrong product (a combination tablet) and one link was broken. Change 109 fixed both before breakfast. Now eighty of the ninety match their own label, none is wrong, and ten are "unsure". The ten are judgement calls, like an insulin label that says "diabetes" but not "type 2". Those come to my sheet tonight.

**What went wrong.** Two things, and we would rather say them ourselves. The planner AI promised to keep reading labels overnight and then did nothing for five hours, because nobody had woken it up. It now sets itself alarms. And it told the checker to expect three things on the live site that were its own mistakes. The site was right; the planner was wrong.

**The big study.** On Day 12 we checked 50 diseases. Overnight we checked a lot more: a sample of 4,631 "Approved" cards across 1,313 disease pages. A computer program read the official label for each pair and asked one question: does this label say the medicine is for this disease?

Where a label was read, it at least partly supports the pairing for about 83 in 100 cards. Only about 25 in 100 match fully. "Partly" usually means a narrower group of patients, a symptom, or a combination. The whole run cost $9.77.

This is not an accuracy score, and it is not a count of mistakes. No doctor has checked the program's work yet. The program said "not found" for 633 cards, and a quick check of 18 of those found at least 3 were false alarms: the medicine was approved, but in Japan or the UK, and the program mostly reads American labels. So the program can be fooled, and the paper says so on page one.

**The paper.** We are writing this up as a short paper for Zenodo, a public library for research, so that anyone can check our method and our files. Its title is "Do the labels agree? A machine-read check of 4,631 'Approved' medicine cards in Moonlight, built on Open Targets 26.09". Version 1.1 will add doctors checking a sample by hand, and labels from Japan, the UK and Europe.

**What Moonlight is becoming.** We set out to build a place to look for clues. It is turning into a place that checks whether the map everyone uses is right, and says honestly where it is not sure. Our hope is simple: that a doctor, a parent or a scientist who opens a disease page can trust what is under "Approved", and that every mistake we find gets fixed for everyone who uses the same data, not only for us.

**Everything that went live since Day 12.**

| Change | What it does |
|---|---|
| 77 | Seven missing approvals added from their labels, including hemin for porphyria and four haemophilia A medicines |
| 78 | Sixty-two red warnings from the overnight label check |
| 79 | The printed page shows what the screen shows |
| 80 | Clue cards show a line about the gene evidence |
| 81 | A "Report" link on every card |
| 82 | The Report form and gene line look tidier (no new words) |
| 83 | Obizur gets a red warning on haemophilia A: its label is for a different, acquired form |
| 84 | Twenty-three source links now open the label that names the disease |
| 85 | Moonlight asks the database fifteen questions at a time, not five |
| 86 | Pages load faster and remember finished answers |
| 87 | Four cards from feedback were read; nothing needed changing |
| 88 | Roctavian on haemophilia A says its label covers only some people |
| 89 | "How to use Moonlight" shows an example card that matches today's cards |
| 90 | Community files for our open-source home |
| 91 | Withdrawals we have read about ourselves show as a grey line |
| 92 | "Source record" opens a regulator's page before a second-hand database |
| 93 | Nitric oxide fixed on lung blood pressure; six odd cards and two links fixed on type 2 diabetes |
| 94 | Changes from my signed sheet of 25 November |
| 95 | A trial card links to a study for this disease |
| 96 | Dicumarol gets my red note on haemophilia A (a blood thinner cannot treat a bleeding disease); sodium phenylbutyrate fixed on ALS |
| 97 | Aducanumab shows its withdrawal on Alzheimer disease |
| 98 | Medicines sold only in a combination say so |
| 99 | Eight changes from the night label check |
| 100 | "Multiple sclerosis" lands on the disease page, headed as typed |
| 101 | A sentence for a medicine withdrawn in one country only |
| 102 | Ninety-one cards removed where the "wider group" was too wide |
| 103 | DIAGNOSTIC tag on scan and test agents, and clearer card words |
| 104 | "Source record" opens the medicine's own label, on fifty-four cards |
| 105 | A trial card never opens a study of a different disease |
| 106 | Seventeen decisions recorded; ipratropium loses a wrong red warning; six blood-pressure medicines get one on type 2 diabetes |
| 107 | Tolazamide and tolbutamide say their approval was withdrawn in the US |
| 108 | All red cards on a page sit together in one red box |
| 109 | Two fixed links on the audited diseases (rosiglitazone and Roctavian) |

**By the numbers.**

| | Day 12 | Day 13 |
|---|---|---|
| Changes merged | 76 | 109 |
| Tests | 2,262 | 3,359 |
| Diseases in the label check | 50 | 1,313 pages (sampled) |
| Cost of the label check | | $9.77 |

After tonight's check of the ten diseases, we stop changing the site for two or three days. Things that have just been fixed should sit still for a while.

If you are a doctor, please open one disease you know well at moonlightclues.com and tell us what is wrong: hello@moonlightclues.com, or the Report link on any card.

*Moonlight is for learning and research. It is not medical advice.*
