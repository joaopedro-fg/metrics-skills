# metrics-skills

Claude Code skills for scoping data, econometrics, and ML work before you touch data or run an analysis.

## Skills

- **`/wool-grill`** ([skills/wool-grill/SKILL.md](skills/wool-grill/SKILL.md)) — interviews you one question at a time to pin down the core of an analysis, model, or decision before anything is built. Surfaces hard-to-reverse choices (outcome/treatment definition, estimator or model family, the sample it's fit on) and checks facts against the environment instead of assuming them. Ends with a confirmed summary and hands off to `/spec`.
- **`/spec`** ([skills/spec/SKILL.md](skills/spec/SKILL.md)) — turns the current conversation into a spec file at `docs/specs/<NNN>-<name>.md`. Fixes the validation strategy up front (out-of-sample test > cross-validation > in-sample diagnostics) and writes out the datasets, sample definition, model, features, and evaluation metric the analysis decisions rest on. No interview — it synthesizes what's already been discussed.

Typical flow: `/grill` to stress-test the idea, then `/spec` to write it down.
