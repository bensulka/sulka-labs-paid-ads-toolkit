---
name: ad-copy
description: >
  This skill should be used when the user wants Meta (Facebook and Instagram)
  ad copy written in their brand voice. Trigger on phrases like "write Meta ad
  copy", "primary text for my Facebook ad", "write ads in my voice", "new
  Meta ad for [product]", "give me primary text and headlines", or when the
  user shares a product and wants scroll-stopping Facebook/Instagram copy.
  Produces multiple primary text angles plus headlines and descriptions.
metadata:
  version: "0.1.0"
  author: "Sulka Labs"
---

# Ad Copy: primary text that matches your voice

Write Meta ad copy that sounds like the brand and is built on proven direct-response angles, not generic hype.

## Data needed

No export required. Ask for:

- Product or offer and the core promise
- Ideal customer and the pain or desire that drives the purchase
- **Brand voice samples** (paste 1-3 existing ads, emails, or site copy) so the output matches tone
- Awareness level of the audience (problem-unaware, problem-aware, solution-aware, product-aware) since this changes the opening
- Proof: reviews, numbers, guarantees, press
- Any promo or urgency, and the CTA / landing page

If a connected account is available, pull the top-performing existing copy to match voice and beat the control (see `${CLAUDE_PLUGIN_ROOT}/shared/data-intake.md`).

## How to write

Match voice first. Mirror the sentence length, punctuation, and vocabulary of the samples. If no samples exist, ask for tone and default to clear, conversational, and specific. Cut AI tells ("unlock", "elevate", "seamless", "in today's world").

Write **primary text in several distinct angles** so the user can test, not five versions of the same idea:

1. **Problem / Agitate / Solve** — name the pain, twist it, resolve with the product.
2. **Testimonial / voice-of-customer** — lead with a real-sounding customer line.
3. **Us vs the old way** — contrast the product against the frustrating status quo.
4. **Listicle / reasons** — "3 reasons [customer] switched to [product]".
5. **Founder / origin** — why the product exists, told plainly.

Rules for every variation:

- **First line is a hook** that works before the "see more" cut (roughly the first 125 characters). Front-load the strongest idea.
- Short lines and white space. One idea per line.
- Concrete over clever: specifics, numbers, and sensory detail beat adjectives.
- End with one clear CTA.
- Keep it compliant: no unrealistic claims, no "you" health/financial guarantees, no before/after promises that violate Meta policy.

## Output format

1. **5 primary text variations**, each labeled with its angle. Mark the hook line.
2. **5 headlines** (short, 5-7 words, benefit or offer).
3. **3 descriptions** (optional link description line).
4. **Voice note:** one line on how these match the samples and which to test first.

No emojis unless the brand voice samples use them. No em dashes.
