---
name: ad-swipe
description: Clone any competitor ad without copying it. Upload a competitor ad image, then this 3-stage workflow deconstructs every creative decision, rebuilds the structure for your brand with original copy, and outputs a complete Nano Banana 2 image prompt ready to paste into fal.ai. Usage: motion:ad-swipe [brand name] [product] [persona] [angle] [emotion]
argument-hint: "[brand name] [product] [persona] [angle] [emotion]"
---

# Motion Creative Bootcamp — Ad Swipe (Competitor Reverse-Engineering)

**Author**: Will Sartorious (Motion Creative Strategy Bootcamp)
**Step in system**: Step 4 (Clone Any Ad workflow)
**Requires**: Competitor ad image uploaded to conversation + brand spec sheet in Project Knowledge

---

## What this does

Takes a competitor's ad image, deconstructs every creative decision, and rebuilds it as a ready-to-generate prompt for YOUR brand with the correct copy for your persona, angle, and emotion. The output is a complete Nano Banana 2 prompt you can paste directly into fal.ai.

**Rule**: We borrow the STRUCTURE and COMPOSITION techniques — never the copy, tagline, or brand-specific language.

---

## Inputs

```
Competitor ad image: [UPLOAD TO CONVERSATION]
Your brand name: [FROM ARGUMENT OR ASK]
Your product: [description, price, key claims]
Your persona: [who this ad is for]
Your angle: [strategic angle]
Your emotion: [target emotion to trigger]
Brand spec sheet: [in Project Knowledge]
Product image: [user uploads to fal.ai separately]
```

---

## STAGE 1: DECONSTRUCT THE COMPETITOR AD

When a competitor ad image is uploaded, analyze and extract all of the following. Be thorough — someone who has never seen this ad should be able to reconstruct it exactly from your description.

### Layout analysis
```json
{
  "aspect_ratio": "",
  "format_type": "headline | before-after | testimonial | social-proof | us-vs-them | statistics | features-benefits | bullet-points | press | news | ugc | founder-story | carousel | handwriting | negative-marketing | other",
  "style_match": "Which style (A/B/C) from the matched format spec best describes this ad",
  "composition": {
    "text_position": "top-third | center | bottom-third | left-aligned | right-aligned | overlaid",
    "product_position": "center | left | right | top | bottom | absent | background",
    "product_frame_percentage": "estimated % of frame the product occupies",
    "negative_space": "minimal | moderate | generous",
    "visual_hierarchy": "What the eye reads first, second, third"
  }
}
```

### Typography extraction
```json
{
  "headline_treatment": {
    "case": "uppercase | lowercase | title case | sentence case",
    "estimated_font_category": "sans-serif geometric | sans-serif humanist | serif modern | serif traditional | slab serif | display | handwritten | monospace",
    "weight": "light | regular | medium | bold | black",
    "alignment": "left | center | right",
    "letter_spacing": "tight | normal | wide | very wide",
    "line_count": "",
    "color": "describe the color"
  },
  "subhead_treatment": "same structure as above, or 'none'",
  "body_treatment": "same structure as above, or 'none'",
  "cta_treatment": {
    "shape": "rounded | pill | sharp corners | no button (text only)",
    "fill": "solid color | outline | ghost",
    "text_case": "uppercase | sentence case",
    "color": "describe fill and text colors"
  }
}
```

### Color and mood extraction
```json
{
  "background": {
    "type": "solid color | gradient | photograph | texture | pattern",
    "dominant_color": "",
    "secondary_color": ""
  },
  "color_palette": ["list all visible colors"],
  "lighting": "flat | soft natural | dramatic side | overhead | backlit | warm golden | cool blue",
  "mood": "1-3 adjectives describing the emotional feel",
  "energy_level": "quiet and restrained | confident and direct | bold and loud | playful and energetic | premium and elevated | urgent and high-pressure"
}
```

### Copy extraction
```json
{
  "text_elements": [
    {
      "role": "headline | subhead | body | label | cta | proof | offer | badge",
      "text": "exact text as rendered",
      "word_count": "",
      "position_in_frame": ""
    }
  ],
  "total_text_elements": "",
  "copy_strategy": "What is the ad actually arguing? What is the single message?",
  "emotional_register": "What emotion is it trying to trigger?",
  "proof_mechanism": "How does it prove its claim? (social proof, statistic, authority, demonstration, testimonial, none)"
}
```

### What makes this ad work (or not)
```json
{
  "strongest_element": "The single best creative decision in this ad",
  "weakest_element": "The single worst creative decision",
  "visual_copy_coherence": "Does the image reinforce the copy's concept? Yes/No and why",
  "scroll_stop_factor": "What would make someone stop scrolling? Rate 1-10",
  "steal_worthy": ["List 1-3 specific techniques worth borrowing"]
}
```

---

## STAGE 2: COPY GENERATION FOR THE REBUILD

Before building the image prompt, generate the copy for your brand.

