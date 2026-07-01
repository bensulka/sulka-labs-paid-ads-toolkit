---
name: audience-builder
description: >
  This skill should be used when the user wants Meta ad targeting ideas built
  from their customer profile. Trigger on phrases like "build a Meta audience",
  "find targeting options", "who should I target on Facebook", "interest
  ideas for my ads", "lookalike strategy", "audience for [product]", or when
  the user describes their customer and wants targeting. Returns interest
  stacks, lookalike and custom audience plans, exclusions, and a test map.
metadata:
  version: "0.1.0"
  author: "Sulka Labs"
---

# Audience Builder: targeting from your customer

Turn a description of the ideal customer into a concrete Meta targeting plan: interests, lookalikes, custom audiences, exclusions, and a testing structure.

## Data needed

No export required. Ask for:

- Who buys this and why (demographics, identity, life stage, the job the product does)
- The product, price point, and category
- What the customer reads, watches, follows, and buys adjacent to this
- Current data assets: pixel/CAPI installed, email list size, purchaser volume, video content
- Monthly budget (drives how many audiences to test at once)

Pull seed-audience sizes from a connected account if available (`${CLAUDE_PLUGIN_ROOT}/shared/data-intake.md`).

## What to build

**1. Custom audiences (first-party, highest value).** List the ones to create: purchasers, high-LTV purchasers, add-to-cart no purchase, site visitors (30/60/180 day), video viewers (25/50/75%), IG and FB engagers, email subscribers, and a suppression list of recent buyers.

**2. Lookalikes.** Recommend seed sources in priority order (value-based LTV lookalike > purchasers > add-to-cart > engagers) and percentages to test (1%, 1-3%, 3-5%). Note when the list is too small to seed and what to use instead.

**3. Interest and behavior stacks.** Build 3-6 themed stacks, each grouped by a logic (category buyers, competitor/brand affinity, lifestyle/identity, adjacent hobbies, life events). For each stack, list the specific interests and behaviors and the reasoning. Keep each stack broad enough to exit learning.

**4. Broad and Advantage+ direction.** State plainly that on modern Meta, broad targeting plus strong creative and Advantage+ audience often beats hand-built interests. Recommend how to split budget between broad/Advantage+ and interest tests given the account's size, rather than defaulting to heavy interest stacking.

**5. Exclusions.** Recent purchasers from prospecting, employees, and any irrelevant geos or ages.

**6. Retargeting tiers.** Warm (engagers, viewers), hot (site visitors, ATC), and the offer/message each tier should get.

## Output format

1. **Custom audiences to create** — checklist.
2. **Lookalike plan** — seed, percentages, priority.
3. **Interest stacks** — each named, with the interests and the logic.
4. **Broad vs interest budget split** recommendation for this account size.
5. **Exclusions** and **retargeting tiers.**
6. **Test map:** what to launch first with the stated budget, and how to read results.

No emojis, no em dashes.
