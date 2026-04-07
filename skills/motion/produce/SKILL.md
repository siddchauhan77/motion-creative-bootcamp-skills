---
name: produce
description: Day-to-day production workflow once your system is set up. Four prompts in sequence: brief an ad → agent review → convert to Nano Banana 2 image prompt → multiply a winning brief across all 15 format templates. Usage: motion:produce [format] [product] [persona] [angle] [emotion]
argument-hint: "[format] [product] [persona] [angle] [emotion] — or just run and Claude will ask"
---

# Motion Creative Bootcamp — Production Workflow

**Author**: Will Sartorious (Motion Creative Strategy Bootcamp)
**Step in system**: Steps 3+4 (daily production once system is set up)
**Requires**: Brand brief + format templates in Project Knowledge

---

## What this skill is

Once your brand research brief, reference cards, format templates, and scoring agents are all in Project Knowledge, this is the workflow you run every single time you make an ad. Four prompts. One output: a Nano Banana 2 prompt ready to paste into fal.ai.

---

## PROMPT 1: BRIEF THE AD

```
I want to create a [FORMAT] ad for [PRODUCT NAME].

Persona: [e.g. Sensitive Skin Sufferer]
Angle: [e.g. Transformation]
Emotion: [e.g. Relief]

Use my brand bible and format template to write the full brief: headline, subhead, copy, creative direction, everything. Follow the format template exactly.
```

**Format options**: Headline | Before & After | Bullet Points | Features & Benefits | Testimonial | Social Proof | Us vs Them | Statistics | Press | News | UGC | Founder Story | Carousel | Handwriting | Negative Marketing

Claude will write the full brief using:
- Your brand research brief (brand voice, product details, proof points)
- The matching format template (copy slots, word counts, structural rules)

---

## PROMPT 2: AGENT REVIEW + ITERATION

Run immediately after Prompt 1, in the same conversation:

```
Please have the agents review the copy.

Please iterate on the copy until every agent gives it a 90+ / 100.
```

Claude runs all 7 agents:
1. Persona Fit (1-100, min 90)
2. Angle Execution (1-100, min 90)
3. Emotion (1-100, min 90)
4. Brand Consistency (1-100, min 90)
5. Copy Excellence (1-100, min 90)
6. Format Compliance (1-100, min 90)
7. Copy Editor (Pass/Fail — veto power)

Claude shows scores, flags failures, rewrites, and re-runs until all pass.

---

## PROMPT 3: CONVERT TO NANO BANANA 2 PROMPT

Run after all agents pass, in the same conversation:

```
Convert this into a ready-to-paste Nano Banana 2 image generation prompt.

The prompt must include:
- Exact dimensions (1080x1920, 9:16 vertical)
- Every piece of approved copy rendered verbatim in the image
- Product position, angle, and scale from the creative direction
- Background treatment from the creative direction
- Typography: exact font names, weights, and color from the brand spec card
- Safe zones (top 270px, bottom 340px clear of critical content)
- Lighting and energy direction
- Logo placement per brand spec sheet
- All 10 universal rules (no panels, no text under 24px, sufficient contrast, photorealistic product, etc.)
- A note that I will upload the brand spec card, visual style card, and product photo as reference images
```

Copy the prompt. Go to fal.ai Nano Banana 2. Upload:
1. Brand spec card PNG
2. Visual style card PNG
3. Product hero photo

Paste prompt. Generate.

---

## PROMPT 4: MULTIPLY A WINNER ACROSS ALL FORMATS

Once you have a brief that's working, multiply it across all 15 format templates in one shot:

```
I have a winning ad brief that I want to multiply across different format templates. The original brief is below.

Here are my format templates: [upload or list your .md template files]

For EACH format template, rewrite the brief to fit that format exactly:
- Keep the same persona, angle, emotion, and core product truth
- Rewrite the copy to match the new format's structure (headline lengths, copy slots, required elements)
- Follow the format template's copy rules and variation vectors
- Adjust the creative direction to match the new format's visual requirements
- Write a complete Nano Banana 2 image generation prompt for each

Do not change the strategic foundation. Only change the packaging.

The original brief:
[paste your winning brief here]
```

This turns 1 winning brief into up to 15 complete ad briefs, each with a ready-to-paste Nano Banana 2 prompt.

---

## Full session flow

```
Session start → Claude Project loads: brand brief, format templates, scoring agents, brand spec cards

→ Prompt 1: Brief the ad (format + persona + angle + emotion)
→ Prompt 2: Agent review + iterate to 90+
→ Prompt 3: Convert to Nano Banana 2 prompt
→ Go to fal.ai: upload spec cards + product photo + paste prompt → generate

Optional:
→ Prompt 4: Multiply winner across all 15 formats
→ /motion:animate: Animate the winner
```

---

## Notes

- Always run in a Claude Project that has your brand brief loaded
- Prompt 3 output should be copy-pasted with zero edits — if you're editing it, the brief wasn't specific enough
- For Prompt 4: you need your format template .md files uploaded to Project Knowledge for Claude to apply them correctly
- The Multiply prompt works best with 3+ format templates in Knowledge — the more it has, the more variations it produces