### Inputs for copy generation
- **Format**: [Matched format from Stage 1 deconstruction]
- **Style**: [Matched style from Stage 1 deconstruction]
- **Persona**: [User-provided]
- **Angle**: [User-provided]
- **Emotion**: [User-provided]
- **Product**: [User-provided]
- **Word count constraints**: [From the matched format spec's copy template]

### Copy generation process
1. Load the matched format spec from Project Knowledge (or use the format template embedded in /motion:ad-brief)
2. Use the copy template from the matched style
3. Write copy that fits the persona/angle/emotion
4. Verify against word count limits from the template
5. Run Agent 7 checklist:
   - Grammar check (subject-verb agreement, tense)
   - Spelling check (including brand name capitalization)
   - Punctuation check
   - Banned characters: NO em dashes (—), NO en dashes (–), NO semicolons in headlines
   - Number consistency
   - Duplicate content check (no data point appears twice)
   - Word count compliance (every element within spec)
6. Output the copy mapped to each text element slot

---

## STAGE 3: REBUILD FOR YOUR BRAND

Using the deconstruction (Stage 1) and approved copy (Stage 2), generate the complete Nano Banana 2 image prompt:

```
You are generating a social media ad creative. The output must be a finished, publication-ready image at [ASPECT RATIO] with all copy rendered directly in the image using the brand's fonts from the uploaded spec sheet.

CREATIVE ORIGIN:
This ad is inspired by a competitor's creative approach. We are borrowing the STRUCTURE and COMPOSITION techniques, not the copy, colors, or brand identity. The structural techniques being borrowed are: [LIST STEAL-WORTHY TECHNIQUES FROM STAGE 1 DECONSTRUCTION].

BRAND CONTEXT:
This is [BRAND NAME]. Reference the uploaded brand spec sheet for all visual identity decisions.
- Fonts: [FROM SPEC SHEET]
- Colors: [FROM SPEC SHEET]
- Voice: [FROM BRAND BRIEF]

PERSONA: [PERSONA NAME AND DESCRIPTION]
ANGLE: [ANGLE]
EMOTION: [EMOTION]
PRODUCT: [PRODUCT NAME AND KEY DETAILS]

COMPOSITION:
One continuous image filling the entire frame at [ASPECT RATIO].

[MAP THE COMPETITOR'S LAYOUT TO YOUR BRAND]:
- Product position: [MATCH COMPETITOR'S PRODUCT POSITION, USING YOUR PRODUCT]
- Text position: [MATCH COMPETITOR'S TEXT POSITION]
- Visual hierarchy: [MATCH COMPETITOR'S READING ORDER]
- Negative space: [MATCH COMPETITOR'S SPACING APPROACH]

COPY ELEMENTS:
This ad has exactly [N] text elements. No more.

[For each text element, mapped from the competitor's structure]:
1. [ROLE]: "[YOUR COPY]"
   - Font: [FROM SPEC SHEET]
   - Color: [FROM SPEC SHEET]
   - Treatment: [MATCH COMPETITOR'S TREATMENT — case, weight, spacing]

[Continue for each element]

SAFE ZONES:
Top 270px and bottom 340px of the frame kept clear of critical content. Left margin 40px. Right margin 120px from y=600 downward.

PRIMARY CONTENT ZONE: All critical content within x=40-960, y=270-1580.

COLOR AND TREATMENT:
Background: [YOUR BRAND'S BACKGROUND, NOT THE COMPETITOR'S]
Lighting: [MATCH COMPETITOR'S LIGHTING APPROACH, ADAPTED TO YOUR BRAND PALETTE]
The overall color treatment should feel like YOUR brand, even though the layout borrows from the competitor's structure.

BRAND IDENTITY:
Logo placed per brand spec sheet rules.

PHOTOGRAPHY DIRECTION:
[YOUR BRAND'S PHOTOGRAPHY STYLE FROM BRAND BRIEF]. The product must be accurately represented per the uploaded product image.

MOOD:
[MATCH THE COMPETITOR'S ENERGY LEVEL, FILTERED THROUGH YOUR BRAND'S VOICE].
The ad should feel like it was conceived natively for your brand, not like a reskin of someone else's creative.

RULES:
1. Exactly [N] text elements. No more. No offer bars, financing lines, or extra proof unless defined in the format spec.
2. Reference the uploaded brand spec sheet for ALL visual identity decisions.
3. The product must be accurately represented per the uploaded product image.
4. All critical content within the primary content zone.
5. No text smaller than 24px at 1080px width.
6. One continuous image. No panels, borders, or grid lines.
7. No em dashes anywhere in rendered copy.
8. Every data point (price, stat, claim) appears exactly once.
9. This must look like YOUR brand's ad, not a copy of the competitor's.
```

---

## EXECUTION WORKFLOW

```
1. User uploads competitor ad image
2. Confirm inputs: brand, product, persona, angle, emotion
3. Run Stage 1 — full deconstruction JSON output
4. Show "steal-worthy" techniques to user, confirm before proceeding
5. Run Stage 2 — generate copy + Agent 7 check
6. If Agent 7 fails: fix and re-run before proceeding to Stage 3
7. Run Stage 3 — build complete Nano Banana prompt
8. Output:

---
STAGE 1: DECONSTRUCTION
[Full JSON]

STEAL-WORTHY TECHNIQUES
[Bulleted list from deconstruction]

STAGE 2: APPROVED COPY (Agent 7: PASS)
[All text elements with word counts]

STAGE 3: IMAGE PROMPT (copy-paste into Nano Banana 2)
[Full prompt]

FORMAT REFERENCE
This ad maps to: [FORMAT] / [STYLE] from the Motion format spec library.
---
```

---

## Rules

1. Never copy a competitor's actual copy, tagline, or brand-specific language
2. The structural techniques are what we borrow, not the creative content
3. The output must pass YOUR brand's format spec constraints, not the competitor's
4. Agent 7 must sign off on all copy before it enters the prompt
5. The final ad must look like it was conceived for your brand from scratch
6. If the competitor ad uses a format/style not in our spec library, flag it and suggest the closest match
7. Always specify which format the rebuild maps to
8. Always list the specific steal-worthy techniques being borrowed so the user understands exactly what's being adapted
