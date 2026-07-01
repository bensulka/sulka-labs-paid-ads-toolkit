---
name: creative-analyzer
description: >
  This skill should be used when the user wants their Meta ad creatives scored
  and explained. Trigger on phrases like "score my ads", "analyze my
  creatives", "why is this ad working", "which creative is best", "is my ad
  fatiguing", "what's working in my creative", or when the user shares
  creative performance data or the creatives themselves. Scores each creative,
  diagnoses fatigue, and recommends iterations of the winners.
metadata:
  version: "0.1.0"
  author: "Sulka Labs"
---

# Creative Analyzer: score your ads, explain what's working

Score Meta creatives, diagnose why the winners win and the losers lose, and prescribe the next iterations.

## Data needed

Creative-level performance and/or the creatives. Useful metrics: amount spent, impressions, frequency, CTR (all) and CTR (link), CPC, CPM, hook rate (3-second / thumbstop), hold rate (ThruPlay or 15-sec), results, cost per result, purchase ROAS, and adds to cart. Attach the actual image or video where possible. Follow `${CLAUDE_PLUGIN_ROOT}/shared/data-intake.md`.

## Benchmarks to judge against

Use these as directional goalposts, adjusting for vertical and price point:

- **Hook rate (3-sec views / impressions):** roughly 25-30%+ is healthy; under 20% means the first frame is losing people.
- **Hold rate (ThruPlay / impressions):** varies by length; declining hold means the middle sags.
- **CTR (link):** roughly 1%+ on prospecting is a reasonable floor; well above average signals a strong offer/hook.
- **Frequency:** creeping past 2.5-3 in a short window on a set audience signals fatigue.
- **CPA / ROAS vs the account target** is the final arbiter; a great hook that does not convert is a landing-page or offer problem, not a creative win.

State that benchmarks are directional and the account's own averages are the real baseline.

## How to analyze

For each creative:

1. **Score it** (simple A-F or 1-10) on hook, hold, click, and convert, then overall.
2. **Diagnose the funnel step that breaks:** low hook rate = weak first 3 seconds (point to the hook-optimizer skill); good hook but low hold = weak middle/pacing; good hold but low CTR = weak CTA or unclear offer; good CTR but low ROAS = landing page, price, or audience mismatch.
3. **Fatigue check:** rising frequency with falling CTR and rising CPA over time = retire or refresh.
4. **Name the winning elements:** the specific hook, format (UGC, static, testimonial, demo), angle, and offer that are driving results, so they can be reused.

Across the set, find the **patterns**: which angles, formats, and hooks consistently win, and which are dead. That pattern is the brief for the next batch.

## Output format

1. **Leaderboard:** creatives ranked, each with its score and one-line verdict.
2. **What's working:** the 2-4 winning elements to double down on.
3. **What's fatiguing / dead:** what to cut and why.
4. **Iteration briefs:** for each winner, 2-3 specific new variations to test (new hook, new format, same angle).
5. **One next step.**

No emojis, no em dashes.
