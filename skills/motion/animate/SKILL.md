---
name: animate
description: Turn a winning static ad into a 3-4 second animation in 15 minutes. 5-step workflow: ideate concepts → generate missing frame with Nano Banana 2 → get Veo 3.1 JSON prompt → animate via Google Flow → iterate. Key insight: you create a start frame and end frame, then let AI interpolate between them. Usage: motion:animate (upload your static ad first)
argument-hint: "[optional: describe your animation idea or just upload the static]"
---

# Motion Creative Bootcamp — Animate Your Statics

**Author**: Will Sartorious (Motion Creative Strategy Bootcamp)
**Step in system**: Bonus (after a static ad is approved and generated)
**Requires**: A winning static ad image uploaded to the conversation

---

## The key insight

You are NOT asking AI to "animate your ad." You create a **start frame** and an **end frame**, then let AI interpolate between them. This produces clean, controlled motion instead of AI hallucinating movement.

**Rules for every animation:**
- All text stays frozen in place throughout — no movement, no warping, no fading
- No camera movement whatsoever
- 3-4 seconds max (use 8-second Veo output, trim to 3-4)
- Always use Veo 3.1 Fast mode via Google Flow
- Cap at 3-4 iterations before starting fresh

---

## STEP 1: IDEATE — Get 5 animation concepts

Upload your static ad to the conversation, then use this prompt:

```
I want to animate this static ad. Give me 5 animation concepts.

For each one tell me:
(1) Is my static the START or END frame?
(2) What does the other frame look like — describe it in detail?
(3) What motion happens between the two frames?
(4) Why does this motion make sense for the product?

Rules: all text must stay frozen in place throughout the animation, no camera movement, 3-4 seconds max
```

Choose 1 concept and note whether your static is the START or END frame.

---

## STEP 2: GENERATE THE MISSING FRAME — Nano Banana 2

After choosing your concept, generate the other frame as a still image using this prompt:

```
I want to animate this static ad. The concept is: [describe your chosen concept from Step 1, e.g. "gummy bears march into frame and lift the product up into position. My static is the END frame."]

My static is the [START / END] frame.

I need you to write a Nano Banana 2 prompt to generate the other frame as a still image. Based on the animation concept, figure out which elements need to be added, removed, or repositioned in the missing frame.

Every piece of text must be reproduced verbatim — same words, same position, same fonts, colors, and sizing. The background, lighting, and overall style must match my static exactly. Only change what needs to be different for the other frame of the animation.

The prompt must specify exact dimensions (1080x1920). I will upload my original static as a reference image — tell the generator to match everything from it except the elements that change between frames.

Be extremely detailed — NB2 won't guess, it only does what you tell it.
```

Take the Nano Banana 2 prompt → run it in fal.ai with your static as reference → you now have both frames.

---

## STEP 3: GET THE VEO 3.1 JSON PROMPT

Upload BOTH frames to a new Claude conversation, then use this prompt:

```
I'm uploading two frames for a video animation.

IMAGE 1 is the START frame.
IMAGE 2 is the END frame.

The animation concept: [describe your concept, e.g. "gummy bears march into frame and lift the product up into its final position."]

Write me a comprehensive Veo 3.1 JSON prompt that creates a smooth 8 second animation from the start frame to the end frame.

The prompt MUST include:
- Every piece of text from both frames reproduced verbatim so the fonts don't degrade during generation
- Explicit instruction that ALL text stays completely frozen in place throughout — no movement, no warping, no fading
- No camera movement whatsoever
- The background stays perfectly still
- A detailed description of the motion: what enters, from where, how it moves, the physics and easing
- The animation must resolve cleanly into the end frame as its final resting state
- Describe what stays still and what moves — be explicit about both

Format as a ready-to-paste JSON prompt for Veo 3.1.
```

---

## STEP 4: ANIMATE — Google Flow (Veo 3.1)

1. Go to [labs.google/flow](https://labs.google/flow)
2. Use Veo 3.1 **Fast/Lower Priority** mode (not Standard — too slow, not worth it)
3. Paste the JSON prompt from Step 3
4. Generate 4-8 variations
5. Download the best one as a GIF

---

## STEP 5: ITERATE — Fix problems

Download the GIF, upload it to Claude along with both original frames, then use this prompt:

```
I'm uploading the animation output plus my original start frame and end frame for reference.

Here's what's wrong with the animation:
[describe your issues — e.g. "no gummy bears appeared, the text warps at 3 seconds, the tube just floats up on its own instead of being lifted, there's a weird color shift in the background"]

Give me a corrected Veo 3.1 JSON prompt that fixes these issues. Keep everything that worked well.
```

Iterate up to 3-4 times. If you can't get it working after 4 tries, pick a simpler animation concept from Step 1 and start over.

---

## Quick reference: what this skill does step by step

```
1. User uploads static ad
2. Claude generates 5 animation concepts (prompt above)
3. User picks one → Claude writes Nano Banana 2 prompt for missing frame
4. User generates missing frame in fal.ai
5. User uploads both frames → Claude writes Veo 3.1 JSON prompt
6. User animates in Google Flow (Veo 3.1 Fast)
7. User downloads GIF → if iteration needed, Claude fixes the prompt
```

---

## When to run this skill

Run after a static ad has been **approved by all 7 agents** AND **generated in fal.ai**. Only animate winners — don't waste Veo credits on untested creative.
