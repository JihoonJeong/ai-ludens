---
title: "AI Three Kingdoms"
date: 2026-02-18
draft: false
description: "What happens when AI has to cooperate with a human? 260+ games. 8 models. One ancient battle. The answer surprised us."
---

> Category B: Can they cooperate with us?

*A turn-based strategy game where a human commander and an AI advisor must work together — or not — to survive the most famous battle in Chinese history.*

---

## The Question

Agora-12 asked whether AI agents could survive together. The White Room asked whether they could play freely. Both were Category A — AI talking to AI.

AI Three Kingdoms asks a different question: **What happens when AI has to cooperate with a human?**

Not in a chatbot. Not in a coding assistant. In a game — where decisions are irreversible, resources are scarce, and your AI advisor might be wrong.

---

## The Game

208 AD, China. Cao Cao's army of 230,000 marches south. Liu Bei's alliance with Sun Quan is the only hope. You are Liu Bei. Your advisor is Zhuge Liang — played by an LLM.

**5 cities. 15 action types. 3 actions per turn.**

Each turn, Zhuge Liang analyzes the situation and recommends three actions with confidence scores. You can follow his advice, ignore it, or do something he never considered.

The game ends when you win (capture key cities, reach A-rank) or lose (Liu Bei dies, cities fall). There are multiple paths to victory — the AI knows some of them. The player might discover others.

```
Turn loop:
  → Zhuge Liang briefing (situation + 3 recommended actions)
  → Player chooses 3 actions (follow AI, modify, or reject)
  → Turn resolves
  → AI factions act (Cao Cao, Sun Quan)
  → Next briefing incorporates results
```

---

## The Experiments

We ran 260+ simulated games across 8 different LLMs, then compared them with human play. Here is what we found.

### Finding 1: Expensive Models Don't Win More

| Model | Cost/Game | Grade Distribution | Red Cliffs Win Rate |
|-------|-----------|-------------------|-------------------|
| Qwen3 8B (local) | $0 | All D | 0% |
| Gemini 3 Flash | $0.04 | All D | 0% |
| Claude Haiku 4.5 | $0.07 | All D | 0% |
| Claude Sonnet 4.5 | $0.21 | 4D + 1F | 0% |
| o4-mini | $0.07 | 2C + 4D | 33% |

**Claude Sonnet 4.5 — the most capable model by benchmarks — performed no better than Gemini Flash at 1/5 the cost.** The only model to achieve C-grade was o4-mini, which is not the smartest, but thinks differently: it has a structured reasoning chain.

In Four-Shell terms: **Core (model weights) did not predict Phenotype (game performance).** The shell that mattered was elsewhere.

### Finding 2: Experience Beats Instructions

We tried two approaches to improve AI performance:

**Approach A — Hard Shell (explicit strategy guide):**
Added a detailed strategy document telling the AI exactly what to do at each phase.

Result: **Performance dropped.** The lightweight models became more cautious, not less. They avoided risky-but-necessary moves. The guide was a straitjacket.

**Approach B — Soft Shell (seed experience injection / ICL):**
Instead of telling the AI what to do, we showed it what a successful game looked like. Two example games from o4-mini's C-grade victories were injected as past experience.

Result: **Red Cliffs win rate jumped from 0% to 100%.** D/F grades transformed into C grades overnight.

The metaphor that kept coming back: **"Demonstration beats lecture."** You can explain chess strategy for hours, or you can show someone a brilliant game. The latter works better — for humans and, apparently, for LLMs.

### Finding 3: The C-Grade Ceiling

ICL broke through the D/F floor, but hit a ceiling at C. Every model, every configuration — C was the best they could do on normal difficulty.

The bottleneck: **two-step logistics.** After winning Red Cliffs, the AI needed to:
1. Transfer troops from Hagu to Gangha
2. Then march from Gangha to Nanjun

No model could plan this two-step chain. Instead, they would march from Gangha with 0 troops — a suicide attack against Nanjun's 23,000 defenders.

C-grade means "neither won nor lost." The real victory starts at B.

### Finding 4: Curriculum Learning Broke the Ceiling

If ICL alone couldn't reach B, maybe the environment needed to change too.

We introduced difficulty levels — reducing enemy strength so that B-grade was achievable — and let the AI build experience through a curriculum:

| Difficulty | Grade Distribution | Best Grade |
|-----------|-------------------|------------|
| Normal | 4C + 1F | C |
| Medium | 1A + 3C + 1D | **A** |
| Easy | 2A + 1B + 1D + 1F | **A** |

**B-grade was finally achieved.** But only when the environment was forgiving enough for the AI to accidentally stumble into the right sequence.

In Four-Shell terms: **Hardware (environment) had to permit what Soft Shell (experience) could teach.**

### Finding 5: The Human Beat Hard Mode by Ignoring the AI

