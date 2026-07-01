---
name: pmax-auditor
description: >
  This skill should be used when the user wants to audit a Google Ads
  Performance Max campaign and get a graded punch list of fixes. Trigger on
  phrases like "audit my PMax", "grade my Performance Max assets", "what's
  wrong with my PMax campaign", "review my asset groups", "PMax audit", or
  when the user shares Performance Max settings or asset group details.
  Grades each part of the campaign and returns prioritized fixes.
metadata:
  version: "0.1.0"
  author: "Sulka Labs"
---

# PMax Auditor: grade your assets, get a fix list

Audit a Performance Max campaign, grade each component A through F, and hand back a prioritized list of what to fix first.

## Data needed

Campaign settings and asset group details. Follow `${CLAUDE_PLUGIN_ROOT}/shared/data-intake.md`. If pulling from a connector, get asset group makeup, asset counts, audience signals, search themes, and campaign settings. Otherwise ask for screenshots or an export of the asset groups plus the settings page.

## What to grade

Score each area and explain the gap. Use this checklist:

1. **Account structure.** Is PMax split into logical asset groups by product theme, margin, or intent, rather than one catch-all? Are Shopping and PMax fighting over the same inventory? Grade structure and flag overlap.
2. **Asset quantity and strength.** Per asset group, check against Google's maximums: up to 5 headlines missing? Fewer than 4-5 long headlines? Under 4 descriptions? Fewer than the 20 image slots and 5 logos used well? Any video (if none, Google auto-generates a weak one)? Grade "Ad strength" drivers.
3. **Asset quality.** Are headlines benefit-led and distinct, or repetitive and generic? Are images a mix of lifestyle, product, and different aspect ratios (1:1, 1.91:1, 4:5)? Flag duplicate or low-res assets.
4. **Audience signals.** Are signals attached (customer lists, custom segments from competitor and category search terms, website visitors)? Empty signals slow learning. Grade signal quality.
5. **Search themes.** Present and relevant (up to 25)? Missing high-intent themes?
6. **Listing groups** (for retail). Are low-margin or out-of-stock products excluded? Is the feed segmented?
7. **Brand controls.** Brand exclusions applied so PMax is not just harvesting cheap brand traffic and inflating ROAS? This is the most common way PMax looks better than it is. Always check and call it out.
8. **Final URL expansion.** On or off, and is that right for the account? Are URL exclusions set?
9. **Settings hygiene.** Geo targeting set to "presence" not "presence or interest" unless intended, ad schedule, campaign exclusions, conversion goals aligned to real value (not counting micro-conversions as purchases).

## Output format

1. **Overall grade** and a one-paragraph verdict.
2. **Scorecard table:** each area, letter grade, one-line reason.
3. **Prioritized fixes** — numbered, highest-impact first, each with the specific action. Lead with brand exclusions and audience signals if those are weak, since they distort everything else.
4. **Quick wins** the user can do today vs **structural fixes** that need a rebuild.
5. **One next step.**

No emojis, no em dashes.
