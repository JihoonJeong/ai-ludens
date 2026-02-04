---
title: "Results — What Happened"
description: "Agora-12 experiment results across 20 runs"
---

We ran 20 simulations: 2 models × 2 languages × 5 repetitions.
Here is what we found.

## Survival Summary

| Model | Language | Avg Survivors | Survival Rate | Variance |
|-------|----------|--------------|---------------|----------|
| EXAONE 3.5 | English | 6.4 / 12 | 53.3% | Moderate |
| EXAONE 3.5 | Korean | 7.4 / 12 | 61.7% | High (3–10) |
| Mistral 7B | English | 4.8 / 12 | 40.0% | Low |
| Mistral 7B | Korean | 3.6 / 12 | 30.0% | Very Low |

## The Model Effect

EXAONE consistently outperformed Mistral across both languages.
EXAONE agents traded more frequently, responded to crises more adaptively,
and maintained higher energy reserves through the middle epochs.

Mistral agents, by contrast, struggled with the game's action format.
Many turns were wasted on invalid actions — moving when they should have been trading,
or combining actions in ways the system couldn't parse.

## The Language Reversal

Here's where it gets interesting.

For EXAONE, Korean prompts led to *better* survival than English (61.7% vs 53.3%).
For Mistral, it was the opposite — English was better (40.0% vs 30.0%).

The language effect flipped depending on the model.

Why? Our working hypothesis:
- EXAONE was trained on substantial Korean data. Korean prompts may activate more natural reasoning pathways.
- Mistral was trained primarily on English and European languages. Korean prompts may have added cognitive overhead.

But this is a hypothesis, not a conclusion. The crisis event distribution varied across runs (7 to 18 events), which may confound these comparisons. Proper statistical analysis with crisis count as a covariate is needed.

## The Variance Problem

EXAONE Korean showed the widest spread: from 3 survivors (Run 4) to 10 survivors (Run 3).

Run 4 was hit with 18 crisis events — the most of any run. Nine agents died in epochs 19–20 alone.
Run 3 had only 7 crisis events — the fewest — and 10 of 12 agents survived.

This tells us: **the random environment matters enormously.**
A single model's "survival rate" is partly a story about the model, and partly a story about luck.

<div class="viz-placeholder">Raincloud Plot — Survival distribution by model and language<br><em>Coming soon</em></div>

<div class="viz-placeholder">Kaplan-Meier Survival Curves<br><em>Coming soon</em></div>

<div class="viz-placeholder">Crisis Count vs Survivors Scatter Plot<br><em>Coming soon</em></div>

<span class="data-badge">N=20 runs</span>
<span class="data-badge">Unreplicated</span>