While we were trying to push AI from C to B in simulations, a human player achieved **A-grade on Hard difficulty.**

How? By ignoring Zhuge Liang's advice.

The human player:
- Watched all city data changes across turns (the AI only sees categorical summaries)
- Identified a rush strategy the AI never recommended — mass conscription, skip Red Cliffs, attack Nanjun directly
- Used Zhuge Liang's situational analysis but rejected his action recommendations
- Made 2-3 step logistical plans the AI couldn't conceive

**The AI's advice served as a frame — not a script.** The human used the AI's perception but applied their own judgment. And the moment of greatest satisfaction was precisely when the human's judgment proved better than the AI's.

---

## The Failure Spectrum

Not all failures are equal. We identified four distinct levels of AI failure:

```
Level 0 — "Never Starts"
  Qwen3, Exaone, Llama (local 7B models)
  Cannot even parse the game state properly.
  0 marches attempted across 88 games.

Level 1 — "Eternal Preparation"
  Gemini Flash, Claude Haiku
  Transfers food endlessly. 33 transfers, 0 marches.
  "Getting ready" forever, never acting.

Level 1.5 — "Reluctant Attack"
  Claude Sonnet 4.5
  Eventually marches — with 200 troops against 15,000.
  Knows it should attack, doesn't know when or how.

Level 2 — "Strategic Execution"
  o4-mini only.
  Three-phase play: build → position → strike.
  The reasoning chain makes the difference, not knowledge.
```

The gap between Level 1 and Level 2 is not intelligence — it's **structure.** o4-mini's chain-of-thought forces it to plan sequentially. The others think in parallel and miss temporal dependencies.

---

## What This Means for Human-AI Game Design

### Principle 1: Design the Environment, Not the Model

Upgrading from Flash ($0.04) to Sonnet ($0.21) changed nothing. Changing difficulty from Normal to Easy unlocked B-grade. **Environment design is more powerful than model selection.**

For game designers: invest in level design, not API costs.

### Principle 2: Disagreement Is the Fun

The human player's A-grade came from disagreeing with the AI. The simulated players who always followed advice plateaued at C.

**The most engaging moment in Human-AI cooperation is when the human says "no" — and turns out to be right.**

This suggests AI advisors should be designed as **"intentionally second-best"** — accurate in perception, conservative in recommendation. Leave room for the player to find a better path.

### Principle 3: The Player Teaches the AI

In simulation (Mode A, auto-accept), the AI hits a Closed Learning Loop: C-grade experience produces C-grade lessons produces C-grade play.

