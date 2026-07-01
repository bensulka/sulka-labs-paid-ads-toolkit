---
name: negative-keywords
description: >
  This skill should be used when the user wants to find wasted spend in a
  Google Ads account and build a negative keyword block list. Trigger on
  phrases like "find wasted spend", "negative keywords", "build a block list",
  "clean up my search terms", "what should I negative out", "where am I
  wasting money on Google Ads", or when the user pastes a Google Ads search
  terms report. Produces exact-match and phrase-match negative lists grouped
  by theme, with the reason and estimated spend recovered for each.
metadata:
  version: "0.1.0"
  author: "Sulka Labs"
---

# Negative Keywords: find wasted spend, build a block list

Analyze a Google Ads search terms report, find spend that is not producing conversions or is off-intent, and return a ready-to-paste negative keyword list.

## Data needed

A search terms report covering the last 30-90 days with, at minimum: search term, campaign, cost, clicks, conversions, and conversion value. More columns (ad group, match type, CTR, cost/conv) sharpen the analysis.

Follow the intake pattern in `${CLAUDE_PLUGIN_ROOT}/shared/data-intake.md`: try a connected account first, otherwise have the user export or paste the search terms report.

## How to analyze

Work through every search term and flag it against these waste patterns:

1. **Zero-conversion spend drain.** Terms with cost above the account's target CPA (or above roughly 1.5x the average cost per conversion if CPA is unknown) and zero conversions. These are the highest-priority blocks.
2. **Off-intent and irrelevant.** Terms that do not match what the business sells (wrong product, wrong category, unrelated meaning of a keyword).
3. **Informational / research intent.** "how to", "what is", "DIY", "free", "template", "tutorial", "meaning", "vs" comparisons where the business is not the answer.
4. **Job / career / wholesale / used.** "jobs", "salary", "careers", "used", "cheap", "wholesale", "bulk", "supplier" when those do not fit the offer.
5. **Competitor and brand terms** the account should not pay for (unless the strategy is deliberate conquesting, in which case flag, do not block).
6. **Low-intent modifiers** bleeding budget: "reviews" (sometimes keep), "images", "near me" if not local, wrong geography.

For each flagged term, estimate recovered spend = cost of the term over the report window. Sum it into a headline "wasted spend recovered per period" number.

## Match type and level guidance

- Recommend **exact-match negatives** for specific bad terms and **phrase-match negatives** for recurring bad tokens (e.g., phrase negative "free" or "jobs" that kills a whole family of queries). Warn that phrase negatives are broader and to sanity-check them against good terms.
- Recommend the **level**: block at account level for universally irrelevant tokens (via a shared negative list), campaign level for campaign-specific noise, ad group level for tight themes.
- Flag any term that is borderline as **"watch, do not block yet"** so the user does not cut a term that is one conversion away from proving out.

## Output format

1. **Headline:** estimated wasted spend recovered over the window, and the count of terms blocked.
2. **Exact-match negatives** — a clean, copy-paste block, grouped by theme (Off-intent, Informational, Job/used/wholesale, Competitor, Geo).
3. **Phrase-match negatives** — copy-paste block of recurring bad tokens, each with a one-line reason.
4. **Recommended shared negative list** for account-level application.
5. **Watch list** — borderline terms to monitor, not block.
6. **One next step** — e.g., "add these as an account-level negative list, then re-pull in 14 days."

Keep the negative lists as plain lists the user can paste straight into Google Ads. Do not use emojis or em dashes.
