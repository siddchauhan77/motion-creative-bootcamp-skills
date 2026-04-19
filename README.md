# Motion Creative Bootcamp Skills

> 13 Claude Code skills for AI ad creative production — brand research, ad briefing, competitor intelligence, animation workflows, and video production. Built on Will Sartorious's Motion Creative Strategy Bootcamp system.

![Claude Code Plugin](https://img.shields.io/badge/Claude_Code-Plugin-7C3AED?style=flat)
![Skills](https://img.shields.io/badge/Skills-13-10B981?style=flat)
![Namespace](https://img.shields.io/badge/Namespace-motion%3A-F59E0B?style=flat)
![Author](https://img.shields.io/badge/Author-Will_Sartorious-EC4899?style=flat)

---

## What It Is

A Claude Code plugin that encodes Will Sartorious's complete DTC ad creative system as runnable skills. The system covers the full production pipeline: research a brand → write a brief → generate an image prompt → animate the result — with AI tools at each step (Gemini, Nano Banana 2, Midjourney, Veo, Kling, Seedance, fal.ai).

Installed and adapted by Sidd Chauhan.

---

## 13 Skills

### Research & Intelligence

| Skill | What it does |
|-------|-------------|
| `motion:brand-research` | One-time brand deep dive — builds Ad Creative Research Brief, Brand Spec Card, and Visual Style Card as HTML ready to screenshot and upload to fal.ai |
| `motion:competitor-intel` | Pulls Meta Ad Library data, classifies ads across 4 dimensions, extracts personas via 4-filter customer review method, outputs creative gap analysis |
| `motion:brand-guard` | Makes AI ads look on-brand — sets up brand guidelines in Claude Projects and applies visual humanization rules to strip the "AI gloss" |

### Briefing & Copy

| Skill | What it does |
|-------|-------------|
| `motion:ad-brief` | Complete ad brief for any of 15 DTC formats — runs 7 scoring agents, iterates until all score 90+, outputs fal.ai image generation prompt |
| `motion:brief-engine` | End-to-end brief system with 6-step headline chain, Claude Cowork automation, and OpenAI Agents persona succession |
| `motion:produce` | Day-to-day production flow: brief → agent review → NB2 image prompt → multiply across all 15 format templates |

### Image Generation

| Skill | What it does |
|-------|-------------|
| `motion:nb2-master` | Full Nano Banana 2 workflow library — 13 ad format templates, 1-to-15 format expansion, SKU color variants, surgical element editing, holiday prompts |
| `motion:ad-swipe` | Clone any competitor ad without copying — deconstructs creative decisions, rebuilds structure for your brand, outputs NB2 prompt |
| `motion:product-shots` | AI product photography — create from scratch (Midjourney + NB2), fix wrong-size insertion, or use Seedance 4.0 for high-fidelity shots |
| `motion:creative-funnel` | GPT-5 insight mining + therapy-speak persona ad generation — builds a persistent creative intelligence model per brand |

### Animation & Video

| Skill | What it does |
|-------|-------------|
| `motion:animate` | Turn a winning static into a 3–4 second animation in 15 minutes — start frame + end frame → Veo 3.1 JSON prompt → Google Flow |
| `motion:animate-statics` | Batch-animate existing static ad inventory — 10 statics → 40+ animations in 30 minutes via Midjourney/Andromeda/NB2 pipeline |
| `motion:video-engine` | Complete AI video ad system — 5 modes: quick dual-flow (Seedance/Veo), full Veo 3.1 with hero + product swap, 1987 vintage style, Flux Kontext + Kling, frame-based animation |

---

## Workflow

**Standard production run:**
```
motion:brand-research [Brand] [URL] [Hero Product]
  → saves Brand Spec Card + Visual Style Card as HTML

motion:ad-brief headline [persona] [angle] [emotion]
  → 7 scoring agents iterate to 90+ → NB2 prompt output

→ paste NB2 prompt into fal.ai Nano Banana 2
  → static ad image

motion:animate
  → upload static → get Veo 3.1 JSON → animate in Google Flow
```

**Competitor swipe:**
```
motion:competitor-intel [brand or category]
  → creative gap analysis + persona extraction

motion:ad-swipe [brand] [product] [persona] [angle] [emotion]
  → upload competitor ad → get NB2 prompt for your brand's version
```

---

## Install

```bash
claude plugin install /path/to/motion-creative-bootcamp-skills
```

Or copy the plugin folder into `~/.claude/plugins/cache/local/` and restart Claude Code.

---

*Skills authored by Will Sartorious (Motion Creative Strategy Bootcamp / SelfStack). Installed by Sidd Chauhan.*
