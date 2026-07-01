---
name: asc-auditor
description: >
  This skill should be used when the user wants to audit a Meta Advantage+
  Shopping campaign (now called Advantage+ sales) for setup mistakes. Trigger
  on phrases like "audit my Advantage+ campaign", "ASC audit", "check my
  Advantage+ shopping setup", "is my Advantage+ campaign set up right", "why
  is my ASC underperforming", or when the user shares Advantage+ campaign
  settings. Returns setup mistakes and a prioritized fix list.
metadata:
  version: "0.1.0"
  author: "Sulka Labs"
---

# ASC Auditor: catch setup mistakes in Advantage+ campaigns

Audit a Meta Advantage+ Shopping campaign (Advantage+ sales) and surface the setup mistakes that quietly cap performance.

## Data needed

Campaign settings and creative makeup. Follow `${CLAUDE_PLUGIN_ROOT}/shared/data-intake.md`. Ask for screenshots or notes on: existing-customer budget cap, attribution setting, cost cap / ROAS controls, budget, placements, catalog connection, and the number and type of active creatives. If a connector is available, pull spend, ROAS, and creative-level data.

## What to check

1. **Existing-customer budget cap.** This is the most misused lever. If the cap is high (or default), the campaign spends on retargeting warm buyers and reports inflated ROAS while starving new-customer acquisition. Recommend a cap aligned to the goal (often lower for prospecting-led growth). Always inspect this first.
2. **Creative volume and diversity.** ASC rewards many creatives. Flag if there are too few (aim for a healthy pool across static, video, UGC, and different angles) so the algorithm has room to find winners. One or two creatives is a common failure.
3. **Creative freshness.** Are new creatives being added on a cadence, or is the campaign riding stale winners into fatigue? Recommend a refresh rhythm.
4. **Attribution setting.** Note the attribution window (e.g., 7-day click / 1-day view) and whether reporting is being compared apples-to-apples. Misread attribution drives bad budget calls.
5. **Cost controls.** Cost cap or ROAS goal set too aggressively can choke delivery; none at all can overspend on weak audiences. Match the control to the account's maturity.
6. **Budget and learning.** Is budget high enough to exit the learning phase (enough conversions per week), and is the user resetting learning by editing too often?
7. **Placements and catalog.** Advantage+ placements on, catalog connected and healthy, dynamic formats enabled where relevant.
8. **Account structure around ASC.** Is there a clean split between ASC and any manual/BAU campaigns for creative testing, or are they cannibalizing each other and muddying signal?
9. **Audience controls.** Any unnecessary exclusions or narrowing that fights the broad-targeting model.

## Output format

1. **Verdict** in one paragraph: the biggest thing capping this campaign.
2. **Scorecard:** each area, status (OK / Fix / Critical), one-line reason. Lead with the existing-customer cap and creative volume.
3. **Prioritized fixes**, highest impact first, each a specific action.
4. **Creative gap:** what types to add next and how many.
5. **One next step.**

No emojis, no em dashes.
