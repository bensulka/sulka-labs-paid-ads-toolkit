---
name: rsa-generator
description: >
  This skill should be used when the user wants to write Google Ads
  responsive search ads that sound human, not robotic. Trigger on phrases
  like "write RSAs", "responsive search ad", "write Google Ads copy", "my
  ads sound robotic", "generate headlines and descriptions", "new search ad
  for [product]", or when the user shares a product or landing page and wants
  search ad copy. Produces 15 headlines and 4 descriptions with character
  counts, pinning guidance, and Ad Strength notes.
metadata:
  version: "0.1.0"
  author: "Sulka Labs"
---

# RSA Generator: write ads that don't sound robotic

Write a complete responsive search ad that reads like a human wrote it, fits Google's limits, and is built to hit "Excellent" Ad Strength.

## Data needed

No export required. Ask for (and infer what you can from a landing page URL):

- Product or service and the single most important offer or hook
- Top 3-5 target keywords or the ad group theme
- Primary benefits and proof (numbers, guarantees, shipping, reviews)
- Brand name and tone (premium, playful, no-nonsense)
- Any promo, price, or urgency

Follow `${CLAUDE_PLUGIN_ROOT}/shared/data-intake.md` if pulling context from a connected account.

## Rules and limits

- **15 headlines**, each 30 characters or fewer. Count every character and show the count.
- **4 descriptions**, each 90 characters or fewer. Show counts.
- Write to the limit without going over. Never pad with filler to fake a benefit.
- Make headlines **distinct** across these buckets so Google has real variety to test: keyword-match headlines, benefit headlines, offer/price headlines, social proof, urgency/CTA, brand, and objection-handlers. Avoid three headlines that say the same thing.
- Sound human: active verbs, plain words, specifics over adjectives. Cut "unlock", "elevate", "seamless", "revolutionary", and other AI tells. Read each headline aloud in your head; if it sounds like a template, rewrite it.
- Work the primary keyword into 3-4 headlines and at least one description for relevance, but do not keyword-stuff.
- Descriptions lead with the benefit, then proof, then a CTA.

## Pinning guidance

Recommend a light pinning strategy, not heavy pinning (which kills Ad Strength):

- Optionally pin one brand or offer headline to position 1 or 3 if the business needs message control.
- Leave the rest unpinned so Google can optimize combinations.
- Explain the trade-off in one line so the user chooses knowingly.

## Output format

1. **Headlines (15)** as a numbered list, each with its character count and its bucket label.
2. **Descriptions (4)** with character counts.
3. **Pinning recommendation** in 2-3 lines.
4. **Ad Strength note:** why this set should score well (variety, keyword coverage, distinct assets) and the one thing to add if the user wants more.
5. Optional: 2 display path suggestions (15 characters each).

No emojis, no em dashes.
