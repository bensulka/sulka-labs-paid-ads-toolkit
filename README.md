# Sulka Labs Paid Ads Toolkit

Ten free Claude skills that audit and improve Google Ads and Meta Ads accounts. Find wasted spend, grade your campaigns, write ads that sound human, build audiences, and stop the scroll.

They run inside Claude, connected to your real ad data or working from a data export you paste in. No dashboard, no API keys, no code.

Built by [Sulka Labs](https://sulkalabs.com), a human-led, AI-driven growth partner for DTC brands.


---

## The skills

### Google Ads

| Skill | What it does |
| --- | --- |
| negative-keywords | Finds wasted spend and builds an exact and phrase-match block list |
| pmax-auditor | Grades your Performance Max assets and tells you what to fix |
| rsa-generator | Writes responsive search ads that don't sound robotic |
| search-terms | Surfaces winners and losers in your search terms report |
| shopping-feed | Checks product titles, descriptions, and attributes for issues |

### Meta Ads

| Skill | What it does |
| --- | --- |
| ad-copy | Writes primary text that matches your brand voice |
| asc-auditor | Catches setup mistakes in Advantage+ campaigns |
| audience-builder | Finds targeting options based on your customer |
| creative-analyzer | Scores your ads and explains what's working |
| hook-optimizer | Rewrites your first 3 seconds to stop the scroll |

---

## Install

### Option A: One-click (Claude Code or Cowork with plugins)

In Claude, run:

```
/plugin marketplace add bensulka/sulka-labs-paid-ads-toolkit
/plugin install sulka-labs-paid-ads-toolkit@sulka-labs
```

That is it. Ask Claude "find wasted spend in my Google Ads" or "rewrite my hook" and the right skill loads.

### Option B: Drop-in file (Cowork)

1. Download `sulka-labs-paid-ads-toolkit.plugin` from this repo.
2. Drag it into Claude, or add it under Settings > Capabilities.
3. Ask Claude what you need.

### Option C: Manual (any Claude, including claude.ai Pro)

1. Download or clone this repo.
2. Open any skill file under `plugins/sulka-labs-paid-ads-toolkit/skills/`.
3. Paste its contents into Claude as a prompt, or add the folder as project knowledge.

---

## Connect your data (optional)

The skills work two ways:

- **Connected account:** if you have Google Ads or Meta connected to Claude (for example through a connector like Supermetrics), the skills pull data automatically.
- **Manual:** if not, each skill tells you exactly what to export or paste, then works from that.

Tip: open `plugins/sulka-labs-paid-ads-toolkit/shared/brand-profile.md`, fill it in once, and every skill adapts to your brand, voice, and targets.

---

## Suggested cadence

This is a maintenance-rhythm toolkit, not a daily one. Let data accumulate between runs.

- Every 2 weeks on active accounts: search-terms, negative-keywords, creative-analyzer
- Monthly: pmax-auditor, asc-auditor, shopping-feed
- On demand, when building new ads: rsa-generator, ad-copy, hook-optimizer
- At launch or a restructure: audience-builder

---

## Want a human to run it for you?

These skills are free, forever. If you would rather have a senior team run your paid media, Sulka Labs scales DTC brands profitably across Google, Meta, and Amazon. Grab a free performance review at [sulkalabs.com](https://sulkalabs.com) or email ben@sulkasearch.com.

## License

MIT. Use it, fork it, adapt it.
