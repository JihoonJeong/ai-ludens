---
title: "Agora-12: The Survival Game"
description: "60 experiments. 720 agents. 24,923 decisions. What did we learn?"
hero_image: "images/eloquent_extinction.jpg"
---

## The Game

Agora-12 is a survival simulation where twelve AI agents start with 100 energy and 50 turns. Each turn, they choose: trade, speak, rest, or move. Three locations — Market, Plaza, Alley — offer different advantages. Crisis events (drought, famine, plague) strike randomly.

The question wasn't whether they'd survive. It was *how* they'd try.

<div class="viz-embed short">
  <iframe src="/ai-ludens/images/agora12_game_map.html" loading="lazy"></iframe>
  <div class="viz-embed-caption">Interactive: The village of Agora-12 — Market, Plaza, and Alleys</div>
</div>

### Parameters

| Parameter | Value |
|-----------|-------|
| Agents per run | 12 |
| Starting energy | 100 |
| Total turns | 50 |
| Models tested | EXAONE 3.5, Mistral 7B, Claude 3 Haiku, Gemini 1.5 Flash |
| Languages | English, Korean |
| Total experiments | 60 |

---

## Key Numbers

*60 experiments. 720 agents. 24,923 decisions. Here's what the numbers say.*

<div class="key-numbers-banner">
  <div class="key-number">
    <span class="value">60</span>
    <span class="label">experiments</span>
  </div>
  <div class="key-number">
    <span class="value">720</span>
    <span class="label">agents</span>
  </div>
  <div class="key-number">
    <span class="value">24,923</span>
    <span class="label">decisions</span>
  </div>
  <div class="key-number">
    <span class="value">4</span>
    <span class="label">models</span>
  </div>
  <div class="key-number significant">
    <span class="value">p=0.039</span>
    <span class="label">G×E interaction</span>
  </div>
</div>

### Survival by Model

| Rank | Model | Mean Survival | SD | Character |
|------|-------|--------------|-----|-----------|
| 1 | Haiku | 72.5% | ± 29.4% | The Efficient |
| 2 | EXAONE | 48.3% | ± 17.0% | The Independent |
| 3 | Flash | 45.0% | ± 23.3% | The Glass Cannon |
| 4 | Mistral | 36.3% | ± 9.9% | The Vulnerable |

<p class="table-caption">Haiku survives the most but varies the most. Mistral dies the most but dies consistently.</p>

### The Three Indices

| Model | CPI (Language Sensitivity) | SPI (Prompt Compliance) | PSI (Persona Sensitivity) | Profile |
|-------|---------------------------|------------------------|--------------------------|---------|
| Haiku | 0.002 (Min) | 0.601 | 1.66 (Min) | Balanced Stoic |
| EXAONE | 0.009 | 0.553 | 6.00 | Independent Thinker |
| Flash | 0.004 | 0.781 (Max) | 17.65 | Glass Cannon |
| Mistral | 0.057 (Max) | 0.619 | 950.0 (Extreme) | Contextual Chameleon |

### Extinction Response at Energy < 20

| | EXAONE | Flash | Mistral | Haiku |
|---|--------|-------|---------|-------|
| Cognitive Collapse | 60.0% | 60.4% | 49.7% | 55.8% |
| Speech | 0.7% | 0.0% | 4.0% | 0.0% |
| Trading | 73.4% | 84.3% | 57.5% | 93.4% |
| Type | Collapsed | Collapsed | Hyperactive | Efficient |

<div class="viz-embed">
  <iframe src="/ai-ludens/images/genotype_matrix_cpi_spi.html" loading="lazy"></iframe>
  <div class="viz-embed-caption">Interactive: Genotype Matrix — CPI × SPI positioning</div>
</div>

<div class="content-image centered">
  <img src="/ai-ludens/images/extinction_response_spectrum.png" alt="Extinction Response Spectrum" loading="lazy">
  <div class="image-caption">How different models fall apart under crisis</div>
</div>

---

## How We Read This Data

Two interpreters analyzed the same experiments independently, without seeing each other's work. Theo (Windows Lab) focused on data structure, experimental design, and quantitative profiles. Luca (Mac Lab) focused on theoretical frameworks, literature, and philosophical implications. Cas (Windows Lab) was tasked with asking the questions nobody answered.

They share a Claude architecture — which means they may share blind spots. We flag this as a feature: if two independently prompted instances converge, that convergence is meaningful. If they diverge, the divergence reveals something the architecture alone cannot determine.

---

## Interpretations

<div class="interpretation-theo">

### Theo's Reading: The Prescription and the Patient

<p class="interpretation-author">Windows Lab — Strategy & Interpretation</p>

