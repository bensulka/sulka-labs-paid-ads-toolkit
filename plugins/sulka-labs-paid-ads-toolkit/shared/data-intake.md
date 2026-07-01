# Data intake pattern (shared)

Every skill in this toolkit needs account data. Follow this order every time.

## Step 0: Load brand context

Check whether the user has filled `${CLAUDE_PLUGIN_ROOT}/shared/brand-profile.md`. If it has content, use it for brand name, voice, ideal customer, target CPA/ROAS, and budget so you do not re-ask for things already provided. If it is blank, just proceed and ask only for what the specific skill needs. Never require the user to fill it.

## Step 1: Try a connected account first

Check whether the user has a connected data source that can return the data this skill needs. Look for any of:

- A Supermetrics connector (covers Google Ads and Meta/Facebook Ads)
- A native Google Ads or Google Ads MCP connector
- A native Meta / Facebook Ads connector
- Any connected analytics source (GA4) for downstream metrics

If a relevant connector is available, use it to pull the exact fields the skill lists in its "Data needed" section. Confirm the account and date range with the user before pulling, then proceed.

## Step 2: Fall back to manual paste or file drop

If no connector is available, do NOT stall. Tell the user exactly what to export and how, then work from what they paste or drop in. Accept pasted tables, CSVs, XLSX, or screenshots.

### Google Ads exports

- **Search terms report**: Google Ads > Campaigns > Insights & reports > Search terms. Set the date range (last 30-90 days). Include columns: Search term, Campaign, Ad group, Match type, Cost, Clicks, Impressions, CTR, Conversions, Conv. value, Cost/conv. Download as CSV or Excel.
- **Performance Max**: open the PMax campaign, screenshot or export the asset groups, asset details, audience signals, search themes, and listing groups. Also grab campaign settings (final URL expansion, brand exclusions, geo, schedule).
- **Shopping feed**: export the product feed from Google Merchant Center (Products > All products > download) or share the source feed (title, description, GTIN, brand, product type, color, size, material, gender, age group, price, availability).
- **RSA / ads**: no export needed. Ask for the product/landing page URL, offer, top keywords, and USPs.

### Meta Ads exports

- **Ads Manager report**: Ads Manager > Reports or the main table. Set the level (campaign / ad set / ad). Add columns: Amount spent, Impressions, Reach, Frequency, CTR (all and link), CPC, CPM, Hook rate (3-sec / thumbstop), Hold rate (ThruPlay or 15-sec views), Results, Cost per result, Purchase ROAS, Adds to cart. Export as CSV/XLSX, or paste the table.
- **Advantage+ Shopping / Advantage+ sales audit**: screenshot the campaign settings (existing customer budget cap, attribution setting, cost cap or ROAS control, placements, catalog), and the number/type of active creatives.
- **Creative analysis**: attach the ad creative (image or video) and/or paste its performance row from Ads Manager.
- **Ad copy / audiences / hooks**: no export needed. Ask for the product, offer, ideal customer, brand voice samples, and awareness level.

## Step 3: Only ask for what is missing

Never ask for everything at once. If the user already pasted a search terms report, do not re-request it. Fill gaps with reasonable defaults and note any assumptions.