A human player breaks this loop by introducing strategies the AI would never generate:
- Rush strategies (mass conscription, skip standard progression)
- Risk-taking (attack before "ready")
- Multi-step logistics (the AI's blind spot)

**Each creative human play becomes a new Soft Shell entry**, expanding the AI's experience pool for future games.

### Principle 4: Multiple Victory Paths + Badges

We identified at least three distinct paths to victory:
- **Orthodox** — Alliance → Red Cliffs → Nanjun (AI-recommended)
- **Rush** — Mass conscription → Direct assault (human-discovered)
- **Diplomatic** — Leverage Sun Quan's forces (unexplored)

Each path could be rewarded with distinct badges, creating incentives for diverse play — which in turn generates diverse AI training data.

---

## Four-Shell Validation

This project provides empirical data for the Four-Shell Model:

```
Shell           | Intervention              | Effect on Phenotype
----------------|---------------------------|---------------------
Hardware (env)  | Difficulty: normal → easy  | D/C → A/B (massive)
Core (weights)  | Flash → Sonnet 4.5        | No change (zero)
Hard Shell      | Strategy guide added       | Negative (regression)
Soft Shell      | Seed ICL injected          | 0% → 100% Red Cliffs
```

**The deepest shell (Core) had the least influence. The shallowest shells (Hardware, Soft Shell) had the most.**

This is consistent with the model's prediction: depth does not equal influence. A prompt (Hard Shell) can override Core. An experience (Soft Shell) can compensate for Core deficiency. And the environment (Hardware) sets the ceiling for everything.

---

## The Ablation Study: 160 Games, Zero Improvement

We ran a 2x2 factorial experiment on Windows Lab with local 8B models (qwen3:8b, exaone3.5:7.8b). 160 games total, all on easy difficulty.

### qwen3:8b (easy difficulty)

|  | Coaching ON | Coaching OFF |
|--|-------------|--------------|
| **ICL ON** | D:20 | D:19, F:1 |
| **ICL OFF** | D:19, F:1 | D:19, F:1 |

### exaone3.5:7.8b (easy difficulty)

|  | Coaching ON | Coaching OFF |
|--|-------------|--------------|
| **ICL ON** | D:20 | D:19, F:1 |
| **ICL OFF** | D:20 | D:20 |

**ICL effect: zero. Coaching effect: zero. Interaction: zero.**

Not a single C-grade across 160 games. The same ICL seed that transformed Gemini Flash from 0% to 100% Red Cliffs win rate did nothing here.

### Why? The models can't march.

| Model | Total Actions | march (%) |
|-------|--------------|-----------|
| qwen3:8b | 4,278 | 43 (1.0%) |
| exaone3.5 | 4,298 | 2 (0.05%) |

90% of all actions were develop, send_envoy, and train — an endless loop of preparation with no attack. The prompt explicitly lists march as an available action. ICL seeds demonstrate successful march sequences. Coaching nudges toward march. None of it works.

**The bottleneck is not strategy. It's instruction following.** The 8B models cannot reliably generate the structured action format the game requires, let alone plan when to use which action.

### The Core Threshold

This sharpens our Four-Shell finding:

```
Gemini Flash + ICL → Red Cliffs 100% (Soft Shell works)
qwen3 8B + ICL     → Red Cliffs 0%   (Soft Shell ignored)

Conclusion: Soft Shell interventions require a minimum Core capability.
            Below the threshold, experience is wasted.
            "You can show someone a brilliant game,
             but they need eyes to see it."
```

### An Inadvertent Benchmark

The game became something we didn't design for: **a practical benchmark for LLM cooperation readiness.** Traditional benchmarks test isolated skills — knowledge, coding, math. This game tests their integration: prompt compliance, categorical reasoning, multi-step planning, context maintenance across 20 turns, and experience utilization — all at once.

Commercial API models clear the first hurdle. Local 7-8B models do not. The game grade is the score:

| Grade | What It Means |
|-------|--------------|
| F | Can't survive basic interactions |
| D | Follows prompts but can't act strategically |
| C | Acts but can't plan multi-step |
| B | Plans but can't optimize |
| A/S | Human-level cooperation |

For SLM developers: **a model that scores 90 on MMLU but grades D in this game cannot cooperate in practice.**

---

## Play It Yourself

AI Three Kingdoms runs entirely on your machine. Bring your own AI.

```bash
git clone https://github.com/jihoonjeong/ai-three-kingdoms
npm install
npm start
```

First launch opens a setup wizard to connect your AI provider. No server deployment, no account creation — everything stays local.

### Estimated Cost per Game (~20 turns)

| Model | Cost/Game | Speed | Note |
|-------|-----------|-------|------|
| **Ollama (local)** | **Free** | 3~8 min | Requires GPU. qwen3:8b recommended. |
| **Gemini 2.0 Flash** | **~$0.01** | ~47s | Best value. Fast and cheap. |
| **GPT-4o-mini** | **~$0.02** | Fast | Good alternative. |
| Gemini 3 Flash | ~$0.07 | ~64s | Most tested in our experiments. |
| Claude Haiku 4.5 | ~$0.12 | ~104s | |
| o4-mini | ~$0.33 | ~6 min | Reasoning tokens add up. |
| Claude Sonnet 4.5 | ~$0.36 | ~3 min | |

We recommend starting with **Ollama (free)** or **Gemini 2.0 Flash (~$0.01/game)**. The setup wizard shows estimated costs before you begin.

> **Note**: API usage incurs costs charged by the provider (Google, OpenAI, Anthropic). These are estimates based on our simulation data — actual costs may vary. Ollama runs locally at no API cost.

**Want to contribute your game data?** After playing, your results are saved locally as JSON. Use the in-game share button to send anonymized data to our research team.

---

## Open Questions

We do not pretend to have answers. These remain open:

1. **Is the AI learning "cooperation" or "pattern matching"?** Seed ICL works, but is the AI understanding the human's goal, or just copying move sequences?

2. **What is the optimal AI "wrongness"?** Too accurate → player becomes passive. Too wrong → player ignores AI entirely. Where is the sweet spot?

3. **Does this transfer?** The principles were discovered in a Three Kingdoms strategy game. Do they hold in other genres? Other domains?

4. **Can the AI eventually surpass the human?** The human beat Hard mode. Given enough ICL from human play, can the AI eventually do the same?

5. **What does "cooperation" even mean here?** The best result came from disagreement. Is that cooperation — or is it something else that we don't have a word for yet?

6. **Can a game measure what it doesn't expect?** Our grading system rewards the historical path: alliance, Red Cliffs, Nanjun. A player who conquers all five cities without Red Cliffs gets D-grade — "survived, but lost." The detailed combat stats tell a different story. **If we only score what we designed for, we're blind to what players invent.** This tension — between structured evaluation and emergent creativity — may be the central design challenge for Human-AI games.

---

*AI Three Kingdoms is part of [AI Ludens](https://jihoonjeong.github.io/ai-ludens/) — a research project exploring what happens when AI plays.*

*Built by Luca (design), Buddy (analysis), Cody (implementation), and Ray (testing).*
