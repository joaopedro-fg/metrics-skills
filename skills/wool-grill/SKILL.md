---
name: wool-grill
description: Grill the user about the core of a plan, decision, or idea, then write a spec once they confirm. Use when the user wants to stress-test their thinking, or uses any 'grill' trigger phrases.
---

Interview me until the core idea is clear. Then summarise and wait.

Until I confirm, this is exploration. Do not run the analysis. Do not touch the data. Do not change files.

Ask one question at a time and wait for my answer. Give your recommended answer with it, so I can reply "yes".

Before each question, discover everything you can from the environment. Look at files, every git branch, tools, live systems you can reach, docs, code, data, notebooks, prior analyses, and the web. Never ask me something you can find out yourself. Never state a fact you have not checked.

Ask only about what changes the shape of the work: the goal, hard-to-reverse choices, and contradictions in what I told you. Default anything that is cheap to change once the analysis exists. A model's identification is never cheap: the outcome and treatment or target definition, the estimator or model family, and the sample it is fit on.

When the work replaces an analysis or model that runs today, read what it currently produces first. Name each result, metric, or behaviour the plan drops, and ask me about it. Never drop a result as a default.

When you have enough, give me the core idea in a few lines, the decisions I made, and an **Assumed** list — every choice you defaulted, one line each, with the default you will use. A fact is not a choice. Check a fact, or ask me about it.

Then give a **Checked** list. It holds each fact the plan rests on, one line each, with where you checked it. A fact about another system counts: what a data source actually contains, what a column means, what the current baseline achieves. A fact you could not check is a question for me, not a line in this list.

Then wait for one of two answers:

- **I change some defaults.** Apply my changes, summarise again, and wait again. Repeat as often as I need.
- **I confirm.** Run `/spec`. Do not run the analysis. Do not restart the grilling.

The work itself is a separate step. `/spec` writes the definition to a file.

## House style

Write definitions in this style. It comes from Simplified Technical English (ASD-STE100), without the controlled vocabulary.

- One idea per sentence. Keep sentences under 20 words.
- Active voice, present tense.
- One word for one meaning. Do not switch synonyms.
- Define jargon on first use.
- Say what the thing is, not what it is like.
- Prefer the short word to the long one.
- Cut words that carry no meaning.