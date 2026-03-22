# Contributing to LLM Failure Mode Taxonomy

This taxonomy grows from real sessions, not theory. Every entry in it was observed in an actual conversation, diagnosed with a testable mechanism, and resolved with an intervention that worked. That standard is what makes it useful — and it's the only standard for contributions.

If you've encountered a failure mode that isn't documented here, and you can name it, explain why it happens, and describe what fixed it — this is the right place for it.

---

## What qualifies

A valid contribution must have all three of the following:

**1. A real observed instance**
The failure must have occurred in an actual session — not a hypothetical, not something you read about, not something you suspect might happen. Include the platform (Claude, DeepSeek, GPT-4, Gemini, etc.), the task context, and what the output did wrong.

**2. A stated mechanism**
Explain *why* the architecture or training produces this behavior. Distinguish between training-origin failures (the model learned this pattern) and inference-origin failures (the generation process causes this). If the mechanism is genuinely unclear, note that honestly — but entries where the mechanism is simply missing will not be merged.

**3. A tested intervention**
Describe what you did that fixed it, and whether the fix is reliable across sessions or context-dependent. "It seemed to help once" is not an intervention. "Restating the role + output constraint at each cycle reliably prevented onset" is.

---

## What does not qualify

- Patterns observed only in synthetic or constructed prompts
- Failures you've read about but not personally encountered
- Theoretical classifications without grounding in a real session
- Prompt engineering tips that aren't tied to a specific failure class
- Model comparisons without a stated failure mode

---

## Submission format

Use this template exactly. Field names and order match the existing taxonomy entries for consistency.

```
### [Failure Mode Name]

**Definition:** What the failure actually is — one to three sentences, precise.

**Mechanism:** Why it happens. Distinguish training vs inference origin where possible.
Note if the mechanism is partially unclear.

**Observed example:** [Platform — task context, date if known]
What the model did wrong, described specifically.

**Prevalence:** How frequently observed, under what conditions, on which platforms.
Note if observed on only one platform.

**Intervention (single-session):** What fixed it within a single conversation.

**Intervention (multi-model setup):** If applicable — what a moderator or external
instance can do that a single-session fix cannot.

**Educational note:** What this failure reveals about how models work.

**Observed by:** Your name or handle (will be credited in the entry)
```

Not every field will apply to every failure mode — for example, not all failures have a multi-model intervention. Leave inapplicable fields out rather than filling them with placeholders.

---

## Which category does it belong to?

Place your submission in the most appropriate existing category:

| Category | Covers |
|---|---|
| 1 — Context & Memory | Failures from losing track of session state, role, history |
| 2 — Output Quality | Failures in depth, form, or specificity of output |
| 3 — Identity & Persona | Failures in how the model represents itself or an assigned role |
| 4 — Safety & Compliance | Failures at the boundary of safety constraints and legitimate use |
| 5 — Reasoning | Failures in the model's internal reasoning process |
| 6 — Calibration | Failures from inference infrastructure, load, or update cycles |
| 7 — Cross-Platform | Failures that only emerge through comparison across models |

If your failure mode doesn't fit any existing category cleanly, propose a new one in your issue and explain why it warrants a separate classification. New categories require at least two distinct failure modes to justify the addition.

---

## How to submit

**Option A — Issue (preferred for discussion)**
Open an issue using the title format: `[New Failure Mode] — [Name]`
Paste the template above filled in. If you're uncertain about the category or mechanism, flag it — that's a valid starting point for a conversation.

**Option B — Pull request**
Add your entry directly to `README.md` under the correct category, following the existing formatting exactly. Open a PR with the title: `Add: [Failure Mode Name]`

Both paths are equally valid. Issues are better if you want feedback on the mechanism before committing to an entry. PRs are better if you're confident in the submission.

---

## Cross-platform observations

Failures confirmed across multiple models are prioritized — they reveal something about the architecture or training paradigm rather than a single vendor's implementation. If you've observed the same failure on two or more platforms, say so explicitly and note any differences in how it manifests or what resolves it.

Single-platform observations are accepted, but must be clearly marked as such. The taxonomy distinguishes between cross-platform confirmed patterns and single-platform observations throughout — your submission should do the same.

---

## Attribution

Every accepted contribution is credited in the entry itself under **Observed by**, alongside the platform and approximate date. If you'd prefer to contribute anonymously, note that in your submission and the field will be omitted.

The taxonomy is a shared empirical record. Your name belongs on what you found.

---

## A note on the standard

This document started from 225 sessions over two+ years. The bar for inclusion is not high in terms of effort — a single well-documented observation is enough. The bar is high in terms of honesty: the mechanism must be stated, the example must be real, and the intervention must have been tested.

If you're uncertain whether something qualifies, open an issue and describe what you saw. Uncertainty about classification is fine. Uncertainty about whether something actually happened is not.

---

*Amir El Belawy — Mansoura University*
