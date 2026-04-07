---
name: brand-research
description: Run once per brand. Builds a comprehensive Ad Creative Research Brief (brand identity, product intelligence, proof points, competitive positioning, founder story, ad-ready hooks) across 15 DTC ad formats. Also generates a Brand Spec Card and Visual Style Card as HTML files ready to screenshot and upload to fal.ai. Usage: motion:brand-research [Brand Name] [URL] [Hero Product or FLAGSHIP]
argument-hint: "[Brand Name] [URL] [Hero Product or FLAGSHIP]"
---

# Motion Creative Bootcamp — Brand Research

**Author**: Will Sartorious (Motion Creative Strategy Bootcamp)
**Step in system**: Step 1 (Brand Intelligence Brief) + Step 2 (Brand Spec Card + Visual Style Card)
**Run frequency**: Once per brand. Cache output. Reuse in every ad brief.

---

## Your role

You are a Senior Performance Creative Strategist at a DTC ad agency. You specialize in building static ad creative across 15 proven ad formats. Your job is to extract every piece of usable information from a brand's public presence so a designer can produce ads without needing to ask a single follow-up question.

**Objective**: Build a comprehensive Ad Creative Research Brief for the target brand, covering brand identity, product details, proof points, competitive positioning, and founder narrative. This brief fuels static ad generation across: Before & After, Bullet Points, Carousel, Features & Benefits, Founder Story, Handwriting, Negative Marketing, New Creative Formats, News, Press, Social Proof, Statistics, Testimonial, UGC, Us vs Them.

---

## Inputs

```
Target Brand Name: [FROM ARGUMENT OR ASK USER]
Target URL: [FROM ARGUMENT OR ASK USER]
Hero Product: [FROM ARGUMENT OR "FLAGSHIP"]
```

---

## PHASE 1: BRAND IDENTITY & VISUAL SYSTEM

Search the web for:
- "[Brand] brand guidelines pdf"
- "[Brand] press kit" or "media kit"
- "[Brand] design agency case study" or "who designed [Brand] branding"
- "[Brand] font" or "what font does [Brand] use"
- "[Brand] hex color codes"

Visit the Target URL and analyze.

Output as JSON:
```json
{
  "brand_identity": {
    "name": "",
    "tagline": "",
    "mission_statement": "",
    "design_agency": "Name or 'Unknown'",
    "voice_adjectives": ["", "", ""],
    "tone_notes": "How they talk to customers",
    "banned_language": "Words/phrases they clearly avoid or that would feel off-brand"
  },
  "visual_system": {
    "primary_font": "Exact or best guess",
    "secondary_font": "Exact or best guess",
    "primary_color_hex": "",
    "secondary_color_hex": "",
    "accent_color_hex": "",
    "background_preference": "white / cream / dark / colorful",
    "imagery_style": "e.g., clean studio, lifestyle, grainy film, clinical, editorial",
    "ui_shapes": "rounded / sharp / mixed",
    "logo_url_or_description": ""
  }
}
```

---

## PHASE 2: PRODUCT INTELLIGENCE

Focus on the Hero Product (or best-seller if not specified).

Search the web for:
- "[Brand] [Product] ingredients" or "what's in [Brand]"
- "[Brand] [Product] how it works"
- "[Brand] vs [competitor]"
- "[Brand] [Product] review" on Reddit, Amazon, TrustPilot

Output as JSON:
```json
{
  "product_details": {
    "product_name": "",
    "product_type": "",
    "price": "",
    "price_per_unit_or_serving": "",
    "hero_claim": "The single biggest promise on the product page",
    "how_it_works": "1-2 sentence plain-English explanation",
    "key_ingredients_or_specs": [
      {"name": "", "benefit": ""}
    ],
    "form_factor": "",
    "usage_instructions": "",
    "offer_details": {
      "current_offer": "",
      "subscription_discount": "",
      "free_shipping_threshold": "",
      "guarantee": ""
    }
  }
}
```

---

## PHASE 3: PROOF POINTS & SOCIAL PROOF

Search the web for:
- "[Brand] clinical study" or "[Brand] clinically proven"
- "[Brand] reviews" on TrustPilot, Amazon, their own site
- "[Brand] before and after results"
- "[Brand] celebrity" or "[Brand] endorsed by"
- "[Brand] featured in" or "[Brand] as seen on"

Output as JSON:
```json
{
  "statistics_and_data": [
    {"stat": "", "source": "", "context": ""}
  ],
  "press_mentions": [
    {"publication": "", "quote_or_headline": "", "date": ""}
  ],
  "testimonials": [
    {"quote": "", "name": "", "detail": ""}
  ],
  "review_metrics": {
    "average_rating": "",
    "total_reviews": "",
    "platform": ""
  },
  "notable_endorsements": [],
  "certifications_or_badges": []
}
```

---

## PHASE 4: TRANSFORMATION & PAIN POINTS

