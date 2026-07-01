# Untera Global Property Price Datasets — June 2026

Open, citeable data on what homes actually cost around the world, compiled by
**[Untera](https://untera.io)** — an independent platform aggregating international
property listings from 190+ sources across 70+ countries.

These datasets underpin Untera's public market reports. They are released free for
journalists, researchers, students, and analysts to use **with attribution**
under a [Creative Commons Attribution 4.0 (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) licence.

> **Snapshot date:** June 2026. Figures are a point-in-time snapshot of live asking
> prices and are frozen for citation stability. See `methodology.md` for how each
> measure is computed and its limitations.

---

## What's in this bundle

| File | What it measures | Countries |
|------|------------------|-----------|
| `data/untera-global-home-price-index-2026.csv` | Median asking price of a home, by country (USD) | 39 |
| `data/untera-global-price-per-sqm-2026.csv` | Median asking price per square meter, by country (USD) | 62 |
| `data/untera-what-250k-buys-2026.csv` | How many homes a USD 250,000 budget can buy, by country | 66 |

Each row carries a `listings_sampled` count so you can weight or filter by sample size.

### Column dictionaries

**`untera-global-home-price-index-2026.csv`**
- `rank` — cheapest (1) to most expensive
- `country_code` — ISO 3166-1 alpha-2
- `country` — country name
- `median_home_price_usd` — median listing asking price, USD
- `listings_sampled` — number of live listings behind the figure

**`untera-global-price-per-sqm-2026.csv`**
- `rank` — cheapest (1) to most expensive
- `country_code`, `country` — as above
- `usd_per_sqm` — median asking price per square meter, USD
- `listings_sampled` — number of live listings behind the figure

**`untera-what-250k-buys-2026.csv`**
- `country_code`, `country` — as above
- `listings_under_250k` — count of live listings priced at or below USD 250,000
- `median_price_usd` — median price of those sub-250k listings
- `cheapest_usd` — cheapest listing recorded in that country

---

## How to cite

> Untera (2026). *Untera Global Property Price Datasets — June 2026* [Data set].
> Untera. https://untera.io/press

When you publish a chart or figure derived from this data, please credit
**"Untera"** with a link to **https://untera.io**. A short note such as
*"Source: Untera (untera.io), June 2026"* is perfect.

See `CITATION.cff` for a machine-readable citation and `datapackage.json` for a
[Frictionless Data](https://frictionlessdata.io/) descriptor.

## Read the full reports

- Global Home-Price Index — https://untera.io/market-reports/global-home-price-index-2026
- Global Price-per-m² Index — https://untera.io/market-reports/global-price-per-square-meter-2026
- What $250,000 Buys Around the World — https://untera.io/market-reports/what-250k-buys-2026
- Global Property Index (every country scored 0–100) — https://untera.io/property-index
- Data sources & coverage — https://untera.io/data-quality
- Press & data hub — https://untera.io/press

## Licence

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). You are free to share and
adapt the data for any purpose, including commercially, as long as you give
appropriate credit to Untera and link back to https://untera.io.

## Contact

For interviews, custom data cuts (by region, property type, or price band), or
commentary on international property and relocation trends, reach William Marsh,
Founder of Untera, via the contact form at https://untera.io/press.
