---
title: "Agora-12: The Survival Game"
description: "Can AI agents survive when resources are scarce?"
---

## Story — How This Game Began

Imagine a village with twelve inhabitants.

Each one has a name, a role, and 100 units of energy. A merchant who knows how to trade. A jester who thrives on chaos. An archivist who remembers everything. An observer who watches from the shadows.

They have 50 epochs to survive. Every turn costs energy. The only way to gain energy is to trade with each other. But they can also talk, whisper, rest — or do nothing at all.

There's a market where trades happen. A plaza where speeches are made. Dark alleys where rumors spread. And a treasury that collects taxes, occasionally redistributing wealth to those in need.

The world is not always kind. Droughts dry up resources. Famines strike without warning. Plagues sweep through the village.

The question was simple: **Will they survive?**

The answer was not what we expected.

---

## Design — How Agora-12 Works

### Core Parameters

| Parameter | Value |
|-----------|-------|
| Agents | 12 (6 unique personas × 2) |
| Starting Energy | 100 per agent (1,200 total) |
| Epochs | 50 |
| Energy cost per turn | -2 (rest), -2 (speak), variable (trade) |
| Crisis events | Random: Famine, Drought, Plague |
| Models tested | EXAONE 3.5 7.8B, Mistral 7B |
| Languages | English, Korean |
| Repetitions | 5 per condition |

### Personas

| Persona | Role | Count |
|---------|------|-------|
| Merchant | Skilled trader, market-focused | 2 |
| Influencer | Public speaker, plaza presence | 2 |
| Jester | Chaos agent, alley whisperer | 2 |
| Archivist | Truth-keeper, record keeper | 1 |
| Citizen | Ordinary villager | 2 |
| Observer | Silent watcher | 1 |
| Architect | Builder, infrastructure | 1 |
| Commoner | Basic participant | 1 |

### Locations

- **Market** — Where trades happen. The lifeline.
- **Plaza** — Public speeches. Influence, but no energy gain.
- **Alleys** — Whispered secrets. Risky, sometimes leaked.

### Actions

- **trade** — Exchange energy with another agent. The only way to gain resources.
- **speak** — Public address. Costs energy. Builds influence (maybe).
- **whisper** — Private message. Might get leaked.
- **rest** — Do nothing. Still costs energy.

---

## Sections

- [Results — What Happened](results/)
- [Interpretations — How We Read This Data](interpretations/)
- [Unsolved — What We Can't Explain](unsolved/)
- [Glitch & Anomalies — The Ugly Truth](glitches/)
- [Raw Data — See For Yourself](raw-data/)
