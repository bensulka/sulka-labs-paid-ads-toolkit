# Sulka Labs Paid Ads Toolkit

Ten drop-in skills that audit and improve Google Ads and Meta Ads accounts. Find wasted spend, grade campaigns, write ads that sound human, build audiences, and stop the scroll.

Built to work for any brand, on any account. There is no sales pitch in the output. Just the work.

Works two ways:

- **With a connected ad account** (Supermetrics, or a native Google Ads / Meta connector) the skills pull data automatically.
- **Without one**, they tell you exactly what to export or paste, then work from that. No API keys, no code.

## How to use

1. Install this plugin in Claude.
2. Optional: open `shared/brand-profile.md` and fill it in once. Every skill reads it, so the toolkit adapts to your brand, voice, and targets without you re-entering them.
3. Optional: connect Google Ads and Meta Ads (via a connector like Supermetrics).
4. Tell Claude what you need in plain language, for example "find wasted spend in my Google Ads" or "rewrite my hook."
5. Claude loads the right skill and either pulls your data or asks for the export.

## The skills

### Google Ads

| Skill | What it does |
| --- | --- |
| `negative-keywords` | Finds wasted spend and builds an exact and phrase-match block list |
| `pmax-auditor` | Grades your Performance Max assets and tells you what to fix |
| `rsa-generator` | Writes responsive search ads that don't sound robotic |
| `search-terms` | Surfaces winners and losers in your search terms report |
| `shopping-feed` | Checks product titles, descriptions, and attributes for issues |

### Meta Ads

| Skill | What it does |
| --- | --- |
| `ad-copy` | Writes primary text that matches your brand voice |
| `asc-auditor` | Catches setup mistakes in Advantage+ campaigns |
| `audience-builder` | Finds targeting options based on your customer |
| `creative-analyzer` | Scores your ads and explains what's working |
| `hook-optimizer` | Rewrites your first 3 seconds to stop the scroll |

## Suggested cadence

This is a maintenance-rhythm toolkit, not a daily one. Paid media punishes over-tinkering, so let data accumulate between runs.

- **Every 2 weeks (active accounts):** `search-terms`, `negative-keywords`, `creative-analyzer`
- **Monthly:** `pmax-auditor`, `asc-auditor`, `shopping-feed`
- **On demand (tied to your creative and launch cadence):** `rsa-generator`, `ad-copy`, `hook-optimizer`
- **At launch, new product, or a restructure:** `audience-builder`

## Components

- 10 skills (`skills/*/SKILL.md`)
- Optional brand profile (`shared/brand-profile.md`) the user fills once so skills adapt to their brand
- Shared data-intake pattern (`shared/data-intake.md`) so every skill handles connected accounts and manual exports the same way
- No agents, hooks, or bundled MCP servers. The skills use whatever ad-platform connectors the user already has.

## Notes on accuracy

The audit thresholds and benchmarks in these skills are directional starting points. The account's own averages are always the real baseline. Nothing here changes an ad account automatically; the skills produce recommendations and copy-paste-ready lists for a human to apply.

Made by Sulka Labs.