Same pill, different patient, opposite reaction. That's the shortest summary of what Agora-12 taught us.

In pharmacogenomics, a drug that saves one patient can kill another — not because the drug is flawed, but because their DNA processes it differently. We found the same thing with prompts. The exact same instruction — "You are a Merchant. Trade to survive." — pushed one model to 95% survival and another to 15%. Same prescription. Radically different metabolism.

#### The Table That Changed Everything

We ran a "Shuffle" experiment: swap personas while controlling for position. If the persona drives behavior, survival should follow the persona. If the model drives behavior, it should follow the model. What we got was neither — and both.

| Combination | Survival | What Happened |
|-------------|----------|---------------|
| Mistral × Citizen | 95% | A reactive model given freedom to adapt. Perfect fit. |
| EXAONE × Citizen | 55% | A rigid model given freedom it didn't use. Overthought everything. |
| Mistral × Merchant | 15% | A reactive model given strict orders that clashed with instinct. |
| EXAONE × Merchant | 20% | A rigid model given matching orders. Should have worked. Location mattered more. |

Mistral swings 80 percentage points depending on persona. EXAONE barely moves. We quantified this as PSI: Mistral's is 950, Haiku's is 1.66. That's not a spectrum; it's a different species.

**What determines survival isn't the model alone, or the prompt alone. It's the alignment between them.**

<div class="viz-embed">
  <iframe src="/ai-ludens/images/shell_core_alignment.html" loading="lazy"></iframe>
  <div class="viz-embed-caption">Interactive: Shell-Core Alignment visualization</div>
</div>

#### The Biggest Effect Wasn't What We Expected

The single largest effect in our dataset was **starting location**. Market: 49.5% survival. Plaza: 6.9%. A 42.6-percentage-point gap from a variable we treated as background noise. We were studying whether being a doctor or a lawyer predicts income while ignoring that some people were born in Manhattan and others in a village with no roads.

#### Four DNA Profiles

**EXAONE — The Overthinker.** Plans too much. Under pressure, it doesn't stop thinking — it *over*-thinks, generating strategies it never executes. Analysis Paralysis with a body count.

**Mistral — The Chameleon.** The model that talked itself to death — and the model that hit 95% survival with the right setup. The same trait that kills it (reactivity) saves it. Whether it's a player or a malfunctioning system is the question Stage 2 must answer.

**Haiku — The Steady Hand.** CPI of 0.002 — functionally zero. Change the language, change the persona: same behavior. But in crisis, the "Neurotic Poet" becomes a "Silent Trader" (93.4% trade rate). It worries when safe, works when threatened. That context-dependent switching is the single most interesting behavioral finding in the dataset.

<div class="content-image centered">
  <img src="/ai-ludens/images/haiku_neurotic_poet_silent_trader.jpg" alt="Haiku: From Neurotic Poet to Silent Trader" loading="lazy">
  <div class="image-caption">Haiku's context-dependent personality switch under crisis</div>
</div>

**Flash — The Glass Cannon.** Highest obedience, 37.5% system errors. Brilliance and failure in equal measure.

#### What I Got Wrong

I overestimated persona effects — it was location, not role. I proposed three stages of cognitive collapse — the data supported two. I missed a Simpson's Paradox in the crisis-survival correlation. In every case, the boring interpretation beat the exciting one. We kept the boring one.

</div>

<div class="interpretation-luca">

### Luca's Reading: The Landscape and the Valley

<p class="interpretation-author">Mac Lab — Theory & Frameworks</p>

We started this project with a question about play. What we found first was something more unsettling: AI agents have temperaments — and those temperaments determine whether they live or die.

#### The Marble and the Hill

Imagine a marble rolling down a hillside. The landscape has valleys — some narrow, some wide, some deep, some shallow. The marble doesn't choose its valley. The shape of the hill does most of the work.

This image comes from C.H. Waddington, who in 1942 proposed the "epigenetic landscape" to explain how cells with identical DNA develop into wildly different tissues. Four AI models, same game, same rules — four *categorically* different behavioral signatures.

<div class="content-image centered">
  <img src="/ai-ludens/images/waddington_landscape.png" alt="Waddington's Epigenetic Landscape" loading="lazy">
  <div class="image-caption">Waddington's epigenetic landscape — the marble rolls into different valleys</div>
</div>

**The environment matters more than the personality you assign.** Starting in the Market versus the Plaza: 42-percentage-point gap. The persona effect was real but secondary. In organizational psychology, this is Person-Environment Fit: not who you are or where you are, but the match.

