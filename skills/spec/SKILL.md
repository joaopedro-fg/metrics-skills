---
name: spec
description: Turn the current conversation into a spec file under docs/specs/. No interview — it synthesizes what you already discussed.
---

Write a spec from the current conversation and your understanding of the data and codebase so far. Do not interview the user. Synthesize what you already know.

## Process

1. Explore the repo if you have not already. Follow the conventions and vocabulary already in use — code, notebooks, and data dictionaries alike.

2. Decide the validation strategy before you do anything else. This is the point at which the analysis could fool you, so fix it now, before you see a result. Prefer the strongest validation available: a true out-of-sample test (new data, a held-out period) beats cross-validation, which beats in-sample diagnostics alone. State it once. Do not change it after you see how the numbers come out.

3. Write the spec to `docs/specs/<NNN>-<kebab-case-name>.md`. `NNN` is the next free three-digit number. With no specs yet, start at `000`. Create the directory if it does not exist. Use the template below. When the spec replaces an earlier spec, carry over every decision that still holds. The new spec stands alone. Do not edit or delete the earlier spec.

4. Tell the user the path. List every decision the spec makes that the conversation did not. List every result, model, or metric that today's analysis produces and the new spec drops. Do not run the analysis.

The spec is the brief for the work. A small model may read it, so write down every decision it needs.

## Style

Write every sentence in this style. It comes from Simplified Technical English (ASD-STE100), without the controlled vocabulary.

- One idea per sentence. Keep sentences under 20 words.
- Active voice, present tense.
- One word for one meaning. Do not switch synonyms.
- Define jargon on first use.
- Say what the thing is, not what it is like.
- Prefer the short word to the long one.
- Cut words that carry no meaning.

## Template

<spec-template>

## Problem Statement

The problem the user has, from the user's view.

## Solution

The solution to that problem, from the user's view.

## User Stories

A long numbered list. Each story uses this format:

1. As an <actor>, I want <answer or capability>, so that <benefit>

Cover every part of the work.

## Analysis Decisions

The decisions that shape the analysis:

- The datasets used: source, vintage or snapshot date, and how to access them
- The unit of observation, and the sample or population definition: filters, inclusion and exclusion criteria
- The outcome or target, and the treatment or predictor definitions
- The model or estimator used, and why: for example OLS with fixed effects, gradient-boosted trees, difference-in-differences
- The features, controls, or covariates included, and any transformations
- The validation strategy, fixed before the results are seen
- The evaluation metric or metrics that decide success
- The names of new things other people see: dashboards, tables, model names, output datasets, reports
- Clarifications from stakeholders
- Schema changes to any output dataset or table

Do not point at existing notebooks or quote code. Those go out of date fast. Do say where new artifacts go, as a directory such as `analysis/` or `models/`.

Exception: include a snippet when it records a decision more exactly than prose can — a regression equation, a causal DAG, a schema, a sampling scheme. Keep only the parts that carry the decision.

## Validation Decisions

- What makes a good validation here. Judge the real-world result — out-of-sample performance, or causal validity — not in-sample fit alone.
- Which parts of the pipeline get validated: data quality checks, model evaluation, robustness or placebo checks.
- Similar validations that already exist among past analyses.

## Out of Scope

What this spec does not cover.

## Further Notes

Anything else the reader needs.

</spec-template>