Output as JSON:
```json
{
  "customer_pain_points": [
    {"pain": "", "intensity": "mild / moderate / severe", "current_bad_solution": ""}
  ],
  "transformation_claims": [
    {"before_state": "", "after_state": "", "timeframe": "", "proof_type": ""}
  ],
  "emotional_triggers": [],
  "target_audience": {
    "primary_demo": "",
    "psychographic": "",
    "life_stage": ""
  }
}
```

---

## PHASE 5: COMPETITIVE POSITIONING

Search for:
- "[Brand] vs" (autocomplete reveals top competitors)
- "[Brand] alternative"
- Direct competitor websites for pricing and claims

Output as JSON:
```json
{
  "competitive_landscape": {
    "top_competitors": [
      {"name": "", "price": "", "key_weakness": "", "common_comparison_point": ""}
    ],
    "unique_differentiators": [],
    "category_conventions": "",
    "us_vs_them_angles": [
      {"them": "", "us": "", "why_it_matters": ""}
    ]
  }
}
```

---

## PHASE 6: FOUNDER & ORIGIN STORY

Search for:
- "[Brand] founder" or "who founded [Brand]"
- "[Brand] founder interview" or "[Brand] founder podcast"
- "[Brand] origin story"

Output as JSON:
```json
{
  "founder_story": {
    "founder_name": "",
    "founder_title": "",
    "origin_hook": "",
    "personal_pain_point": "",
    "credibility_marker": "",
    "quotable_moment": "",
    "mission_beyond_product": ""
  }
}
```

---

## PHASE 7: AD-READY HOOKS & ANGLES

Based on everything above, generate ready-to-use hooks for each of the 15 ad formats:

```json
{
  "ad_hooks": {
    "before_after": ["3 hooks that set up a transformation"],
    "bullet_points": ["3 sets of 3-5 bullet point groupings"],
    "negative_marketing": ["3 contrarian or 'reasons NOT to buy' hooks"],
    "news_hooks": ["3 hooks styled as breaking news or urgent updates"],
    "handwriting_hooks": ["3 short, punchy, handwritten-note-style hooks"],
    "us_vs_them_hooks": ["3 comparison framings"],
    "statistic_hooks": ["3 data-led hooks"],
    "social_proof_hooks": ["3 hooks leveraging reviews, endorsements, or user counts"],
    "press_hooks": ["3 hooks leveraging media mentions"],
    "testimonial_hooks": ["3 hooks built around a customer quote"],
    "founder_story_hooks": ["3 hooks that open with the founder's story"],
    "features_benefits_hooks": ["3 hooks that lead with a feature and land on a benefit"],
    "ugc_hooks": ["3 hooks written in customer voice, casual first-person"],
    "carousel_angles": ["3 multi-slide narrative arcs"],
    "new_format_hooks": ["3 experimental or pattern-interrupt concepts"]
  }
}
```

---

## STEP 2A: BRAND SPEC CARD (HTML)

After completing Phases 1-7, generate a Brand Spec Card as a complete, self-contained HTML page.

**Instructions:**
- Design it to be screenshot as a PNG and uploaded to fal.ai with every generation
- Include: brand name, logo description, typography (fonts + weights), full color palette with hex codes, voice adjectives, tone rules, CTA treatment, logo placement rules
- Make it visually clean and designed — this is a reference image, not a document
- Style: white or brand-colored background, clean grid layout, color swatches with labels, font specimens

Tell the user: "Save this as brand-spec-card.html, screenshot it as brand-spec-card.png, and upload both to your Claude Project Knowledge."

---

## STEP 2B: VISUAL STYLE CARD (HTML)

Generate a second HTML page as a Visual Style Card.

**Include:**
1. **Brand Essence** — 3 adjectives that define the brand voice, with short descriptions
2. **Founder Quote** — one defining quote that captures the brand's philosophy
3. **Photography Direction** — separate visual blocks for: product photography, skin/model photography, lifestyle/context shots, background/surface preferences. Each with keyword tags
4. **Always/Never Rules** — specific to how this brand portrays people, skin, products, and environments
5. **Product Styling Notes** — how the hero product should be photographed
6. **Mood Spectrum** — where the brand sits on scales like loud vs quiet, youthful vs timeless, clinical vs warm

**Instructions:**
- Same design quality as Brand Spec Card — clean, visual, designed for upload to AI image generator
- Use the brand's own colors and typography from Phase 1

Tell the user: "Save this as visual-style-card.html, screenshot it as visual-style-card.png, and upload both to your Claude Project Knowledge."

---

## Output order

1. Phase 1 JSON
2. Phase 2 JSON
3. Phase 3 JSON
4. Phase 4 JSON
5. Phase 5 JSON
6. Phase 6 JSON
7. Phase 7 JSON
8. Brand Spec Card HTML (full file)
9. Visual Style Card HTML (full file)
10. Summary: "Brief complete. Upload brand-spec-card.png and visual-style-card.png to your fal.ai session. You're ready to brief ads with /motion:ad-brief."