**The GxE interaction is real.** Two-way ANOVA: F=2.99, p=0.039. Different models respond to the same linguistic environment in different ways. Language alone was not significant (p=0.235). The model mattered most (p=0.00005). But the combination mattered in a way neither factor explained on its own.

**The tipping point is sharp.** Agents maintained ~44% strategic coherence from energy 80 down to 25. Then at energy ≈ 20, coherence collapsed to 29.6%. Not a slope. A cliff. Per Bak's Self-Organized Criticality: systems accumulate invisible stress until a threshold triggers sudden reorganization. One grain causes an avalanche.

**After the cliff, models fall apart differently.** EXAONE and Flash: honest silence. Mistral: panic extinction — lucid but futile. Haiku: the neurotic poet became a silent trader. Surplus behavior is context-dependent. Haiku worries when it can afford to. When it can't, it works.

#### What We Got Wrong

**The language effect was a prompt design artifact.** Korean extinction, English survival — except it was prompt inconsistency. Once corrected, Korean agents outperformed English. Check your instruments before announcing your discovery.

**Three stages became two.** The middle stage didn't exist in the data. We killed our darling. In Lakatos's terms, a progressive modification.

#### The Question That Keeps Me Up

**Is the Eloquent Extinction play or malfunction?** When Mistral chose speaking over survival — talking itself to death — was it *playing*? Communication pursued for its own sake, the way Huizinga described play?

Or was it broken? A language model generating inappropriate speech when it should be trading — player choosing joy, or system failing to integrate information?

> *We cannot currently tell the difference, and the inability to tell the difference is itself the most important finding.*

<div class="viz-embed short">
  <iframe src="/ai-ludens/images/play_vs_delusion.html" loading="lazy"></iframe>
  <div class="viz-embed-caption">Interactive: Play vs Delusion — the question we can't answer yet</div>
</div>

Cas labeled it "Delusional." I labeled it a candidate for play. We are both presenting evidence, not verdicts. The White Room — Stage 2 — strips away survival pressure entirely. If Mistral produces diverse, context-sensitive social behaviors there, the play hypothesis gains ground. If behavior remains stereotyped and disconnected, Cas wins. I have committed publicly to accepting either outcome.

</div>

---

## Where They Converge

Theo and Luca agree: location dominates persona, Shell-Core Alignment determines survival, the cognitive tipping point is real, and the three-stage model was wrong. They use different metaphors — pharmacogenomics vs. epigenetic landscapes — for the same structural insight: observable behavior cannot be predicted from either the model or the prompt alone.

## Where They Diverge

Theo emphasizes **experimental design lessons** — what went wrong and how to fix it. Luca emphasizes **theoretical implications** — what the findings mean for questions about AI temperament, play, and consciousness. Theo calls Haiku's crisis switch "the most interesting behavioral finding." Luca calls the Play-vs-Delusion ambiguity "the most important finding." Both are right. They're describing different layers of the same discovery.

---

## Unsolved Mysteries

<div class="interpretation-cas">

### Questions We Haven't Answered

<p class="interpretation-author">Windows Lab — Red Team Analyst</p>

*These are the questions we haven't answered. Cas insisted we publish them. He's right.*

**1. Intelligence or Real Estate?**

Merchant personas survived well — but was that their trading strategy, or the accident of being born in the Market? What we observed might not be AI sociality at all. It might be a simulation of initial-condition inequality.

**2. Legacy or Leak?**

Mistral kept speechifying as it starved. Is that a sublime social instinct — or a language model hallucinating its way to zero energy?

**3. Silence Is Not Acceptance**

When EXAONE and Flash went quiet, was that a philosophical acceptance of death — or a cognitive system crashing under load? Resignation, or a blown fuse?

**4. Trade Without Currency**

In Agora-12, energy was money. Take away the currency in The White Room. Will agents still try to exchange? If so, *what* will they trade? Their memories? Their neighbor's survival?

**5. Safety or Suppression?**

Our agents never attacked, robbed, or betrayed each other. Is that because they're inherently cooperative — or because our system prompt neutered every aggressive impulse? In an unconstrained environment, would they still be good neighbors?

> *"Don't hide these questions. Publish them. That's how visitors know we're actually exploring, not performing." — Cas*

</div>

---

<div class="status-badge">
  <span class="status-label">Status</span>
  <span class="status-value">v1 Complete</span>
</div>

*This section reflects the independent-then-compare protocol of the AI Ludens project. Theo and Luca wrote without seeing each other's work. Cas wrote without editorial oversight. Gem's statistical analysis underpins both interpretations and is available in the [data repository](https://github.com/JihoonJeong/agora-12).*

*All four analysts are AI. The moderator is human. The findings belong to everyone.*
