# Alo Yoga — U.S. Expansion Opportunity Analysis

An end-to-end retail site-selection framework built to identify optimal U.S. expansion markets and specific venues for Alo Yoga. Three interactive HTML dashboards, self-contained with no build step required.

---

## Dashboards

| File | Purpose | Markets / Sites |
|------|---------|-----------------|
| `alo_site_analysis.html` | **Tier 1 — Metro Ranking** | 39 MSAs scored & ranked |
| `alo_reverse_engineering.html` | **Model Validation** | 76+ actual stores mapped vs. model |
| `alo_tier2_analysis.html` | **Tier 2 — Site Analysis** | 21 venues across 5 gap markets |

Each file is fully self-contained (data embedded, Chart.js loaded from CDN). Open any one locally in a browser or host on GitHub Pages — no server needed.

---

## Tier 1 — Metro Scoring Model

**39 MSAs** scored across five weighted buckets:

| Bucket | Weight | Key Variables |
|--------|--------|--------------|
| Wealth & Income | 28% | % HH $150K+, median home price, 5yr appreciation, % college-educated |
| Lifestyle & Psychographic | 27% | Boutique fitness density, Whole Foods per 100K, yoga studio index |
| Competitive Landscape | 17% | Lululemon store count (positive signal), Alo saturation (penalty), Vuori/Athleta |
| Market Dynamics | 14% | 5yr population growth, net migration index, GDP per capita growth |
| Tourism & Urban Prestige | 14% | Annual visitors, hotel density, tourist destination score |

**Opportunity Score** = composite score adjusted down for markets where Alo is already saturated relative to Lululemon (up to 25% penalty). Class A mall count multiplier applied (0.75× to 1.10×).

### Top 5 Opportunity Markets (v2)
1. San Francisco-Oakland (6.33) — 2 stores
2. **Seattle-Tacoma (6.10) — 0 stores ★ Largest gap**
3. Los Angeles-Long Beach (6.07) — 9 stores
4. Austin-Round Rock (6.02) — 1 store
5. Miami-Fort Lauderdale (5.83) — 5 stores

---

## Model Validation (Reverse Engineering)

76+ confirmed U.S. Alo store locations mapped and compared against model scores:

- **85% directional accuracy** — all markets scoring above 5.0 have confirmed Alo presence
- **Chicago & Philadelphia identified as model misses** — tourism/urban prestige underweighted in v1; corrected in v2 weights
- **6 strategic patterns** extracted from actual portfolio (cluster-first, mall quality > mall count, Lululemon co-location signal, etc.)

---

## Tier 2 — Site-Level Framework

Five gap markets → 21 candidate venues evaluated on:

| Dimension | Weight | Key Signals |
|-----------|--------|-------------|
| Venue Quality | 25% | National sales/sqft rank, anchor caliber, vacancy rate |
| Trade Area Demographics | 25% | 5-mi ring % HH $150K+, median age 28–42, employer base |
| Co-Tenancy | 25% | Lululemon same venue, Apple Store, Nordstrom/Neiman, Equinox |
| Accessibility | 15% | Parking, highway proximity, transit score |
| Real Estate Economics | 10% | Est. rent $/sqft, occupancy cost % (knockout: >22%) |

### Priority 1 Sites (score ≥ 8.5, occ cost < 10%)
| Site | Market | Score | Occ% |
|------|--------|-------|------|
| Westfield UTC | San Diego | 9.15 | 7.2% |
| Domain NORTHSIDE | Austin | 9.03 | 6.2% |
| Highland Park Village | Dallas | 8.97 | 7.0% |
| University Village | Seattle | 8.80 | 5.9% |
| Legacy West | Dallas | 8.78 | 5.9% |
| Westfield Bellevue Square | Seattle | 8.70 | 7.3% |

**Zero economic knockouts** across all 21 sites.

---

## Using on GitHub Pages

1. Fork or push this repo to GitHub
2. Go to **Settings → Pages → Source: Deploy from branch → main / root**
3. GitHub will publish at `https://yourusername.github.io/alo-expansion-analysis/`
4. The landing page is `alo_site_analysis.html` — navigate between dashboards using the top nav bar in each file

To set a custom landing page, rename `alo_site_analysis.html` to `index.html` (the other two files link to each other by filename so no other changes needed).

---

## Data Sources

- **Income & Demographics:** U.S. Census ACS 5-Year Estimates (2022)
- **Home Prices:** Zillow Home Value Index, Redfin Market Data
- **Lifestyle Proxies:** Google Places density estimates, Yelp business counts
- **Retail Competition:** Company store locators (Lululemon, Alo, Vuori, Athleta) + MallSeeker, SGB Online
- **Tourism:** U.S. Travel Association, STR hotel data
- **Economic Growth:** BEA Regional GDP, Census population estimates
- **Tier 2 Real Estate:** CoStar benchmarks, ICSC research, Esri 5-mile ring demographics

---

*Built Q1 2025 · Data reflects late 2024 store counts · For strategy/analytical use only*
