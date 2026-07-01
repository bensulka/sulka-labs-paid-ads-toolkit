---
name: hook-optimizer
description: >
  This skill should be used when the user wants to rewrite the first three
  seconds of a Meta video ad to stop the scroll. Trigger on phrases like
  "rewrite my hook", "fix my first 3 seconds", "my ad isn't stopping the
  scroll", "new hooks for [product]", "hook ideas", "improve my thumbstop
  rate", or when the user shares a video ad or concept and wants stronger
  openers. Returns 10+ new hooks across proven frameworks, verbal and visual.
metadata:
  version: "0.1.0"
  author: "Sulka Labs"
---

# Hook Optimizer: rewrite the first 3 seconds

The first three seconds decide whether an ad gets watched. Diagnose why the current hook is weak and generate a batch of stronger ones across proven frameworks.

## Data needed

No export required. Ask for:

- The product and the core promise
- The current hook (paste the opening line, describe the first frames, or attach the video)
- The audience and their pain or desire
- Current hook rate / thumbstop rate if known (under 20% means the opener is the problem)

If a connected account is available, pull the hook rate to confirm this is the bottleneck (`${CLAUDE_PLUGIN_ROOT}/shared/data-intake.md`).

## Diagnose first

Say in one or two lines why the current hook is losing people. Common failures: slow build-up, brand logo or product beauty shot with no tension, buried value, generic claim, no motion or face in frame, text too small or too late, the promise arrives after the scroll decision.

## Generate hooks across frameworks

A hook has three layers that must fire in the first 3 seconds: the **visual** (what fills the frame), the **verbal** (first spoken line), and the **text overlay** (on-screen words). Write hooks that specify all three, not just a caption.

Use these frameworks and give at least one hook per framework:

1. **Callout** — name the exact audience ("If you drive a diesel truck...").
2. **Problem** — open on the pain, visually and verbally.
3. **Bold claim / result** — lead with the outcome or a number.
4. **Curiosity gap** — tease something they must keep watching to resolve.
5. **Pattern interrupt** — an unexpected visual, sound, or statement.
6. **Social proof** — "12,000 people switched because..." or a reaction shot.
7. **Before / after** — show the transformation up front.
8. **Question** — a question they answer "yes" to in their head.
9. **Us vs them / myth-bust** — challenge the thing they currently believe or use.
10. **Founder / confession** — a real person saying something honest and specific.

Rules: front-load the value, use motion and a human face or hands early, keep the first spoken line under about 8 words, put readable text on screen in the first second, and make sure the hook is congruent with the rest of the ad (no bait and switch).

## Output format

1. **Diagnosis:** why the current hook underperforms (2-3 lines).
2. **10+ hooks**, each labeled with its framework and written as: Visual + Verbal (first line) + Text overlay.
3. **Top 3 to test first** and why.
4. **Production note:** the one filming or editing change that would lift thumbstop most.

No emojis, no em dashes.
