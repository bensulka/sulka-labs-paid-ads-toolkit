---
name: search-terms
description: >
  This skill should be used when the user wants to mine a Google Ads search
  terms report for winners and losers. Trigger on phrases like "review my
  search terms", "find winning keywords", "which search terms are working",
  "surface winners and losers", "what keywords should I add", or when the
  user pastes a search terms report and wants both keywords to add and terms
  to block. Splits terms into add, block, and watch, with the action for each.
metadata:
  version: "0.1.0"
  author: "Sulka Labs"
---

# Search Terms: surface winners and losers

Read a Google Ads search terms report and split it into three actions: keywords to add, terms to block, and terms to watch. This is the offense-and-defense companion to the negative-keywords skill.

## Data needed

A search terms report, last 30-90 days, with: search term, campaign, ad group, match type, cost, clicks, conversions, conversion value, CTR. Follow `${CLAUDE_PLUGIN_ROOT}/shared/data-intake.md`.

## How to analyze

Establish the account's benchmarks first: average CPA, average ROAS, and average CTR across the report. Then classify every term.

**Winners (add).** Terms that:

- Converted at or above the account average, or at strong ROAS, AND
- Are not already added as keywords (or are only being served through broad/PMax), AND
- Show clear commercial intent.

For each winner, recommend: add as **exact or phrase match**, which ad group or a new tightly themed ad group, and a starting bid or "match existing." Flag high-volume winners that deserve their own ad group with tailored RSAs.

**Losers (block).** High cost, zero or poor conversions, or off-intent. Recommend exact or phrase negatives and the level. (For a deep block list, point the user to the negative-keywords skill.)

**Watch.** Terms with promise but not enough data: some clicks, one conversion, or spend just under the CPA threshold. Recommend a spend or click threshold to revisit them.

Also surface:

- **Intent gaps:** clusters of winning terms that reveal a new angle, product, or ad group the account is not covering.
- **Match-type leakage:** broad keywords pulling in unrelated queries, which signals a structure fix.
- **Brand vs non-brand split:** how much spend and conversion is brand (cheap, high ROAS) vs non-brand (the real growth), so ROAS is not being flattered by brand.

## Output format

1. **Snapshot:** window, total spend, blended CPA/ROAS, brand vs non-brand split.
2. **Add these keywords** — table: term, suggested match type, destination ad group, why.
3. **Block these** — quick list with reason (or defer to negative-keywords for the full list).
4. **Watch these** — with the revisit threshold.
5. **Opportunities** — new ad groups or angles the winners reveal.
6. **One next step.**

No emojis, no em dashes.
