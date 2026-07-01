---
name: shopping-feed
description: >
  This skill should be used when the user wants to check a Google Shopping
  product feed for title, description, and attribute problems. Trigger on
  phrases like "check my shopping feed", "audit my product titles", "fix my
  Merchant Center feed", "my shopping ads aren't showing", "optimize product
  titles", or when the user shares product feed data. Flags weak titles,
  missing attributes, and policy risks, and rewrites sample titles.
metadata:
  version: "0.1.0"
  author: "Sulka Labs"
---

# Shopping Feed: check titles and descriptions for issues

Audit a Google Shopping / Merchant Center product feed, flag what is costing impressions and clicks, and rewrite sample titles to the proven formula.

## Data needed

Product feed data: title, description, GTIN, brand, product type, Google product category, color, size, material, gender, age group, price, availability, image link. Even a partial export or a handful of products is enough to show the pattern. Follow `${CLAUDE_PLUGIN_ROOT}/shared/data-intake.md`.

## Title formula (the highest-leverage fix)

Shopping titles are the single biggest driver of which queries a product matches. Grade every title against this:

- **Front-load the most important keywords.** Google weights the first 70 characters heavily; the mobile SERP truncates around there.
- **Structure:** Brand + Product Type + key attributes (color, size, material, model, quantity, gender). Order by how customers search the category.
- **Length:** use the space, up to 150 characters, without keyword-stuffing gibberish.
- **Match search language:** use the words customers type, not internal SKUs or clever product names alone.
- Flag titles that lead with the brand when the brand has no search demand (lead with product type instead), and titles that are just a product name with no descriptive keywords.

## Attributes and data quality

Flag missing or weak fields, roughly in priority order:

1. **GTIN / brand** missing (hurts eligibility and matching).
2. **Google product category** and **product type** missing or too generic.
3. **Color, size, material, gender, age group** missing for apparel (these power filters and matching; missing them can disable free listings and some placements).
4. **Description** thin or duplicated from the title. Descriptions should restate keywords naturally and cover use case, materials, and specs in the first 150-500 characters.
5. **Image** low quality, has promo overlays (a policy violation), or is a placeholder.
6. **Price / availability** mismatches with the landing page (a top disapproval cause).
7. **Product highlights and additional images** unused.

## Policy and disapproval risks

Call out common triggers: promotional text or watermarks in images, price mismatches, missing GTIN on branded products, restricted-product language, and misleading titles.

## Output format

1. **Health summary:** what percent of the sample has weak titles, missing attributes, or policy risk.
2. **Systemic issues** ranked by impact, each with the fix applied across the whole feed.
3. **Rewritten titles:** take 5-10 real products and show Before to After with the reason.
4. **Attribute fix list:** which fields to populate, in priority order.
5. **One next step** (e.g., fix titles for the top 20 revenue products first).

No emojis, no em dashes.
